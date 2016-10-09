# ES2016_14353352 DOL开发环境配置

## 1.将3个压缩包拷贝到虚拟机中
##### *dol_ethz.zip*
##### *jdk-8u40-linux-x64.gz*
##### *systemc-2.3.1.tgz*

## 2.在虚拟机中运行下面几个指令，添加一些必要的环境
#### $	sudo apt-get update
#### $	sudo apt-get install ant
#### $ 	sudo apt-get install openjdk-7-jdk
#### $	sudo apt-get install unzip

## 3.解压文件
*新建dol的文件夹*
#### $	mkdir dol
*将dolethz.zip解压到 dol文件夹中*
#### $	unzip dol_ethz.zip -d dol
*解压systemc*
#### $	tar -zxvf systemc-2.3.1.tgz

## 4.编译systemc
*解压后进入systemc-2.3.1的目录下*
#### $	cd systemc-2.3.1
*新建一个临时文件夹objdir*
#### $	mkdir objdir
*进入该文件夹objdir*
#### $	cd objdir
*运行configure*
#### $	../configure CXX=g++ --disable-async-updates
*编译*
#### $	sudo make install
*回到根目录查看目录*
#### $ cd ..        
#### $ ls
*记录当前工作路径*
#### $	pwd

## 5.编译dol
*进入dol*
#### $	cd ../dol
*修改build_zip.xml文件*
#### 将pwd的路径写入文件中
*编译*
#### $	ant -f build_zip.xml all

## 6.运行实例测试
####  $ cd build/bin/main
####  $ ant -f runexample.xml -Dnumber=1
