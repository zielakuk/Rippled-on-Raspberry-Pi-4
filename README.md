

Rippled on Rasberry Pi 4
===



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


Turn on the Rasberry and Follow the instruction to finalize installation.



#### Open a Terminal



```
sudo apt-get update && sudo apt-get upgrade -y
```

```
sudo apt-get -y install git pkg-config protobuf-compiler libprotobuf-dev libssl-dev wget build-essential
```

```
sudo apt install cmake
```

```
sudo apt-get install libboost-all-dev
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

#### Make sure you enter the right "user_name" for example: "export BOOST_ROOT=/home/"sev"/boost_1_75_0" 

 
```
export BOOST_ROOT=/home/"user_name"/boost_1_75_0
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
cmake ..
```

```
cmake  -Dstatic=OFF ..
```

```
cmake --build .
```


It will take a while , raspberry can be unstable and slow for long time. Go for a Brendy or Debowe and come back a few h later.  
 - There may be a time when it seems that rasberry is not responding. Don't panic, just leave it running.


 Configure rippled
 ===           
 
 
``` 
mkdir -p ~/.config/ripple
cp cfg/rippled-example.cfg ~/.config/ripple/rippled.cfg
```


```
cp cfg/validators-example.txt ~/.config/ripple/validators.txt
```


