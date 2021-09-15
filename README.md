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

## Primer exemplo

Para comezar imos realizar un exercicio que le dous números flotantes de precisión simple, é dicir, que le dous ```float```
e que devolve a media deles. Para isto o que temos que facer é declarar as variables que imos empregar no inicio do noso ```main```, que
como recordaredes, é a función que se executa sempre nos nosos programas.

A declaración de variables é moi sinxela e faise do seguinte xeito:
```
int main() {
  tipo nome;

  // Código

  return 0;
}
```

No noso caso, como imos empregar variables de tipo float imos declaralas do seguinte xeito:
```
int main() {
  float val1;
  float val2;
  float media;

  // Código

  return 0;
}
```

Ainda que no exemplo que acabamos de definir as variables decláranse igual e sin ningún tipo de problema estas adóitanse declarar agrupadas por
tipo de variable, é dicir, se temos tres variables de tipo ```float``` no noso programa poñémolas separadas por unha ```,```, é dicir, do seguinte
xeito:
```
int main() {
  float val1, val2, media;

  // Código

  return 0;
}
```

Agora que temos xa as varibles que imos empregar para o noso programa o que temos que facer é ler os números e almacenalos nas variables declaradas
previamente, para isto imos empregar a función ```scanf``` que se inclúe na mesma librería que a función de ```printf``` que empregamos no primer tutorial.
No caso que nos atopamos, como imos a ler dous número flotantes de precisión simple temos que empregar ```%f``` dentro do programa para almacenalos nas variables,
isto acádase do seguinte xeito:
```
// Lectura dun número flotante de precisión simple
scanf(" %f", &variable);
```

Como 'tip' para ler os datos por consola é moi recomendable engadir un espacio en branco antes de poñer o ```%``` para vaciar o buffer e evitar así
que se carguen datos que non se esperaban na nosa variable, xa que estos datos poden facer que o noso programa non funcione correctamente.

No caso no que estamos e engadindo esta funcionalidade ao noso código podemos ler os datos introducidos por consola e almacenalos nas variables previamente
declaradas do seguinte xeito:
```
int main() {
  float val1, val2, media;

	// Lectura do dato
	scanf(" %f", &val1);

	// Lectura do dato
	scanf(" %f", &val2);

  // Código

  return 0;
}
```

Unha vez temos os valores introducidos por consola cargados na memoria do noso programa podemos facer con eles o que queiramos, unha boa práctica ao
comezo da nosa andaina pola programación é imprimir os valores que acabamos de inserir no noso programa para ver que a declaración das variables está
feita dun xeito correcto e que non houbo ningún tipo de erro, para isto imos empregar a función ```printf``` dun xeito moi similar a como empregamos
```scanf``` neste código ou como utilizamos esta función no anterior tutorial.

Para imprimir estos valores tan só é preciso facer o seguinte: ```printf("Variable 'val1': %f\n", val1)```. Recoméndase indicar cal é a variable que se
imprime para comprobar que o seu valor é o esperado.

Unha vez temos os datos almacenados nas variables e comprobado que son os datos esperados e que non houbo ningún tipo de erro o que nos toca é calcular
a media dos valores almacenados, para isto o que temos que facer é sumar os valores e dividilos entre dous almacenando o resultado na variable que nos queda sin empregar.
