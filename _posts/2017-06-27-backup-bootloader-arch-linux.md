---
layout: post
title: Backup Bootloader Arch Linux
date: '2017-06-27 20:46'
tags:
  - arch linux
---

I have a big plan for my old laptop. So I need to backup entire `root` partition. Of course I need to backup my `bootloader`, too. In this articel, I will write how to backup `bootloader` only.

I did this in my Arch Linux machine, but I'm pretty sure this is relevant to another gnu/linux distro. I must warn you, that I not yet try to restore from this backup procedure.

Here what i did:
1. Open my `gnome-terminal`
2. Issue this command:
```shell
sudo dd if=/dev/sda of=/home/sumarsono/bootloader_arch_sumar bs=446 count=1
```
Here the output:
```shell
[sudo] password for sumarsono:
1+0 records in
1+0 records out
446 bytes copied, 0,000302793 s, 1,5 MB/s
```

Done

Why `bs=446`? You can found the information [here](https://en.wikipedia.org/wiki/Master_boot_record#Sector_layout)

At last but not least, Sorry for my bad english.
