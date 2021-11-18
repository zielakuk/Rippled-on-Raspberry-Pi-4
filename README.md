Download ubuntu mate image for RasberryPi 4: 

```
https://releases.ubuntu-mate.org/focal/arm64/ubuntu-mate-20.04.1-desktop-arm64+raspi.img.xz
```


Download rasberry imager:

```
https://downloads.raspberrypi.org/imager/imager_latest.exe
```


Rasberry Imager: 

Choose OS > Use Custom > ubuntu-mate-20.04.1-desktop-arm64+raspi.img.xz > Write


Now you have your Ubuntu SD card. Before going on, make sure your Pi is off and insert this SD card. This is what the Pi uses to load all the software you’re about to use. 


Go to home/"user_name"/  ( right mouse button > open Terminal ) 


``` 
sudo apt-get update && sudo apt-get upgrade -y
```

```
sudo apt install cmake
```

```
sudo apt-get install libboost-all-dev
```

```
sudo apt-get install libssl-dev
```

```
sudo apt install git
```

```
wget https://boostorg.jfrog.io/artifactory/main/release/1.75.0/source/boost_1_75_0.tar.gz
```

```
tar xvzf boost_1_75_0.tar.gz
```

```
cd boost_1_75_0
```

```
./bootstrap.sh
```

```
./b2 -j 4
```

```
export BOOST_ROOT=/home/sev/boost_1_75_0
```

```
source ~/.profile
```

```
git clone https://github.com/ripple/rippled.git
cd rippled
git checkout master
```

```
mkdir my_build
cd my_build
```

```
cmake -DCMAKE_BUILD_TYPE=Debug -Dstatic=OFF ..
```

```
cmake --build .
```


