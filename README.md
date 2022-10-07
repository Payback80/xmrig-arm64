# xmrig-arm64 How to compile xmrig statically for arm 64 armv7 & armv8 architectures ENGLISH AND ITALIAN  
I've decided to write this short guide because after a couple of years I've noticed there is still some  confusion on how to build xmrig on arm architectures.

I used as reference [1] the official xmring build page, we will statically link the libraries into the executable so if you have many of the same board you don't have to compile again. A brief article on the differences between dynamic vs. static linking is [2]   

My target machine is a RISC V8 cpu with ubuntu 20.04, the same approach  works on raspi4 with ubuntu image and probably works on raspi3 (that has an armv8 instructions capable cpu but mainly armv7 code, but i don't it have so I can't swear on it) 

create a directory where you want test your build

**mkdir test**
**cd test**

update the repos and install the build tools 

**sudo apt update**
**sudo apt install git build-essential cmake automake libtool autoconf**
download the official xmrig github repo

**git clone https://github.com/xmrig/xmrig.git**
**cd xmrig/scripts**

try to build

**./build_deps.sh && cd ../build**
**cmake .. -DXMRIG_DEPS=scripts/deps**

if error is rised about libssl.so.1.1 you can point here: https://stackoverflow.com/questions/72378647/spl-token-error-while-loading-shared-libraries-libssl-so-1-1-cannot-open-shar to get a grasp about a fix, about GCC i have installed the 9.4 release and it worked. My target is ARM_TARGET=8 (aarch64) , armv7 is=7 but the script should autodetect it   
    
**make -j$(nproc)**

Here there is also the binary I've compiled, if you are ultra lazy and you trust and don't verify you can use it.

If I've helped you and want to send me a tip or donate 10 mins of your hashing power this is one of my monero addresses 84j6VpEMF4yR8k4FyrPpLCRRyugCMd2DS3MSoCSbsnAVjDXmYNu2F6NiqtEZboDh3ZRufULqNqNzRDkXiiYd8CLq89S3rRd

Because this is (at 6/10/2022) the latest version of xmrig, you can mine Raptoreum (RTM) or any ghostrider coin 
https://raptoreum.com/
mining pools you could be interested into
https://miningpoolstats.stream/raptoreum

For a full list of supported algos [3] 

[1] https://xmrig.com/docs/miner/build/ubuntu

[2] https://pediaa.com/what-is-the-difference-between-static-and-dynamic-linking/

[3] https://xmrig.com/docs/algorithms


Ho deciso di scrivere questa breve guida dopo qualche anno perchè ho notato che c'è ancora confusione su come compilare xmrig su architetture arm.

Ho usato come referenza [1] la pagina di compilazione ufficiale di xmrig, linkeremo staticamente le librerie nel binario così se avete diverse schede uguali non dovete compilare di nuovo. Un breve articolo sulle differenze tra linking dinamico vs. statico è qui a [2]

La mia macchina è una RISC ARMV8 cpu con ubuntu 20.04, lo stesso approccio funziona con raspi4 con l' immagine ubuntu e probabilmente funziona su raspi3 (che ha una cpu con istruzioni v8 capable, ma molto codice fatto per la armv7, quindi non posso giurarci)

create una directory dove volete testare e puntateci

**mkdir test**
**cd test**

update dei repos e installate le librerie per la compilazione 

**sudo apt update**
**sudo apt install git build-essential cmake automake libtool autoconf**

scaricate il repo ufficiale di xmrig da github


**git clone https://github.com/xmrig/xmrig.git**
**cd xmrig/scripts**

provate a compilare

**./build_deps.sh && cd ../build**
**cmake .. -DXMRIG_DEPS=scripts/deps**

Se viene sollevata una eccezione su libssl.so.1.1 potete puntare qui: https://stackoverflow.com/questions/72378647/spl-token-error-while-loading-shared-libraries-libssl-so-1-1-cannot-open-shar per avere un' idea della soluzione, per GCC io ho installato la release 9.4 e funziona. Il mio target è ARM_TARGET=8 (aarch64), armv7 è =7 lo script dovrebbe fare l autodetect 

  
    
**make -j$(nproc)**

Qui ci sono i binari che ho compilato, se siete ultra pigri e vi fidate e non verificate potete usarli. 

Se vi ho aiutato e volete mandarmi una mancia o donare dieci minuti del vostro hashing power questo è uno dei miei indirizzi monero 
84j6VpEMF4yR8k4FyrPpLCRRyugCMd2DS3MSoCSbsnAVjDXmYNu2F6NiqtEZboDh3ZRufULqNqNzRDkXiiYd8CLq89S3rRd

Poichè questo (al 6/10/2022) è l'ultima versione di xmrig, potete anche minare Raptoreum (RTM) o altre coin con ghostrider

https://raptoreum.com/
mining pools che vi potrebbero interessare

https://miningpoolstats.stream/raptoreum

Per una lista di tutti gli algoritmi supportati [3] 

[1] https://xmrig.com/docs/miner/build/ubuntu

[2] https://pediaa.com/what-is-the-difference-between-static-and-dynamic-linking/

[3] https://xmrig.com/docs/algorithms
