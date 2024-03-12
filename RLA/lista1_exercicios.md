
# UNIFOR
**Disciplina** raciocinio logico algoritmico <BR>
**Orientador** prof. Ricardo Carubbi

## lista 1 de exercicios

### exercicio 3
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um numero inteiro e positivo é par ou impar.

### fluxograma
```mermaid
flowchart TD
a([inicio]) --> b{{digite um numero:}}
b --> c[/numero/]
c --> d{numero > 0}
d --false--> e{{o numero deve ser positivo!}}
e --> j
d --true-->f[resto = numero % 2]
f --> g{resto == 0}
g --false--> h{{o numero é impar!}}
g --true--> i{{o numero é par!}}
h --> j([fim])
i --> j
```
### pseudocodigo

```
ALGORITMO verifica_par_impar
DECLARE numero, resto INTEIRO
ESCREVA "digite um numero : "
LEIA numero
SE numero >= 0 ENTAO
		resto = numero % 2
		SE resto == 0 ENTAO
				ESCREVA "o numero é par"
		SENAO
					ESCREVA "o numero é impar!"
SENAO							
			ESCREVA "o numero deve ser positivo"
FIM_ALGORITMO
```

# UNIFOR
**DISCIPLINA**  RECIOCINIO LOGICO ALGORITMICO
**ORIENTADOR** Ricardo Carubbi
## lista de exercicios 2
### exercicio 1 
calcule a media de quatro numeros inteiros

### pseudocodigo
```
ALGORITMO calcular_media
DECLARE n1, n2, n3, n4, media INTEIRO
ESCREVA "Digite sua primeira nota: "
LEIA n1
ESCREVA "digite sua segunda nota: "
LEIA n2
ESCREVA "digite sua terceira nota: "
LEIA n3
ESCREVA "digite sua quarta nota: "
LEIA n4
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



### pseudocodigo
### exercicio numero 5
calcule o quadrado de um numero

```
ALGORITMO calcular_quadrado
DECLARE numero, quadrado INTEIRO
ESCREVA "digite um numero"
LEIA numero
quadrado <-- numero * numero
ESCREVA "o quadrado de ", numero, " é: ", quadrado
```

### fluxograma
```mermaid
flowchart TD
a([inicio]) --> b{{digite um numero:}}
b --> c[/numero/]
c --> d[quadrado <-- numero * numero]
d --> e[/quadrado/]
e --> f([fim])  
```
### exercicio numero 2
Leia uma temperatura dada na escala Celsius (C) e imprima o equivalente em Fahrenheit (F)
### pseudocodigo
```
ALGORITMO converter_C_F
DECLARE c, f REAL
ESCREVA "digite a temperatura em fahrenheit: "
LEIA f
c <-- 5/9 * (f - 32)
ESCREVA "a temperatura em celsius é: ", c)
```
