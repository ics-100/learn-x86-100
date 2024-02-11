# 8086\_bios\_and\_dos\_interrupts


## 将显示模式设置成文本模式(清空屏幕)

> * [`02 hello world_哔哩哔哩_bilibili`](https://www.bilibili.com/video/BV1b44y1k7mT/?p=2&spm_id_from=pageDriver&vd_source=a59b1bbab5886cfdc3ab8370ba039efc) - `13:46`

```asm
; text mode. 80x25. 16 colors. 8 pages.
mov ax, 3
int 0x10
``` 



## Ref

<https://yassinebridi.github.io/asm-docs/8086_bios_and_dos_interrupts.html>