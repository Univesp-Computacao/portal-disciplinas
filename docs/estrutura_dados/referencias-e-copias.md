# Referências e Cópias (Valor)

Em C++, podemos passar argumentos e retornar variáveis por referência
ou valor, isto é, uma cópia. A escolha entre um e outro está relacionada
com a performance do programa e boas práticas. Para entendermos bem, uma
revisada em alocação estática vs dinâmica é importante.

## Antes de começarmos

Para os estudos nessa seção, vamos apresentar uma classe que irá expor quando
um objeto é criado, destruido, copiado ou atribuido. Assim, ficará claro o
momento exato de cada processo. Nosso objeto terá a seguinte interface, no
arquivo `obj.h`:

```C++
#ifndef OBJ_H
#define OBJ_H

class OBJ
{
    private:
        static int count;
        int id;
        int cp;
    public:
        Obj();
        ~Obj();
        Obj(const Obj& o);
        Obj& operator = (const Obj& o);
        void print_id_address();
        void print_cp_address();
        void print_obj_address();
        void print_full_address();
};
#endif
```
Cada um dos membros tem a seguinte função:

- **count** : responsável por gerar números sequenciais, assim podemos criar
identificadores únicos para cada objeto;
- **id** : responsável por armazenar o identificador único do objeto;
- **cp** : responsável por armazenar a origem do objeto copiado ou atribuido,
quando construido do zero, ele recebe o próprio `id`;
- **Obj()** : é o construtor;
- **~Obj()** : é o destrutor;
- **Obj(const Obj& o)** : é o construtor de cópia;
- **Obj& operator = (const Obj& o)** : é o operador de atribuição, isto é, (=);
- **print_...** : são responsáveis por imprimir endereços das variáveis;

A implementação encontra-se no arquvio `obj.cpp`, a lógica por trás da classe é
incrementar `count` a cada chamada de construtor, cópia ou atribuição passando esse
valor para o `id`. Quando há cópia ou atribuição, o `id` do objeto copiado é passado
para o objeto final em `cp`. Para sabermos quando cada método é invocado, usamos
um print com o `id` e/ou `cp`.

## Alocação de Memória: Estática vs Dinâmica

Quando executamos um processo, precisamos reservar memória para ele. Essa memória
é dividida em sessões sendo as principais: **stack** e **heap**. Toda vez que chamamos
uma função, a pilha de execução recebe um *push* armazenando variáveis e instruções
na *stack*. Quando a função encerra, tudo que foi armazenado na *stack* é liberado,
isto é, pode ser sobreescrito por uma nova chamada. Ex:

```C++
void test_static_alloc()
{
    std::cout << "Inicio Alocacao Estatica\n";
    Obj o;
    std::cout << "Final Alocacao Estatica\n;
}
```
Se executarmos essa função, ela gera o seguinte output:

```
Inicio Alocacao Estatica
Construtor Objeto(1)
Final Alocacao Estatica
Destrutor Objeto(1) chamado
```

Como pode observar, o objeto é criado no exato momento em que é definido e
é destruido após encerrar o programa. Já na alocação dinâmica, temos a
responsabilidade de liberar a memória, no caso de objetos, invocar seu
destrutor. Para alocarmos dinamicamente, usamos `new` e para liberar
`delete`. Variáveis alocadas dinamicamente são armazenadas no *heap*, assim
elas podem permanecer armazenadas após o final da função. Ex:

```C++
void test_dynamic_alloc()
{
    std::cout << "Inicio Alocacao Dinamica\n";
    Obj* o = new Obj();
    delete o;
    std::cout << "Final Alocacao Dinamica\n";
}
```

Repare que estamos usando ponteiros, isso porque o operador `new`nos retorna um
ponteiro e devemos manter o endereço de memória sempre armazenado em alguma
variável. Assim, podemos liberar aquele endereço. Outro ponto importante é:
não devemos usar `delete` num endereço já liberado, o resultado dessa operação
é indefinido.

A função anterior gera o seguinte output:

```
Inicio Alocacao Dinamica
Construtor Objeto(2) chamado
Destrutor Objeto(2) chamado
Final Alocacao Dinamica
```

Repare que o construtor continua sendo chamado no momento da definição, mas
agora temos total controle do momento em que o destrutor é chamado, podendo
inclusive ser invocado fora do escopo da função, desde que temos o endereço
da memória alocada.

No próximo exemplo, temos um vazamento de memória e uma prova de que o objeto
persiste armazenado mesmo após o final da execução do programa. Em sistemas
operacionais modernos, a memória de um processo é sempre monitorada para 
libera-la ao final da execução, mesmo que o programa não a libere.

```C++
void test_memory_leak()
{
    std::cout << "Inicio Vazamento de Memoria\n";
    Obj* o = new Obj();
    std::cout << "Final Vazamento de Memoria\n";
}
```
Output:
```
Inicio Vazamento de Memoria
Construtor Objeto(13) chamado
Final Vazamento de Memoria
```

Repare que o Objeto(13) não será destruído ao longo do programa.

### Array

A sintaxe para alocação estática e dinâmica de arrays é muito similar e revela
a forma correta de liberar memória: devemos liberar na ordem
inversa que alocamos. Assim, temos as seguintes funções e seus outputs:

```C++
void test_static_alloc_array()
{
    std::cout << "Inicio Alocacao Estatica Array\n";
    Obj o[5];
    std::cout << "Final Alocacao Estatica Array\n";
}
void test_dynamic_alloc_array()
{
    std::cout << "Inicio Alocacao Dinamica Array\n";
    Obj* o = new Obj[5];
    delete [] o;
    std::cout << "Final Alocacao Dinamica Array\n";
}
```
```
Inicio Alocacao Estatica de Array
Construtor Objeto(3) chamado
Construtor Objeto(4) chamado
Construtor Objeto(5) chamado
Construtor Objeto(6) chamado
Construtor Objeto(7) chamado
Final Alocacao Estatica de Array
Destrutor Objeto(7) chamado
Destrutor Objeto(6) chamado
Destrutor Objeto(5) chamado
Destrutor Objeto(4) chamado
Destrutor Objeto(3) chamado
Inicio Alocacao Dinamica de Array
Construtor Objeto(8) chamado
Construtor Objeto(9) chamado
Construtor Objeto(10) chamado
Construtor Objeto(11) chamado
Construtor Objeto(12) chamado
Destrutor Objeto(12) chamado
Destrutor Objeto(11) chamado
Destrutor Objeto(10) chamado
Destrutor Objeto(9) chamado
Destrutor Objeto(8) chamado
Final Alocaco Dinamica de Array
```

## Passagem de Argumentos: Valor vs Referência

Em C++, ao contrário de outras linguagens, podemos passar objetos por **valor**
ou **referência**. Quando passamos um objeto por *valor*, uma cópia é criada e
armazenada na *stack*, e como vimos, é destruído quando a função encerra. Por 
outro lado, quando passamos por *referência*, estamos passando um *alias*, isto
é, um outro identificador para o mesmo objeto válido. Assim, ele tem efeito fora
do escopo daquela função, ou seja, podemos modificá-lo sem precisar retornar.

Para testar as funções abaixo, lembre-se de passar um objeto para função.

```C++
void test_pass_by_value(Obj o, int i)
{
    printf("Inicio Passar Por Valor %d\n", i);
    if (i == 0) {
        std::cout << "Endereco de Obj antes:" << &o << std::endl;
        test_pass_by_value(o, i + 1);
    } else {
        std::cout << "Endereco de Obj depois:" << &o << std::endl;
    }
    printf("Final Passar Por Valor %d\n",i);
}
void test_pass_by_ref(Obj& o, int i)
{
    printf("Inicio Passar Por Referencia %d\n", i);
    if (i == 0) {
        std::cout << "Endereco de Obj antes:" << &o << std::endl;
        test_pass_by_ref(o, i + 1);
    } else {
        std::cout << "Endereco de Obj depois:" << &o << std::endl;
    }
    printf("Final Passar Por Referencia %d\n", i);
}
```
```
Construtor Copia de (0) para Objeto(14) chamado
Inicio Passar Por Valor 0
Endereco de Obj antes:0x7ffd6ba2f5b8
Construtor Copia de (14) para Objeto(15) chamado
Inicio Passar Por Valor 1
Endereco de Obj depois:0x7ffd6ba2f578
Final Passar Por Valor 1
Destrutor Objeto(15) chamado
Final Passar Por Valor 0
Destrutor Objeto(14) chamado
Inicio Passar Por Referencia 0
Endereco de Obj antes:0x7ffd6ba2f5b0
Inicio Passar Por Referencia 1
Endereco de Obj depois:0x7ffd6ba2f5b0
Final Passar Por Referencia 1
Final Passar Por Referencia 0
```
Repare que, quando passamos por valor, o construtor de cópia é chamado,
enquanto que, quando passamos por referência, ele não é. Outro ponto é que o
endereço se mantém. Isso implica que passar por referência é mais performático
que passar por valor, usando menos processamento e memória.

## Retornar e Atribuir

### Por Valor

No caso de retornar objetos existe uma peculiaridade: dependendo do compilador
usado, existem otimizações no retorno por valor que não geram cópias. Essa
opçâo pode ser desabilitada passando `--fno-elide-construtors` no momento da
compilação se estiver utilizando `g++`.

Por enquanto, vamos analisar o resultado com essa otimização, que evita chamadas
desnecessárias ao construtor de cópia.

```C++
Obj test_return_by_value()
{
    cout << "Inicio Retornar por Valor\n";
    Obj o;
    cout << "Final Retornar Por Valor\n";
    return o;
}
void test_assignment_by_value()
{
    cout << "Inicio Atribuicao Por Valor\n";
    Obj o;
    o.print_full_address();
    o = test_return_by_value();
    o.print_full_address();
    Obj p = test_return_by_value();
    cout << "Final Atribuicao por Valor\n";
}
```
Usando apenas a função `test_assignment_by_value()`, obtemos o seguinte:
```
Inicio Atribuicao Por Valor
Construtor Objeto(16) chamado
Endereco de Obj: 0x7ffd6ba2f570
Endereco do ID: 0x7ffd6ba2f570
Endereco de CP: 0x7ffd6ba2f574
Inicio Retornar por Valor
Construtor Objeto(17) chamado
Final Retornar Por Valor
Operador Atribui de (17) para Objeto(16) chamado
Destrutor Objeto(17) chamado
Endereco de Obj: 0x7ffd6ba2f570
Endereco do ID: 0x7ffd6ba2f570
Endereco de CP: 0x7ffd6ba2f574
Inicio Retornar por Valor
Construtor Objeto(18) chamado
Final Retornar Por Valor
Final Atribuicao por Valor
Destrutor Objeto(18) chamado
Destrutor Objeto(16) chamado
```
Observe que o endereço do objeto atribuido não se altera, nem suas variáveis.
Como criamos um objeto dentro de `test_return_by_value()`, vemos a sua criação
e, em seguida, ocorre a atribuição Objeto(16) = Objeto(17). Porém, logo que a
função encerra, o Objeto(17) é destruido. No segundo caso, vemos o resultado
da otimização, pois o objeto é criado dentro da função e retornado. Isso ocorre,
pois a declaração/definição e atribuição estão na mesma linha. Se desativar a 
otimização, poderá observar que o processo de cópia e destruição ocorre em ambos
os casos. Ex:

```
Inicio Atribuicao Por Valor
Construtor Objeto(16) chamado
Endereco de Obj: 0x7fff7f2cdb48
Endereco do ID: 0x7fff7f2cdb48
Endereco de CP: 0x7fff7f2cdb4c
Inicio Retornar por Valor
Construtor Objeto(17) chamado
Final Retornar Por Valor
Construtor Copia de (17) para Objeto(18) chamado
Destrutor Objeto(17) chamado
Operador Atribui de (18) para Objeto(16) chamado
Destrutor Objeto(18) chamado
Endereco de Obj: 0x7fff7f2cdb48
Endereco do ID: 0x7fff7f2cdb48
Endereco de CP: 0x7fff7f2cdb4c
Inicio Retornar por Valor
Construtor Objeto(19) chamado
Final Retornar Por Valor
Construtor Copia de (19) para Objeto(20) chamado
Destrutor Objeto(19) chamado
Construtor Copia de (20) para Objeto(21) chamado
Destrutor Objeto(20) chamado
Final Atribuicao por Valor
Destrutor Objeto(21) chamado
Destrutor Objeto(16) chamado
```

### Por Referência

Retornar por referência possui uma série de particularidades, e, se está
iniciando, evite usar essa técnica. Por outro lado, seu principal uso é a
sobrecarga de operadores, como a que fizemos para atribuir. A regra principal
a ser seguida é: nunca crie uma variável local e a retorne por referência, pois
seu endereço será liberado criando o chamado *dangling pointer* gerando comportamento
indefinido da aplicação. Aqui, mostramos um exemplo e o resultado do output:

```C++
Obj& test_return_by_ref(Obj& o)
{
    cout << "Inicio Retornar por Referencia\n";
    cout << "Final Retornar por Referencia\n";
    return o;
}
void test_assignment_by_ref()
{
    cout << "Inicio Atribuicao por Referencia\n";
    Obj o;
    o.print_full_address();
    Obj& p = test_return_by_ref(o);
    p.print_full_address();
    cout << "Final Atribuicao por Referencia\n";
}
```
Usando apenas `test_assingment_by_ref()`:
```
Inicio Atribuicao por Referencia
Construtor Objeto(22) chamado
Endereco de Obj: 0x7fff7f2cdb50
Endereco do ID: 0x7fff7f2cdb50
Endereco de CP: 0x7fff7f2cdb54
Inicio Retornar por Referencia
Final Retornar por Referencia
Endereco de Obj: 0x7fff7f2cdb50
Endereco do ID: 0x7fff7f2cdb50
Endereco de CP: 0x7fff7f2cdb54
Final Atribuicao por Referencia
Destrutor Objeto(22) chamado
```
Repare que só um construtor é chamado. Esse resultado é independente da
otimização e reforçando: evite essa técnica.

## Prática Recomendada

A prática mais recomendada é passar por referência e retornar por valor.
Assim temos o código mais performático e seguro. Podemos também passar por
referência e alterar o objeto gerando um efeito fora do escopo da função.
Essa técnica é particularmente recomendada quando queremos retornar mais de
uma variável ao mesmo tempo de tipos diferentes.

```C++
Obj test_pass_by_ref_return_by_value(Obj& o)
{
    cout << "Inicio Passagem por Referencia Retorno po Valor\n";
    cout << "Final Passagem por Referencia Retorno po Valor\n";
    return o;
}
int main()
{
    Obj o;
    ...

    cout << "Pratica mais recomendada\n";
    Obj p = test_pass_by_ref_return_by_value(o);
    return 0;
}

```
```
Pratica mais recomendada
Inicio Passagem por Referencia Retorno po Valor
Final Passagem por Referencia Retorno po Valor
Construtor Copia de (0) para Objeto(20) chamado
```
