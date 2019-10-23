# Linux 0.11 Lab

> **This repository stores the source code of Linux 0.11. The complete experimental environment is in oslab.tar.gz. The environment is mainly from shiyanlou.**

> **这个仓库存放的是Linux 0.11的源代码，完整的实验环境在oslab.tar.gz中，环境主要来源于实验楼**

## Get start

我的实验环境在ubuntu18.04中，其它版本应该也同理，但是编译Linux 0.11内核需要低版本的gcc，所以需要先安装gcc-3.4.

- #### *依次执行下面的命令，来安装gcc-3.4*

```cmd
wget http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/gcc-3.4-base_3.4.6-6ubuntu3_amd64.deb

sudo dpkg --force-depends -i gcc-3.4-base_3.4.6-6ubuntu3_amd64.deb


wget http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/gcc-3.4_3.4.6-6ubuntu3_amd64.deb

sudo dpkg --force-depends -i gcc-3.4_3.4.6-6ubuntu3_amd64.deb 


wget http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/cpp-3.4_3.4.6-6ubuntu3_amd64.deb

sudo dpkg --force-depends -i cpp-3.4_3.4.6-6ubuntu3_amd64.deb 

 
wget http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/g++-3.4_3.4.6-6ubuntu3_amd64.deb

sudo dpkg --force-depends -i g++-3.4_3.4.6-6ubuntu3_amd64.deb

 

wget http://old-releases.ubuntu.com/ubuntu/pool/universe/g/gcc-3.4/libstdc++6-dev_3.4.6-6ubuntu3_amd64.deb

sudo dpkg --force-depends -i libstdc++6-dev_3.4.6-6ubuntu3_amd64.deb
```

- #### *实验还需要as86、ld86，如果没有的话也需要进行安装，as86、ld86在bin86包中*

```
sudo apt install bin86
```

- #### 编译内核

进入linux-0.11文件夹，执行make命令即可，会生成Image文件。

- #### 启动bochs

在源目录下，执行./run脚本即可启动Bochs


## Possible problems

在编译内核的时候，可能会出现两个错误

- #### 缺少libSM.so.6

```
./bochs/bochs-gdb: error while loading shared libraries: libSM.so.6: cannot open shared object file: No such file or directory
```

安装对应的32位库即可
```
sudo apt install libsm6:i386
```

- #### 缺少libXpm.so.4

./bochs/bochs-gdb: error while loading shared libraries: libXpm.so.4: cannot open shared object file: No such file or directory

安装对应的32位库即可
```
sudo apt install libxpm:i386
```
