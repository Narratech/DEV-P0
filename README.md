# Desarrollo de Videojuegos - Práctica 0: SuperCastle

Se trata de un prototipo básico de videojuego de plataformas 3D en el que controlamos a un personaje que debe alcanzar un trofeo en lo alto de un castillo, teniendo que superar para ello varias pruebas.

La versión original del juego fue creada por Alejandro Villar, que posteriormente fue revisada y completada por Federico Peinado. El código se distribuye bajo la licencia GPL.

El propósito es servir como ejemplo a los alumnos para las demás prácticas de la asignatura.

## Instalación y uso
Todo el contenido del proyecto está disponible aquí en el repositorio, salvo la subcarpeta StarterContent que ofrece Unreal Engine por defecto.
Esta subcarpeta debe incluirse en la carpeta Content. Si se tiene permiso, es posible [descargarla aquí](https://drive.google.com/file/d/1ece2mzryUjjU-GKg8I7tDDl_OTGqkTdx/view?usp=sharing).

Al no estar publicada todavía ninguna versión ejecutable del prototipo, ni enlazado ningún video con las pruebas realizadas, es necesario abrir el proyecto en Unreal Engine y jugarlo desde allí.

## Preproducción
Aunque no hay un enunciado como tal que sirva de punto de partida, la preproducción consistió en el diseño de un juego que plantee pruebas divertidas y un super-castillo final al que hay que escalar para conseguir el trofeo.

El diseño tiene estas secciones:
- [Estética](#Estética)
  * [Gráficos](#Gráficos)
  * [Sonidos](#Sonidos)
- [Dinámica](#Dinámica)
  * [Objetivo](#Objetivo)
  * [Castigo](#Derrota)
- [Mecánica](#Mecánica)
  * [Avatar](#Avatar)
  * [Pociones](#Pociones)
  * [Barriles](#Barriles)
  * [Troncos](#Troncos)
  * [Balas](#Balas)
  * [Plataformas fantasma](#Plataformas)
  * [Puertas falsas](#Puertas)
  * [Trofeo](#Trofeo)
- [Contenido](#Contenido)
  * [Zona 1](#Zona-1)
  * [Zona 2](#Zona-2)
  * [Zona 3](#Zona-3)
  * [Zona 4](#Zona-4)
  * [Zona 5](#Zona-5)

### Estética
El juego usa solamente el contenido de la plantilla Third Person y el de principiantes, simplificando al máximo la composición de la escena, aunque sin tener un aspecto pulido y acabado.

#### Gráficos
El juego usa solamente el contenido de la plantilla Third Person y el de principiantes.

#### Sonidos
No hay música ambiente y los sonidos utilizados son simplemente:
- **Power Up**. Se activa al coger alguna de las pociones.
- **Cañón**. Cada vez que un cañón dispara emitirá este sonido.
- **Victoria**. Cuando el jugador coge el trofeo sonará una fanfarria de victoria.

### Dinámica
La dinámica del juego consiste en superarlo si tardar demasiado tiempo, aunque no hay cronómetro ni límites temporales.

#### Objetivo
El objetivo del juego es pasar por todas las pruebas hasta conseguir el trofeso que se encuentra en lo más alto del castillo.

#### Castigo
El jugador solo puede morir en el caso de ser golpeado por barriles o balas de cañon. Cuando esto pase, volverá al
inicio del nivel. En el caso de caer al foso, se le ha proporcionado unas rampas para volver al principio de la prueba
en la que se ha caido, con lo que es un castigo mucho más leve.

### Contenido
A continuación detallamos el contenido más importante del juego.

#### Avatar
El clásico maniquí de Unreal Engine que se puede mover y saltar.

#### Pociones
Hay dos tipos y solo podremos coger una de cada. Lo bueno es que el efecto que tienen sobre el jugador no desaparece en toda la partida.

- **Poción de velocidad**. Es de color amarillo y permite que el avatar duplique su velocidad al cogerla. 
- **Pocion de salto**. Es de color amarillo y permite que el avatar multiplique por 1.5 su impulso al saltar.

#### Barriles

Los barriles son cilindros de varios tamaños que caen por la rampa que pertenecen a la Zona 1. Estos tienen tamaños aleatorios y *spawnean* de manera aleatoria
en lo más alto de la ladera. Si el personaje es golpeado por un barril, hará la "animación" de *ragdoll* y volverá al inicio
del nivel. Al colisionar, el tronco desaparecerá de la escena.

![](./img/barril.PNG)

#### Troncos

Los troncos son cilindros con una textura de tablas de madera que pertenecen al nivel de **Los Troncos Mareados**. Estos
giran constantemente usando una velocidad de giro aleatoria (en un rango de valores para que su giro tenga sentido) tanto en el eje Y como en el Z.
Si el personaje se queda quieto encima de un tronco, este lo empujará y el jugador caera al foso.

![](./img/tronco.PNG)

#### Cañones

Los cañones se encuentran en el nivel de **La Pasarela de Jack Sparrow**. La funcionalidad de los cañones es disparar balas en un intervalo aleatorio
entre 2 y 4 segundos. Si una bala colisiona con el jugador, tendrá el mismo comportamiento que los barriles, es decir, el jugador entrará en modo *ragdoll*
y la bala desaparecerá de la escena.

![](./img/canon.PNG)

#### Plataformas

Podemos encontrar plataformas en los niveles de **Las Plataformas Fantasma** y **El Castillo de Disney**. En ambos niveles encontraremos plataformas normales,
sin embargo, en el primero de ellos algunas de las plataformas no tienen colisión (se podría decir que son falsas) por los que el jugador caería 
al foso.

![](./img/platform.PNG)

#### Puertas Falsas

Para entrar en el castillo nos encontraremos con 3 puertas. Ninguna de ellas se abre, pero solo una se puede atravesar.

![](./img/door.PNG)

#### Esfera Dorada

La esfera dorada es el premio final. Cuando la consigues se acabaría el juego.

![](./img/esferadorada.PNG)



### Contenido

#### Zona-1

![](./img/barriles_asesinos.PNG)

```mermaid
flowchat TD; 

st=>start:  Comienzo 
e=>end:  fin 
op=>operation:  Mi operación
cond=>condition:  ¿confirmar?

st->op->cond
cond(yes)->e
cond(no)->op
```

```mermaid
graph LR;
    Inicio del avatar-->Cartel, inicio de la rampa;
    Cartel, inicio de la rampa-->Final de la rampa (generador de barriles);;
```

#### Zona-2

![](./img/troncos_mareados.PNG)

#### Zona-3

![](./img/pasarela_jack.PNG)

#### Zona-4

![](./img/plat_fantasma.PNG)

#### Zona-5

![](./img/castillo.PNG)

## Referencias
Fall Guys, de Mediatonic Games.


