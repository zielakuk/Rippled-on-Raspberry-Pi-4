sciagamy obraz ubuntu mate 
```
https://releases.ubuntu-mate.org/focal/arm64/ubuntu-mate-20.04.1-desktop-arm64+raspi.img.xz
```


sciagamy imaginera 

```
 https://downloads.raspberrypi.org/imager/imager_latest.exe
```

z poziomu imaginer
wybierz system > use custom > lokalizacja sciagnietego obrazu>Write

włóż karte do Rasberry Pi 4>uruchom rasberry 
sfinalizuj instalacje 

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
  
  
  
