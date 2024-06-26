Avaliação diagnóstica (AD) consiste em exercícios ou projetos desenvolvidos em grupo ao longo da disciplina.
A primeira avaliação diagnóstica (AD1) será composta por exercícios e equivale a 30% da nota da primeira avaliação (AV1).

Segue abaixo a expressão para o cálculo da AV1, sendo sendo AF1 equivale a primeira avaliação formativa e AD1, a primeira avaliação diagnóstica.


A AD1 é formada pela entrega dos exercícios (EX1) na data prevista e apresentação (AP1) de um dos exercícios escolhido pelo professor. Segue abaixo a expressão para o cálculo da AD1.


A EX1 é avaliada mediante a correção dos exercícios, sendo a avaliação no intervalo de 0% (não atende a questão), 50% (atende parcialmente) e 100% (atende em sua totalidade). Por exemplo, se o exercício equivale a 2 pontos e sua correção atente parcialmente a questão, então sua avaliação deste exercício será 1 ponto.

A AP1 é avaliada mediante aos pré-requisitos de clareza, organização e domínio do conteúdo. Portanto, o aluno deve demonstrar um bom entendimento do algoritmo, explicando seus princípios fundamentais, seu propósito e como ele funciona passo a passo.

A avaliação da AP1 é apenas considerada no intervalo de 0% (não atende os pré-requisitos), 50% (atende parcialmente) e 100% (atende em sua totalidade). Por exemplo, se na apresentação do exercício, o aluno atenter parcialmente os pré-requisitos, então sua avaliação da apresentação será 5,0.

# AD1

### questão 1
Dadas duas variáveis, A e B, implemente e teste um algoritmo para trocar os valores atribuídos a elas.
### pseudocodigo
```
DECLARE x, y, aux INTEIRO
// variaveis x e y como 
ESCREVA "digite o valor de x:"
LEIA x
ESCREVA "digite o valor de y:"
LEIA y
aux <- y
y <- x
x <- aux
ESCREVAL "x agora vale: ", x"
ESCREVAL "y agora vale: ", y"
```

### FLUXOGRAMA
```mermaid
flowchart TD
a([inicio]) --> b{{digite dois valores: }}
b --> c[/A, B/]
c --> d[auxiliar <-- A]
d --> e[A <-- B]
e --> f[B <-- auxiliar]
f --> g{{o valor de A agora é: A, e o valor de B agora é: B}}
g --> h([fim])
```
### teste de mesa
```
| a  | b  | aux | a  | b  | saída 1 | saída 2 | 
| -- | -- | --  | -- | -- | --      | --      | 
| 0  | 1  | 0   | 1  | 0  | a = 1   | b = 0   |

```

### Questão 2 - Contagem 

Dado um conjunto n de notas de alunos em um exame, implemente e teste um algoritmo para fazer uma contagem cont do número de alunos que foram aprovados no exame. 
Será considerado aprovado o aluno que tirar nota 50 ou maior (no intervalo de 0 a 100).

1. Obter o número de notas n a serem processadas;
2. Inicializar a contagem cont com zero;
3. Enquanto houver notas a serem processadas, fazer repetidamente:
    - obter a próxima nota;
    - se a nota for suficiente para passar no exame (n ≥ 50) então adicionar 1 (um) à contagem $cont$;
4. Exibir a contagem cont (número total de aprovações).
### pseudocodigo
```
Algoritmo ContaAprovacoes
DECLARAR nNot, cont, i, nota: INTEIRO
INICIAR
ESCREVA "Digite o numero de notas: "
LEIA nNot
ENQUANTO i < n FAÇA
	ESCREVA "digite a nota: "
	LEIA nota
	SE nota >= 50 ENTÃO
		cont = cont + 1
	i = i + 1
FIM_ENQUANTO
ESCREVA "numero de alunos aprovados: ", cont
FIM
```

### fluxograma:

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de alunos: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[\i = 1\]
E --> F{i <= n}
F --FALSE--> W{{Número de alunos aprovados: cont}}
W --> Z([FIM])
F --TRUE--> G{{Digite a nota do aluno, i}}
G --> H[\nota\]
H --> I{"nota >= 50 <br>E <br>nota <=100"}
I --TRUE--> J[\cont =+ 1\]
I --FALSE--> K[\i =+ 1\]
J --> K
K --LOOP--> F
```

### Teste de mesa 
```
| it | n  | i  | cont | i<=n  | nota, i | nota | nota_valida | cont+1 | i+1 | saída        | 
| -- | -- | -- | --   | --    | --      | --   | --          | --     | --  | --           |
| 1  | 3  | 1  |  0   | True  | nota 1  | 60   | True        | 1      | 2   |              |
| 2  | 3  | 2  |  1   | True  | nota 2  | 40   | False       | 1      | 3   |              |
| 3  | 3  | 3  |  1   | True  | nota 3  | 90   | True        | 2      | 4   |              |
| 4  | 3  | 4  |  2   | False |         |      |             |        |     | Aprovados: 2 |
```

### Questão 3 - Soma de um conjunto de números

Dado um conjunto de $n$ números, implemente e teste um algoritmo para calcular a soma desses números. <br>
Aceite apenas $n$ maior ou igual a zero.

#### Descrição geral do algoritmo

1. Obter a quantidade de números $n$ a serem somados.
2. Inicializar a variável $soma$ com 0 (zero).
3. Enquanto menos do que $n$ números tiverem sido somados, fazer repetidamente:
    - obter o próximo número $i$;
    - calcular a soma atual, adicionando o número $i$ obtido à soma mais recente;
4. Exibir a soma dos $n$ números

### Fluxograma 

```mermaid
flowchart TD
a([INICIO]) --> b{{Digite quantos numeros serão somados: }}
b --> c[/n/]
c --> d[soma = 0, a = 0]
d --> e{a != n}
e --false--> f{{soma}}
f --> F([FIM])
e --loop--> g{{Digite um numero: }}
g --> h[/i/]
h --> i[soma = soma + i]
i --> j[a = a + 1]
j --> e

```
### Pseudocódigo 

```
Algoritmo soma_de_numeros
DECLARAR n, soma, i, num: INTEIRO
INICIAR
ESCREVA "Digite quantos numeros serão somados: "
LEIA n
SE n >= 0 ENTAO
	soma <- 0
	i <- 1
	ENQUANTO i <= n FAÇA
		Digite um numero:, i
		LEIA num
		soma = soma + num
		i = i+1
	FIM_ENQUANTO
SENAO
	ESCREVA "o n deve ser maior ou igual a zero" 
FIMSE	
	
FIMALGORITMO
```
#### Teste de mesa 

| Entrada | n1 | n2 | n3 | n4 | n5 | Saída |
|   --    | -- | -- | -- | -- | -- |  ---  |
|   3     |  4 |  7 |  2 | -- | -- |  13   |
|   5     |  9 | 16 | 11 |  7 | 15 |  58   |

### Questão 4 - Cálculo de uma série 

Dado um conjunto de $n$ termos da série, implemente e teste um algoritmo para calcular o valor de S, conforme definido abaixo:

$$ S = \frac{1}{2} + \frac{3}{4} + \frac{5}{6} + \frac{7}{8} + \dots $$

#### Descrição geral do algoritmo

1. Obter o número de termos $n$;
2. Inicializar a variável $S$ com 0 (zero).
3. Iterar o valor de $n$ na variável $i$ iniciando com 0 (zero), de acordo com as instruções abaixo:
    - calcular o numerador na variável $numerador$;
    - calcular o denominador  na variável $denominador$;;
    - calcular o termo da série na variável $termo$, onde $termo = numerador/denominador$;
    - adicionar esse termo à variável $S$.
4. Exibir o valor da série $S$.

### Fluxograma 

```mermaid
flowchart TD
a([INICIO]) --> b{{Digite o numero de termos: }}
b --> c[/n/]
c --> d[S = 0, i = 0]
d --> e{i < n}
e --false--> f{{S}}
f --> l([FIM])
e --loop--> g[numerodor = i * 2 + 1]
g --> h[denominador = i * 2 + 2]
h --> i[termo = numerador/denominador]
i --> j[S = S + termo]
j --> k[i = i + 1]
k --> e

```

### Pseudocódigo 

```
Algoritmo calculo_de_serie
DECLARAR numT, S, i, numerador, denominador, termo: REAL
ESCREVA Digite o numero de termos: 
LEIA numT
// variaveis S e i declaradas como 0 e 0 respectivamente
S = 0 
i = 0
ENQUANTO i < numT FACA
	numerador = i * 2 + 1
	denominador = i * 2 + 2
	termo = numerador/denominador
	S = S + termo
	i = i + 1
FIM_ENQUANTO
ESCREVA S
FIM
```
#### Teste de mesa 

|   Entrada   |    Saída    |
|    ---      |     ---     |
|     3       |    1,78     |
|     6       |    4,775    |


### Questão 5 - Cálculo fatorial

Dado um número $n$, implemente e teste um algoritmo para calcular o fatorial de $n$ (escrito como $n!$), onde $n ≥ 0$.

#### Descrição geral do algoritmo

1. Obter o número $n$, onde $n \geq 0$;
2. Inicializar a variável $fator$ com 1 (um) para armazenar o resultado do cálculo do fatorial;
3. Iterar o valor de $n$ na variável $i$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Incrementar o valor atual $fator$ multiplicando pelo valor de $i$;
4. Exibir o resultado ($n!$).

### Fluxograma 

```mermaid
flowchart TD
a([INICIO]) --> b{{Digite um numero maior ou igual a 0: }}
b --> c[/n/]
c --> d[fator = 1, i = 1]
d --> D{n = 0 ou n = 1}
D --false--> e{i < n}
D --true--> E{{fator}}
e --loop--> f[fator = fator * i]
f --> g[i = i + 1]
g --> e
e ---false--> h{{fator}}
h --> i([FIM])
E --> i
```

#### Pseudocódigo 

```
Algoritmo calculo_fatorial
DECLARAR n, fator, i: INTEIRO
INICIAR
// variavel n declarada pelo usuario
ESCREVER "Digite um numero maior ou igual a 0: "
LEIA n
// variavel fator inicializada com o valor de 1
fator = 1
// variavel i inicializada com o valor de 1
i = 1
SE n = 0 ou n = 1
	ESCREVER fator
	FIM
SENÂO
ENQUANTO i < n FAÇA
	fator = fator * i
	// incrementa em 1 a variavel "i"
        i = i + 1
FIM_ENQUANTO
ESCREVER fator
FIM
```

### Teste de mesa 

|  Entrada  |   Saída  |
|    ---    |    ---   | 
|     4     |    24    |
|     6     |   720    |










### Questão 6 - Geração da sequência de Fibonacci 

Gerar e imprimir os n primeiros termos da sequência de Fibonacci, onde n ≥ 1. 
Os primeiros termos são: $0, 1, 1, 2, 3, 5, 8, 13, \dots. Cada termo, além dos dois primeiros, é derivado da soma dos seus dois antecessores mais próximos.

#### Descrição geral do algoritmo

1. Obter o número de termos $n$, onde $n \geq 1$;
2. Inicializar os dois primeiros termos da série nas variável $a$ e $b$ com 0 (zero);
3. Iterar o valor de $n$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Imprimir o termo inicial $a$ (instrução para exibir a sequência ao atualizar a variável $a$);
    - Somar os termos $a$ e $b$ na variável $termo_atual$;
    - Atribuir a variável $a$ o valor da variável $b$;
    - Atribuir a variável $b$ o valor da variável $termo_atual$.

### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[a = 0]
C --> D[b = 1]
D --> E[[i=1 ATÉ n PASSO 1]]
E --"i > n"--> J([FIM])
E --"i=1,2,...,n"--> F{{a}}
F --> G[termo_atual = a + b]
G --> H[a = b]
H --> I[b = termo_atual]
I --LOOP--> E 
```

### teste de mesa:
```
| it | n  | a  | b  | i  | saída | termo_atual = a + b | a = b | b = termo_atual |
| -- | -- | -- | -- | -- | --    | --                  | --    | --              |
| 1  | 5  | 0  | 1  | 1  | 0     | 0 + 1 = 1           | 1     | 1               |
| 2  | 5  | 1  | 1  | 2  | 1     | 1 + 1 = 2           | 1     | 2               |
| 3  | 5  | 1  | 2  | 3  | 1     | 1 + 2 = 3           | 2     | 3               |
| 4  | 5  | 2  | 3  | 4  | 2     | 2 + 3 = 5           | 3     | 5               |
| 4  | 5  | 3  | 5  | 5  | 3     | 3 + 5 = 8           | 5     | 8               |
```

### pseudocodigo
```
DECLARE  limite, anterior, atual, proximo INTEIRO
ESCREVA("digite o limite da sequencia de fibonacci: ")
   LEIA(limite)
   // variaveis anterior e atual declaradas como 0 e 1 respectivamente
   anterior <- 0
   atual <- 1
   // Exibe as mensagens para entrada de variaveis como dados
   ESCREVA(anterior)
   ESCREVA(atual)
   // realizará a operaçao enquanto o comando "enquanto" for verdadeiro
   ENQUANTO (atual + anterior <= limite) FACA
       proximo <- atual + anterior
       ESCREVA (proximo)
       anterior <- atual
       atual <- proximo
   fimenquanto

```

### Questão 7 - Inversão dos dígitos de um número inteiro 

Implemente e teste um algoritmo para inverter a ordem dos dígitos de um número inteiro positivo.

#### Descrição geral do algoritmo

1. Obter o número inteiro positivo $num$ a ser invertido;
2. Inicializar a variável com 0 (zero);
3. Enquanto o número for maior que zero ($num > 0$), faça repetidamente:
    - Calcular o último dígito do número na variável $digito$;
    - Adicionar o dígito ao número invertido;
    - Remover o último dígito do número original $num$; 
4. Exibir o número invertido.

### Fluxograma 

```mermaid
flowchart TD
a([Início]) --> b{{Digite um númmero positivo: }}
b --> c[/num/]
c --> d{num > 0}
d --false--> h{{invertido}}
h --> i([Fim])
d --loop--> e["digito = num % 10"]
e --> f[invertido = invertido * 10 + digito]
f --> g[num = num / 10]
g --> d
```

#### Pseudocódigo 

```

```
#### Teste de mesa 

|   Entrada    | Número invertido |
|      --      |        --        | 
| 123          | 321              | 
| 398472       | 274893           |
| 1001         | 1001             |








