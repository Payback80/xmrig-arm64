# xmrig-arm64
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
