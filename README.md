

Rippled on Raspberry Pi 4
===



Download ubuntu mate image for Raspberry Pi 4: 

```
https://releases.ubuntu-mate.org/jammy/arm64/ubuntu-mate-22.04-desktop-arm64+raspi.img.xz
```


Download rasberry imager:

```
https://downloads.raspberrypi.org/imager/imager_latest.exe
```


Raspberry Imager: 


Choose OS > Use Custom > ubuntu-mate-20.04.1-desktop-arm64+raspi.img.xz > Write


Now you have your Ubuntu SD card. Before going on, make sure your Pi is off and insert this SD card. This is what the Pi uses to load all the software you’re about to use. 


Turn on the Rasberry and Follow the instruction to finalize installation.



#### Open a Terminal





```
sudo apt-get -y install git pkg-config protobuf-compiler libprotobuf-dev libssl-dev wget build-essential
```

```
sudo apt install cmake
```

```
sudo apt install libprotoc-dev
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

#### Make sure you enter the right "user_name" for example: "export BOOST_ROOT=/home/sev/boost_1_75_0" 

 
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
```

```
cmake -Dstatic=OFF -DCMAKE_BUILD_TYPE=Debug .. 
```

```
cmake --build .
```


It will take a while.  This may take about two hours. 



 Configure rippled
 ===           
 
 ```
 cd ..
 ```
 
``` 
mkdir -p ~/.config/ripple
cp cfg/rippled-example.cfg ~/.config/ripple/rippled.cfg
```

### make changes to the file: .config/ripple/rippled.cfg

-Set the [node_db]'s path to the location where you want to store the ledger database.

-Set the [database_path] to the location where you want to store other database data. (This includes an SQLite database with configuration data, and is typically one level above the [node_db] path field.)

-Set the [debug_logfile] to a path where rippled can write logging information

```
cp cfg/validators-example.txt ~/.config/ripple/validators.txt
```

### Run rippled

```
cd my_build 
```

```
./rippled
```

## " crawl , walk , run "
