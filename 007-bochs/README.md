#  Bochs

|本期版本|上期版本
|:---:|:---:|
|`2.7`
`Fri Oct  8 10:30:48 CST 2021` | -



## display_library


```
display_library: sdl2					# macOS
display_library: x, options="gui_debug"
```

## macOS

```
brew install bochs
```



## Debug

* `s`: 单步执行
* `b`: 断点
* `c`: 持续执行
* `r`: 显示通用寄存器的内容
* `sreg`: 显示段寄存器
* `creg`: 显示控制寄存器
* `xp`: 显示指定物理内存的内容
* `q`: 退出
* `n`: 自动完成循环过程， 并在循环体外的下一条指令前停住 / rep、loop
* `u`: 反汇编，第一个参数是跟在 / 后面的数字，指定反汇编出多少条指令；第二个参数用于指定一个内存地址
* `info eflag`: 显示标志寄存器的状态, 标志名称是小写的，说明该标志位是 0; 否则改标志位的状态为 1
* `print-stack`: 查看栈

<img src="xp-1.png" />
<img src="xp-2.png" />

**Ref**

* 5.9.2 Bochs 下的程序调试入门 -  《x86汇编语言 - 从实模式到保护模式》
* 6.12 本章程序的调试 - 《x86汇编语言 - 从实模式到保护模式》
* 7.6.2 在调试过程中查看栈中内容 - 《x86汇编语言 - 从实模式到保护模式》
* 3.4 bochs 调试方法 - 《操作系统真象还原》
* [「Coding Master」第12话 如何正确的调试汇编程序](https://www.youtube.com/watch?v=EJgdGTAixVg&list=PLLBMaJy_MOpM2xUPbjSBSib7hUUaaEGa6&index=14)


## 2.6.11

> `20.04`


```bash
sudo apt-get install -y bochs bochs-x

# 可选
sudo apt-get install -y vagbios bximage
```

> Bug

* [`https://www.bilibili.com/video/BV1b44y1k7mT?p=2`](https://www.bilibili.com/video/BV1b44y1k7mT?p=2)
* [Fixed deadlock in GTK debugger gui pointed out in SF patch](https://sourceforge.net/p/bochs/code/14068/)



## 2.7


## vector must be within idt table limits

* `https://sourceforge.net/p/bochs/bugs/1355/`

```bash
BIOS-bochs-latest is not expected to work with 386 model.
This is why we keep the BIOS-bochs-legacy image as well.
```


> `22.04`

依赖

```bash
# vagrant
apt-get install -y build-essential libx11-dev xorg-dev libgtk2.0-dev
```


源码编译

```bash
wget https://nchc.dl.sourceforge.net/project/bochs/bochs/2.7/bochs-2.7.tar.gz
tar -zxvf bochs-2.7.tar.gz
cd bochs-2.7
./configure --enable-debugger --enable-debugger-gui
make
sudo make install
```


## Misc

创建磁盘

```bash
bximage -mode=create -hd=16M -q master.img # 2.6.11
bximage -func=create -hd=16M -q master.img # 2.7
bximage -func=create -fd=1.44M -q a.img	# 软盘
```

镜像写入磁盘

```bash
nasm hello.asm -o hello.bin
dd if=hello.bin of=master.img bs=512 count=1 conv=notrunc
```




## 自动打一个断点

> [`https://www.bilibili.com/video/BV1b44y1k7mT?p=4&spm_id_from=pageDriver`](https://www.bilibili.com/video/BV1b44y1k7mT?p=4&spm_id_from=pageDriver)

需要在配置开启

```
magic_break: enabled=1
```

```nasm
xchg bx, bx
```

## Ref

* [https://bochs.sourceforge.io/](https://bochs.sourceforge.io/)
* [http://nongnu.org/vgabios/](http://nongnu.org/vgabios/)
* [Bochs简易教程](http://www.edu2act.cn/article/bochsjian-yi-jiao-cheng/)
* [自己动手写操作系统（一）](https://blog.csdn.net/weixin_51760563/article/details/119713850)


