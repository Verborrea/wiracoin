# Wiracoin - Mining
Repositorio con las indicaciones para minar la moneda.

## Enlaces:

* Explorer: http://62.210.69.92:3025/
* Mining Pool: http://62.210.69.92:8025/getting_started

## Indicaciones:

Para empezar a minar se necesita de un software especial y utlizar software de UNIX debido a que Windows baneó la mayoría de software para minar. En este caso utilizaremos CPU Miner.

### Instalación de CPU Miner:

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

## Trabajo Futuro:

Lo único restante para que el proyecto sea útil sería la creación y administración de wallets a demanda por parte de los usuarios, para esto es necesario un tiempo bastante largo de compilación que culminará el día de mañana. Una vez obtenido el ejecutable, será subido a este repositorio y cualquier persona podrá crear su wallet y ser parte del block-chain ;)

Gracias por su atención.
