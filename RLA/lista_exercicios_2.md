# UNIFOR
**Nome**: Nome do estudante 
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

### Pseudocódigo
```
1  ALGORITMO sal_Reajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere
3  INICIO
4  // mostra a mensagem para a atribuir um dado a variavel
   ESCREVA "INSIRA SUA PROFISSAO: "
   // atribui a variavel o valor inserido
   LEIA prof
   // mostra a mensagem para a atribuir um dado a variavel
   ESCREVA "INSIRA SEU SALARIO: "
   // atribui a variavel o valor inserido
   LEIA sal
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal
10 CASO CONTRARIO                       // caso 3
11    sal_reaj ← 1.1 * sal
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj
14 FIM
```

### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

### Exercício 01 
Calcule a média de quatro números inteiros dados.

### pseudocodigo
```
ALGORITMO calcular_media
DECLARE n1, n2, n3, n4, media INTEIRO
// mostra a mensagem para a atribuir um dado a variavel
ESCREVA "Digite sua primeira nota: "
// atribui a variavel o valor inserido
LEIA n1
ESCREVA "digite sua segunda nota: "
LEIA n2
ESCREVA "digite sua terceira nota: "
LEIA n3
ESCREVA "digite sua quarta nota: "
LEIA n4
// executa o calculo da media somando os valores inseridos na variavel e dividindo pela quantidade
media <-- (n1 + n2 + n3 + n4) / 4
ESCREVA "sua media é: ", media
```

### fluxograma
```mermaid
flowchart TD
a([inicio]) --> b{{digite 4 numeros}}
b --> c[/n1,n2,n3,n4/]
c --> d[media <-- n1 + n2 + n3+ n4/4]
d --> e{{a media é 'media'}}
e --> f([fim])
```

### Teste de mesa 

| Entrada1 | Entrada2 | Entrada3 | Entrada4 |  Saída   | 
|    --    |    --    |    --    |    --    |    --    | 
|    13    |    24    |    30    |   120    |  46.75   |
|    10    |    20    |    30    |    40    |   25.0   |


### exercicio numero 2
Leia uma temperatura dada na escala Celsius (C) e imprima o equivalente em Fahrenheit (F)
### pseudocodigo
```
ALGORITMO converter_C_F
DECLARE c, f REAL
// mostra a mensagem para a atribuir um dado a variavel
ESCREVA "digite a temperatura em fahrenheit: "
// atribui a variavel o valor inserido
LEIA f
// executará a operaçao requisitada para concluir o algoritmo
c <-- 5/9 * (f - 32)
ESCREVA "a temperatura em celsius é: ", c)
```

### Teste de mesa 

| Entrada | Saída |
|    -    |   -   |
|   10    | 50.0  |
|   36    | 96.8  |

### Exercício 03 
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma 

```mermaid
flowchart TD
a([INICIO]) --> b{{digite um numero:}}
b --> B[/n1/]
B --> c{{digite outro numero:}}
c --> C[/n2/]
C --> d{{"selecione a operação desejada:\n 1 para: Somar(+)\n 2 para: Subtrair(-)\n 3 para: Multiplicar(x)\n 4 para: Dividir(/)\n"}}
d --> e[/opcao/]
e --> f{opcao == 1}
f --false--> g{opcao == 2}
g --false--> h{opcao == 3}
h --false--> i[resultado = n1 / n2]
i --> J{{resultado}}
J --> K([FIM])
f --true--> F[resultado = n1 + n2]
F --> J
g --true--> G[resultado = n1 - n2]
G --> J
h --true--> H[resultado = n1 * n2]
H --> J
```

### Pseudocódigo 

```
Algoritmo Calculadora
DECLARAR n1, n2, opcao, resultado: REAL
INICIAR
// mostra a mensagem para a atribuir um dado a variavel
ESCREVER "digite um numero:"
// atribui a variavel o valor inserido
LEIA n1
ESCREVER "digite outro numero:"
LEIA n2
ESCREVER "selecione a operação desejada:\n 1 para: Somar(+)\n 2 para: Subtrair(-)\n 3 para: Multiplicar(x)\n 4 para: Dividir(/)"
LEIA opcao
SE opcao == 1 ENTAO               // atribui uma condiçao para que o algoritmo seja executado
	resultado = n1 + n2
SENAO
	SE opcao == 2 ENTAO
	resultado = n1 - n2
	SENAO
		SE opcao == 3 ENTAO
		   resultado = n1 * n2
		SENAO
			resultado = n1 / n2
                FIMSE        
        FIMSE
FIMSE
ESCREVER resultado
FIM
```

#### Teste de mesa 

| Entrada1 | Entrada2 | Entrada3 | Saída |
|    --    |    --    |    --    |   -   | 
|    5     |    5     |    1     |  10   |
|    5     |    5     |    2     |   0   |
|    5     |    5     |    3     |  25   |
|    5     |    5     |    4     |   1   |

### Exercício 04

Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma 

```mermaid
flowchart TD
a([INICIO]) --> b{{Digite sua idade: }}
b --> B[/idade/]
B --> c{ 5 <= idade <=7}
c --false--> d{8 <= idade <=10}
d --false--> e{11 <= idade <=13}
e --false--> f{14 <= idade <= 17}
f --false--> G{{categoria: adulto}}
c --true--> C{{categoria: infantil A}}
d --true--> D{{categoria: infantil B}}
e --true--> E{{categoria: juvenil A}}
f --true--> F{{categoria: juvenil B}}
C --> H([FIM])
D --> H
E --> H
F --> H
G --> H
```

#### Pseudocódigo 

```
Algoritmo ClassificaCategoria
DECLARAR idade: INTEIRO
INICIAR
ESCREVA "Digite sua idade:"
LEIA idade
SE 5 <= idade <=7 ENTAO                        // atribui uma condiçao para que o algoritmo seja executado
	ESCREVA "categoria: infantil A"
SENAO
	SE 8 <= idade <=10 ENTAO
	ESCREVA "categoria: infantil B"
	SENAO
		SE 11 <= idade <=13 ENTAO
		ESCREVA "categoria: infantil B"
		SENAO
			SE 14 <= idade <=17 ENTAO
			ESCREVA "categoria: juvenil B"
		FIMSE	SENÃO
	FIMSE			ESCREVA "categoria: adulto"
FIMSE
FIM
```

#### Teste de mesa 

|Entrada| Saída |
|  --   |  --   |
| 15    | categoria: juvenil B|
| 20    |  categoria: adulto  |
