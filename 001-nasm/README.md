# NASM

|本期版本|上期版本
|:---:|:---:|
`Wed Apr  3 17:10:13 CST 2024` | `Tue Jan  2 10:46:44 CST 2024`

## macOS

> `13.6`

```
brew install nasm
```

## Ubuntu

> `22.04`

```
sudo apt-get update && sudo apt-get install -y nasm
```

### 使用说明

* `man nasm`
* `nasm -h`
* `-f` 指定输出文件的格式
* `-o`: 指定编译后输出的文件名
* `-l`: 输出 `lst` 文件


## Misc

* 咱们只关注 `bin` 和 `elf` 格式就好啦
* `$` 当前行的地址
* `$$` 当前 section 的起始地址
* `section.节名.start`


## Ref

* [https://www.nasm.us/](https://www.nasm.us/)
* [NASM 示例](https://cee.github.io/NASM-Tutorial/)
* 《x86汇编语言 - 从实模式到保护模式》- 3.2 NASM 编译器
