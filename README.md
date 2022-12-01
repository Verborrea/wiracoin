# Wiracoin - Mining
Repositorio con las indicaciones para minar la moneda.
Por: Alan Monroy Bernedo

## Enlaces:

* Explorer: http://62.210.69.92:3025/
* Mining Pool: http://62.210.69.92:8025/getting_started

## Indicaciones:

Para empezar a minar se necesita de un software especial y utlizar software de UNIX debido a que Windows baneó la mayoría de software para minar. En este caso utilizaremos CPU Miner.

## 1. Obtención de Address:

El objetivo de minar es generar monedas para poder almacenarlas en una cuenta. Es por eso que lo primero es obtener una address. Para esto y demás operaciones (como realizar y ver nuestras transacciones) debemos descargar la wallet. La nuestra está basada en la [Bitcoin Core](https://bitcoin.org/es/descargar) y es posible descargarla desde este [enlace](colocar_enlaceeeee). Es necesario esperar un tiempo y contar con suficiente espacio para la sincronización de bloques. Como la moneda es reciente, el tiempo a esperar es pequeño. Una vez descargado, obtendremos una ventana parecida a esta:

[img_1](imgs/img1)

## 2. Instalación de CPU Miner:

Primero hay que instalar algunas dependencias con el siguiente comando:

    sudo apt install libcurl4-openssl-dev libncurses5-dev pkg-config automake yasm

Luego, descargamos el código fuente del programa:

    git clone https://github.com/pooler/cpuminer.git

Y procedemos a su instalación:

    cd cpuminer
    ./autogen.sh
    ./configure CFLAGS="-O3"
    make

### Minado:

Una vez que contamos con el programa, solamente tenenmos que correr el siguiente comando para minar:

    ./minerd --url=[DIFICULTAD] --user=[WALLET]
    
Para establecer la DIFICULTAD, podemos elegir cualquiera de los 3 URLS definidos en la minig Pool:

* **Diff   8:** `stratum+tcp://62.210.69.92:3025`
* **Diff  32:** `stratum+tcp://62.210.69.92:3050`
* **Diff 256:** `stratum+tcp://62.210.69.92:3275`

En WALLET colocamos nuestra wallet, para propositos de prueba, aquí hay 5 wallets de ejemplo:

    WmCLABx2BkLXNqUSoodvK7UdpX4vCJw9Cg
    WPzeN6HhkxGojsn1mkJik42mqxQR13FeVu
    WguERBhQqpAroEQpinN8kRfJfYYMj7dgLh
    WXLNFrEPsGCK4mUUy6KmD3wmw1uY1aoe2i
    WPGQDCTedXALJ7WUT4NJpuD6TTceGr1LNM

El proceso se mostrará en pantalla y podremos corroborar los nuevos bloques generados mediante el [Explorer](http://62.210.69.92:3025).
