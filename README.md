# Wiracoin - Mining
Repositorio con las indicaciones para minar la moneda.
Por: Alan Monroy Bernedo

## Enlaces:

* Explorer: http://62.210.69.92:3025/
* Mining Pool: http://62.210.69.92:8025/getting_started

## Indicaciones:

## 1. Obtención de Address:

El objetivo de minar es generar monedas para poder almacenarlas en una cuenta. Es por eso que lo primero es obtener una address. Para esto y demás operaciones (como realizar y ver nuestras transacciones) debemos descargar la wallet. La nuestra está basada en la [Bitcoin Core](https://bitcoin.org/es/descargar) y es posible descargarla desde este [enlace](https://drive.google.com/file/d/18aNuo2IvEDA37Qe7_vy6MaNuPdgsn4Us/view?usp=sharing) para la plataforma de Windows. Es necesario esperar un tiempo y contar con suficiente espacio para la sincronización de bloques. Como la moneda es reciente, el tiempo a esperar es pequeño. Una vez descargado y tras su instalación, obtendremos una ventana parecida a esta:

![img_1](https://github.com/Verborrea/wiracoin/blob/main/imgs/img1.jpg?raw=true)

Esta es nuestra wallet, al ejecutarla por primera vez nuestra address será generasa, para visualizarla debemos hacer click en la pestaña **Recibir** y en el botón **Recibir pago**.

![img_2](https://github.com/Verborrea/wiracoin/blob/main/imgs/img2.jpg?raw=true)

Una vez ahí, ya hemos obtenido nuestra dirección. Toda moneda minada con esta dirección estará vinculada directamente con esta. **Es importante guardarla muy bien, ya que una vez perdida, no se podrá recuperar**.

![img_3](https://github.com/Verborrea/wiracoin/blob/main/imgs/img3.jpg?raw=true)

## 2. Instalación de CPU Miner:

Para empezar a minar se necesita de un hardware o software especializado. En este caso utilizaremos CPU Miner.

### Windows

Windows baneó la mayoría de software para minar, así que si no se cuenta con una computadora basada en UNIX, podemos utilizar alguna tecnlogía de máquina virtual como Docker o [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Para el software que presentamos, es recomendada la versión de [Ubuntu 18.04](https://releases.ubuntu.com/18.04/) utlizando la **server install image** para mejor rendimiento.

### Linux

Una vez nos encontremos en nuestra terminal de linux, primero tendremos que instalar algunas dependencias con el siguiente comando:

    sudo apt install libcurl4-openssl-dev libncurses5-dev pkg-config automake yasm

Luego, descargamos el código fuente del programa:

    git clone https://github.com/pooler/cpuminer.git

Y procedemos a su instalación:

    cd cpuminer
    ./autogen.sh
    ./configure CFLAGS="-O3"
    make

## 3. Minado usando CPU Miner:

Una vez que contamos con el programa, solamente tenenmos que correr el siguiente comando para minar:

    ./minerd --url=[DIFICULTAD] --user=[WALLET]
    
Para establecer la DIFICULTAD, podemos elegir cualquiera de los 3 URLS definidos en la minig Pool:

* **Diff   8:** `stratum+tcp://62.210.69.92:3025`
* **Diff  32:** `stratum+tcp://62.210.69.92:3050`
* **Diff 256:** `stratum+tcp://62.210.69.92:3275`

En WALLET colocamos la address previamente generada. Sin embargo, para propositos de prueba, aquí se muestran 5 wallets de ejemplo:

    WmCLABx2BkLXNqUSoodvK7UdpX4vCJw9Cg
    WPzeN6HhkxGojsn1mkJik42mqxQR13FeVu
    WguERBhQqpAroEQpinN8kRfJfYYMj7dgLh
    WXLNFrEPsGCK4mUUy6KmD3wmw1uY1aoe2i
    WPGQDCTedXALJ7WUT4NJpuD6TTceGr1LNM

El proceso se mostrará en pantalla y podremos corroborar los nuevos bloques generados mediante nuestro [Explorer](http://62.210.69.92:3025).
