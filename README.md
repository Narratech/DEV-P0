# DEV-P0
Desarrollo de Videojuegos - Práctica 0

Añade la carpeta StarterContent que ofrece Unreal Engine en la carpeta Content. 
También disponible si tienes permiso aquí: https://drive.google.com/file/d/1ece2mzryUjjU-GKg8I7tDDl_OTGqkTdx/view?usp=sharing

## SuperCastle
- [Objetivo](#objetivo)
  * [Victoria](#victoria)
  * [Derrota](#Derrota)
- [Actores](#actores)
  * [El Personaje](#el-personaje)
  * [Pociones](#pociones)
  * [Barriles](#barriles)
  * [Troncos](#troncos)
  * [Cañones](#ca-ones)
  * [Plataformas](#plataformas)
  * [Puertas Falsas](#puertas-falsas)
  * [Esfera Dorada](#esfera-dorada)
- [Niveles](#niveles)
  * [Los Barriles Asesinos](#los-barriles-asesinos)
  * [Los Troncos Mareados](#los-troncos-mareados)
  * [La Pasarela de Jack Sparrow](#la-pasarela-de-jack-sparrow)
  * [Las Plataformas Fantasma](#las-plataformas-fantasma)
  * [El Castillo de Disney](#el-castillo-de-disney)
- [Sonidos](#sonidos)

### Objetivo

El objetivo del juego es pasar por todas las pruebas hasta conseguir la esfera dorada al final del todo.

#### Victoria

La victoria se consigue cuando el jugador coge la esfera dorada que se encuentra dentro del castillo.

#### Derrota

El jugador solo puede morir en el caso de ser golpeado por barriles o balas de cañon. Cuando esto pase, volverá al
inicio del nivel. En el caso de caer al foso, se le ha proporcionado unas rampas para volver al principio de la prueba
en la que se ha caido.

### Actores

#### El Personaje

#### Pociones

Durante el nivel solo podremos coger una de cada y el efecto que tienen sobre el jugador no desaparece en todo el juego.

- **Poción de Velocidad**. Es una cápsula flotante de color amarillo. El personaje duplica su velocidad
al colisionar con ella.
- **Pocion de Salto**. Es una cápsula flotante de color rojo. El personaje multiplica x1.5 su velocidad de salto.

![](./img/yellow-potion.PNG)
![](./img/red-potion.PNG)

#### Barriles

Los barriles son cilindros que caen por la ladera que pertenecen al nivel de **Los Barriles Asesinos**. Estos tienen tamaños aleatorios y *spawnean* de manera aleatoria
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

### Sonidos

- **Power Up**. Se activa al coger alguna de las pociones.
- **Cañón**. Cada vez que un cañón disparece emitirá este sonido.
- **Victoria**. Cuando el jugador coja la **esfera dorada** sonará una melodía que representa la victoria.

### Niveles

#### Los Barriles Asesinos

![](./img/barriles_asesinos.PNG)

#### Los Troncos Mareados

![](./img/troncos_mareados.PNG)

#### La Pasarela de Jack Sparrow

![](./img/pasarela_jack.PNG)

#### Las Plataformas Fantasma

![](./img/plat_fantasma.PNG)

#### El Castillo de Disney

![](./img/castillo.PNG)




