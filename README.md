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
```C
int main() {
  tipo nome;

  // Código

  return 0;
}
```

No noso caso, como imos empregar variables de tipo float imos declaralas do seguinte xeito:
```C
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
```C
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
```C
// Lectura dun número flotante de precisión simple
scanf(" %f", &variable);
```

Como 'tip' para ler os datos por consola é moi recomendable engadir un espacio en branco antes de poñer o ```%``` para vaciar o buffer e evitar así
que se carguen datos que non se esperaban na nosa variable, xa que estos datos poden facer que o noso programa non funcione correctamente.

No caso no que estamos e engadindo esta funcionalidade ao noso código podemos ler os datos introducidos por consola e almacenalos nas variables previamente
declaradas do seguinte xeito:
```C
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

Para calcular a media só é preciso que sumemos os valores almacenado nas dúas variables e dividilo entre dous, esta operación defínese igual que se fixera
nunha calculadora manual, é dicir, ```(a + b) / 2``` cambiando 'a' e 'b' polo nome das variables asociando o resultado á variable 'media' que almacena o valor, para almacenar este valor tan só é preciso facer
``` c = (a + b) / 2 ```. Neste caso a operación sería:

```C
media = (val1 + val2) / 2.0;
```

*Dato interesante: Dividimos empregando '2.0' e non '2' para asegurarnos que o resultado da operación é un número flotante, xa que si empregamos '2' e ser un número enteiro pode provocar que o resultado sexa un valor aproximado.

Tras almacenar o resultado na variable tan só queda imprimir o valor e comprobar que este valor que calculou o programa está correcto. Para acadalo o que se fai é empregar a función de 'printf' tal e como empregamos ata agora pero indicando que valor quremos que imprima, para iso temos que mirar a táboa de correspondencias dos tipos de datos e o que temos que empregar para poder escribilo ou lelo.

Isto acádase poñendo este marcador no medio das comillas, no sitio que nos gustaría que se vira o resultado, que pode ir acompañado de texto, e poñendo, separado por comas, as variables que queremos imprimir. No noso caso podemos imprimir algo do estilo:

```C
// Imprimimos o valor resultado
printf("Valor medio: %f\n", media);
```

## Segundo exemplo

Neste exemplo imos a calcular o punto medio dun segmento, este exemplo é moi similar ao anterior, pero temos que ler máis datos polo que imos a ler varios datos empregando un só 'scanf'. Para ler varios datos o que hai que facer é o mesmo que vimos no anterior exemplo, é dicir, poñer dentro das comillas o tipo de valor que queremos ler, neste caso ao ser varios poñémolos un ao lado do outro separados por un espacio.

No noso caso sería algo así (inclúese a declaración de variables e a lectura de ambos pares de puntos):
```C
int main(int argc, char **argv) {
  // Declaración de variables locais
  float valAX, valAY, valBX, valBY, puntoMedioX, puntoMedioY;

  // Información do que queremos
  printf ("Introduza os valores de A: ");
  // Lectura do dato
  scanf(" %f %f", &valAX, &valAY);

  // Información do que queremos
  printf ("Introduza os valores de B: ");
  // Lectura do dato
  scanf(" %f %f", &valBX, &valBY);

  // Código

  return 0;
}
```

Unha vez temos os datos almacenados (podemos comprobar que se gardaron ben cun 'printf' dos valores das variables) aplicamos a fórmula para calcular o punto medio do segmento. Este punto medio calcúlase facendo a media dos puntos A e B separados polas súas compoñentes X e Y.

```C
// Calculamos o punto medio do segmento
puntoMedioX = (valAX + valBX) / 2.0;
puntoMedioY = (valAY + valBY) / 2.0;
```

Unha vez obtemos o resultado imprimímolo por pantalla empregando un formato que nos resulte cómodo para visualizar os datos, por exemplo:
```C
// Imprimimos o valor resultado
printf("Valor medio: [%f, %f]\n", puntoMedioX, puntoMedioY);
```

### Segundo exemplo empregando vectores

Este exercicio podémolo facer empregando un vector de dous elementos para cada un dos puntos e así ter unha variable para cada punto e non ter dúas variables por punto. Ao final o uso de memoria vai ser o mesmo, pero á hora da declaración imos empregar menos nomes de variables.

#### Que é un vector?

Un vector, array ou matriz é unha zona de almacenamento de datos contiguo en memoria que ten os datos ordeados posicionalmente.

Ex de vector de dimensión 4:

| Posición 0 | Posición 1 | Posición 2 | Posición 3 |
|------------|------------|------------|------------|

En C, e na maioría de linguaxes de programación, a primeira posición é a posición 0 e vai ata a lonxitude do array - 1, ao principio é algo confuso mais ten a súa lóxica, como veremos a continuación.

Comeza na posición 0 debido a como se almacenan os datos en memoria, imaxinemos que comeza na posición '0x0000' e un 'int' almacénase en 4 bytes, o primeiro elemento almacénase da posición '0x0000' ata '0x0003' inclusive.

Cando se executa o programa, este calcula as posicións de memoria sabendo a primeira posición na que está almacenada o array e multiplica a posición á que se quere acceder polo número de bytes que ocupa o tipo de datos do que se declarou. Por este motivo, se a conta comezara en 1, este resultado sería erróneo e habería que realizar cálculos adicionais facendo que o rendemento do programa sexa moito menor.

### Como se declara un vector?

Unha vez que xa sabemos que é un vector imos a explicar como se declara. Hai dúas formas principais de declaralos, empregando memoria estática ou dinámica. Se empregamos memoria estática o noso vector vai ter
un tamaño fixo e inmutable, este tamaño determínase cando declaramos a variable. Se empregamos memoria dinámica (verémolo máis a fondo en próximos tutoriais) o tamaño do vector é modificable e este tamaño
declárase cando desexamos (sempre antes de empregalo).

| Memoria    | Declaración | Lectura   |
|------------|-------------|------------|
| Estática   | ```int vector[2];``` | ```scanf(" %d", &vector[0]);``` |
| Dinámica   | ```int *vector = malloc(2 * sizeof(int));``` | ```scanf(" %d", &vector[0]);``` |

No caso de da memoria dinámica é preciso facer a reserva de memoria, xa que si non a facemos o programa acabaría cun 'Segmentation fault', erro que ides a ver máis dunha vez, asegurado.
Ao empregar 'malloc' (hai máis posibilidades para facer esta reserva) hai que liberar a memoria chamando á función ```free``` nas últimas liñas do noso 'main'. Exemplo básico destas notas:

```C
int main() {
  // Declaración e reserva de memoria
  int *vector = malloc(2 * sizeof(int));

  // Lectura do dato
  scanf(" %d", &vector[0]);

  // Imprimimos o valor almacenado
  printf("O número introducido é '%d'\n", vector[0]);

  // Liberamos a memoria
  free(vector);

  return 0;
}
```

### Cambios a realizar para empregar vectores

Para comezar hai que cambiar as declaracións das variables e empregar vectores, no noso caso podemos empregar tres vectores, un para o primer punto, outro para o segundo e o terceiro para
o resultado final. Podemos empregar vecores estáticos ou dinámicos, o máis cómodo neste caso é empregar estáticos, xa que o tamaño destes vectores non vai mudar durante a execución do programa.

```C
int int main(int argc, char const *argv[]) {
  // Declaración das variables
  float puntoA[2], puntoB[2], resultado[2];

  return 0;
}
```

Tras declarar os vectores o único que temos que facer é cambiar onde aparece 'valAX' por 'puntoA[0]' e onde aparece 'valAY' por 'puntoA[1]' e así respectivamente co resto de variables que empregamos
ao longo do programa, xa que antes tíñamos diferentes nomes para cada compoñente dos puntos, e agora temos a mesma variable (vector) en diferentes posicións.

## Terceiro exemplo

Tras ter certos coñecementos acerca de como funcionan os números en C imos a comezar cos caracteres, neste exemplo imos a aprender como se pode ler un caracter, almacenalo e devolvelo empregando as
funcións 'toupper' e 'tolower' que serven para poñer en maiúsculas e minúscalas estos caracteres, respectivamente. Estas funcións inclúense ca librería 'ctype.h'.

Como vimos na táboa inicial de como se len os diferentes tipos de datos, para o caso dos caracteres temos que declarar a variable empregando o tipo de datos 'char'. Como se mostra no seguinte exemplo:

```C
int int main(int argc, char const *argv[]) {
  // Declaración de variables locais
  char letra;

  return 0;
}
```

Unha vez temos declarada a variable na que imos a almacenar o caracter lido temos que solicitarlle ao usuario que nos diga que caracter quere procesar. Para isto empregamos 'scanf' do mesmo xeito
que empregamos anteriormente cos valores numéricos, é dicir, ```scanf(" %c", &letra);```

Poñendo en conxunto as diferentes partes aquí descritas podemos obter un programa que nos imprime a maiúscula e minúscula da letra introducida por terminal que sexa similar ao seguinte:

```C
// Importamos as librerías
#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>

int int main(int argc, char const *argv[]) {
  // Declaración de variables locais
  char letra;

  // Lectura do dato
  scanf(" %c", &letra);

  // Imprimimos o resultado
  printf("A letra maiúscula de '%c' é: '%c'\n", letra, toupper(letra));
  printf("A letra minúscula de '%c' é: '%c'\n", letra, tolower(letra));

  return 0;
}
```

Neste caso en concreto non almacenamos o valor devolto por 'toupper' e 'tolower', xa que se despois non imos a volver a empregar este resultado. No caso de que si precisáramos este valor devolto podíamolo
almacenar nunha variable para poder acceder a este valor cando fose preciso. O cambio sería engadir as variables que almacenan estos caracteres modificados e unha vez lido o caracter que introduce o usuario,
asignarlles un valor.

```C
// Importamos as librerías
#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>

int int main(int argc, char const *argv[]) {
  // Declaración de variables locais
  char letra, minus, maius;

  // Lectura do dato
  scanf(" %c", &letra);

  minus = tolower(letra);
  maius = toupper(letra);

  return 0;
}
```
