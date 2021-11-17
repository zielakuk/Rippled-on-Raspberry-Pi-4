Download ubuntu mate image for RasberryPi 4: 

```
https://releases.ubuntu-mate.org/focal/arm64/ubuntu-mate-20.04.1-desktop-arm64+raspi.img.xz
```


Download rasberry imager:

```
https://downloads.raspberrypi.org/imager/imager_latest.exe
```


z poziomu imaginer
wybierz system > use custom > lokalizacja sciagnietego obrazu>Write

włóż karte do Rasberry Pi 4>uruchom rasberry 
zfinalizuj instalacje 


sudo apt-get update && sudo apt-get upgrade -y

sudo apt install cmake

sudo apt-get install libboost-all-dev

sudo apt-get install libssl-dev

sudo apt install git


wget https://boostorg.jfrog.io/artifactory/main/release/1.75.0/source/boost_1_75_0.tar.gz

tar xvzf boost_1_75_0.tar.gz

cd boost_1_75_0

./bootstrap.sh

./b2 -j 4

export BOOST_ROOT=/home/sev/boost_1_75_0

source ~/.profile

git clone https://github.com/ripple/rippled.git

cd rippled

git checkout master

mkdir my_build

cd my_build

-wylaczyc przegladarke oraz wszystkie okna poza terminalem 

cmake -DCMAKE_BUILD_TYPE=Debug -Dstatic=OFF ..

cmake --build .



