# Primeiros pasos en C
## _Tutorial definitivo para comezar a programar_

<p align="center"> <img width="200" height="200" src="https://avatars.githubusercontent.com/u/87182741?v=4"> </p>

C é unha das linguaxes máis extendidas e unha das máis populares debido á súa 
potencia e velocidade. Neste caso empregarase para comezar a apaixonte andaina 
da programación.

Aprenderemos a ler e imprimir:
- Variables numéricas
- Caracteres
- Cadeas de caracteres
- ✨Magic ✨

Ademais de tratar con:
- Funcións matemáticas
- Funcións de tratamento de caracteres

## Requisitos

- [Ter instalado o compilador seguindo os pasos do anterior tutorial](https://github.com/HackingAllYT/configure-c-compiler "Curso previo")
- Ganas de aprender
- Seguir este tutorial

## Contidos explicados
Seguindo co [anterior tutorial](https://github.com/HackingAllYT/configure-c-compiler "Curso previo"), 
no que explicamos como se compila e como se imprime unha frase predefinida por pantalla, neste imos 
aprender a introducir datos por consola, é dicir, tecleando nós os datos.

Para acadalo imos empregar a función ```scanf``` que, ao igual que ```printf```, atópase na librería
```stdio.h``` que podemos importar no noso programa empregando ```#include<stdio.h>```. Esta función
acepta de dous a N argumentos de entrada, o primeiro deles sempre vai ser o que determina que tipos de
parámetros se van ler, e de aí en diante, as variables que se van a empregar para almacenar os datos.

Antes de nada, que son as variables? As variables son trozos de memoria que reserva o usuario (programador)
para almacenar os datos que quere. Estas variables poden ser de tipo primitivo ou xerados polo usuario 
combinando tipos primitivos. Os tipos primitivos pódense diferenciar, alo menos para comezar, en numéricos
e de texto.

Tipos de datos numéricos:
| Coloquialmente | Declaración no programa | Como se le / imprime |
| ------------- | ------------- | ------------- |
| Número enteiro | ```int``` | ```%d``` ou ```%i``` |
| Número enteiro de 32 bits | ```long``` | ```%ld``` |
| Número flotante (de precisión simple) | ```float``` | ```%f``` |
| Número flotante (de precisión doble) | ```double``` | ```%lf``` |

Tipos de datos de texto:

| Coloquialmente | Declaración no programa | Como se le / imprime |
| ------------- | ------------- | ------------- |
| Letra, un caracter calquera | ```char``` | ```%c``` |
| Cadea de caracteres | ```char str[N]```* | ```%s``` |

*Sendo ```str``` o  nome da variable e ```N``` a lonxitude de caracteres máximo a ler. Hai outras formas de facelo,
mais esta é a máis doada á hora de comezar, xa que si non hai que empregar punteiros.
