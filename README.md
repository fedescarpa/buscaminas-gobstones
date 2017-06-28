# Buscaminas :triangular_flag_on_post: :bomb:

## Objetivos

¡Hora de hacer nuestro primer juego! Queremos programar el clásico buscaminas (así que si nunca lo jugaste antes te recomendamos que empieces por hacerlo y aprender sus reglas :stuck_out_tongue:) 

¡Pero no tan rápido! Veamos algunos requerimientos mínimos de nuestro juego: 

###  1. Tablero inicial

El juego iniciará con un tablero con _minas_, totalmente _tapadas_: 

![](https://github.com/flbulgarelli/buscaminas-gobstones/raw/master/Captura1.png)

Como ves, vamos a dejar siempre las últimas dos filas del tablero para mostrar estadísticas: la cantidad de _marcas_ (identificadas con banderas) y la cantidad de minas. 

### 2. Un programa interactivo

¿Y qué hace nuestro programa? ¡Dejarnos jugar! La idea es que usando el teclado podamos recorrer el tablero e intentar encontrar las minas sin que exploten. En concreto, el objetivo es que podamos presionar las siguientes teclas: 

* `arriba`, `abajo`, `izquiera`, `derecha`: para permitirnos desplazar en ese sentido;
* `barra espaciadora`: para destapar una celda; (:warning: ¡Cuidado! Si hay una mina va a explotar!)
* `enter`: para colocar una bandera (porque creemos que allí hay una mina :wink:)

Lo que acá vamos a necesitar es entonces no un programa común, sino uno interactivo: 

```gobstones
interactive program {
  INIT -> {
    PrepararTablero()
  }
  K_ARROW_LEFT -> {
    MoverHacia(Oeste)
  }
  K_ARROW_UP -> {
    MoverHacia(Norte)
  }
  K_ARROW_DOWN -> {
    MoverHacia(Sur)
  }
  K_ARROW_RIGHT -> {
    MoverHacia(Este)
  }
  K_SPACE -> {
    DestaparSiNoHayBandera()
  }
  K_ENTER -> {
    PonerOSacarBandera()
    ActualizarContadorBanderasYVolver()
    Gano()
  }
}
```

### 3. Destapando las minas

![](https://github.com/flbulgarelli/buscaminas-gobstones/raw/master/Captura2.png)

### 4. Colocando banderas

![](https://github.com/flbulgarelli/buscaminas-gobstones/raw/master/Captura3.png)

### 5. Ganando el juego

![](https://github.com/flbulgarelli/buscaminas-gobstones/raw/master/Captura4.png)

### 6. ¿Y las bolitas?

![](https://github.com/flbulgarelli/buscaminas-gobstones/raw/master/Captura5.png)


##  Créditos


Este ejercicio está basado en el trabajo de Evelyn Torres, Joaquín Córdova Maruskiewicz, Damián Tapia, Hernán Iñiguez y Jonathan Ibarra.

Ver: https://github.com/sagrado-corazon-alcal/buscaminas-gobstones
