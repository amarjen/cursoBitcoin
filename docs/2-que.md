# Lección 2: ¿Que es bitcoin?

En esta lección...

## Objetivos

- Distinguir entre la unidad bitcoin y la red Bitcoin
- Conocer las principales reglas de consenso de bitcoin
- Entender el concepto de *Hash*
- Entender los conceptos de mempool, bloques y blockchain
- Entender los conceptos de nodo y SPV wallet
- Entender el proceso de minería y la importancia del algorítmos PoW

## ¿Qué es bitcoin?

Bitcoin es un sistema de pagos electrónicos, en esencia es solo un programa de ordenador. [@Nakamoto]

Al ejecutar el programa, se conecta a otros ordenadores que tienen el mismo programa a traves de la red por todo el mundo. Esto crea una enorme red de ordenadores que se comunican y comparten información entre sí. A cada  uno de estos ordenadores se le conoce como "nodo". Todo esto para compartir un solo fichero, y a este fichero se le conoce como *blockchain*.

El *blockchain* es un fichero que contiene transacciones. Cualquier puede hacer transacciones e insertarlas en un nodo, y desde aquí se propagará de nodo a nodo hasta que todos tengan una copia. Eventualmente, dicha transacción se registrará en el blockchain.

Pero, hay un problema. Nada impide insertar en la red dos transacciones en conflicto. Por ejemplo, puedes comprar una pizza con una transacción, y crear otra transacción para comprar cerveza usando los mismos bitcoins. Si insertaras una transacción en un ordenador, y otra en otro, parte de la red recibiría la transacción de la pizza primero y la otra parte vería primero la transacción de la cerveza.

Ambas transacciones no pueden grabarse en el fichero, de lo contrario sucedería lo que se conoce como "doble-gasto". Entonces, tenemos una red de ordenadores con transacciones en conflicto, y ningún ordenador esta a cargo. Entonces, ¿como se decide?

Bitcoin resuelve este problema a través de un sistema que se conoce como "minería". En lugar de registrar en el blockchain todas las nuevas transacciones nuevas, estas se van acumulando en una sala de espera de cada nodo que se conoce como "memory pool" o "mempool" para abreviar. Cada nodo tendrá su propio *mempool* de transacciones pendientes de registrar y competirán para intentar registrar un conjunto de transacciones en el blockchain.

La carrera comienza. Cada nodo empieza aplicando una función resumen "hash" a un bloque de transacciones que selecciona de su *mempool*. La competición consiste en intentar lograr primero un número por debajo de un umbral determinado por el nivel de dificultad. Si de aplicar la función hash el número es mayor, se volverá a repetir la operación, y como dado el mismo conjunto de datos el resultado de la función hash será el mismo, para bucar otro valor, se le añade un número arbitrario que se llama **nonce**. Las propiedades matemáticas de los *hash* garantizan que la única estrategia viable en esta carrera es la repetición del algorítmo lo más rápido posible sobre el mismo bloque de transacciones cambiando solo el *nonce* para obtener un resultado distinto, hasta encontrar un valor deseado. Con suerte, si el resultado es menor que el umbral, el nodo que lo consigue "canta bingo", es decir, notifica al resto de la red del hallazgo y recibiendo una recompensa en bitcoin y el bloque de transacciones elegidas se grabarán en el blockchain, repitiendose el proceso nuevamente con nuevas transacciones pendientes.

Por ejemplo, digamos que yo tengo la transacción de la cerveza entrá en un bloque, en ese momento, los nodos expulsarán de sus respectivos mempools la otra transacción de la pizza porque está intentando usar unos bitcoins ya gastados.

Al recibir un bloque nuevo, los nodos empezarán a trabajar en el siguiente bloque, esto implica que el blockchain está contruyendose de forma continua añadiendo nuevos bloques de transacciones aproximadamente cada diez minutos. Como resultado, tenemos un sistema donde cualquiera puede insertar una transacción a la red Bitcoin cuyos nodos trabajarán duramente para intentar añadirlos a un fichero compartido.

Gracias a este mecanismo de minería que previene registrar transacciones de dodble-gasto en el fichero compartido, tenemos un sistema de pagos electrónicos que funciona sobre una red de ordenadores diseminada por todo el mundo que funciona sin un punto central de control.

Esto, queridos amigos, es bitcoin.



## Principales reglas de consenso

- Ajuste de dificultad
	- Cada 2016 bloques. (aprox. 2 semanas)
	

- Retribución por creación de bloque
	- La retribución inicial es de 50 BTC por bloque
	- Cada 210000 bloques (aprox. 4 años), retribución se divide por 2, a este evento se le conoce como "*halving*"
	- La emisión máxima será de aprox. 21 millones de BTC, que se alcanzará aprox. en el año 2140, tras 32 *halvings*.


$$\sum_{i=0}^{32} 210000 \dfrac{50}{2i} \approx 21000000$$

\full_bibliography
