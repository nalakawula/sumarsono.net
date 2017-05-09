---
layout: post
title: "Memperbaiki Touchpad Error di Fedora"
date: 2017-04-27 20:44:40
---

Beberapa waktu yang lalu, saya jenuh dengan **GNOME**. Oleh sebab itu saya memasang **PLASMA**.
Namun apa daya, itu hanya pelarian sesaat. Akhirnya saya memutuskan untuk membuang plasma dan kembali ke gnome.

Proses balikan ini tidak berjalan mulus, setelah saya remove plasma kemudian set `gdm` over `sddm` kemudian reboot, startx gagal start. Hal ini disebabkan karena komponen gnome ada yang hilang terbawa plasma yang saya buang. Okelah tidak apa-apa, saya install gnome lagi. Kemudian reboot dan jreng masuk ke Desktop. Senangnya, bisa balikan ke gnome.

Namun ternyata, cobaan untuk balikan masih ada. Semua lancar ketika di 	`wayland` session, namun karena saya belum sreg, saya switch ke `Xorg` session. Disini masalah muncul lagi, Touchpadnya hanya bisa klik kanan dan klik kiri, tidak bisa move kursor. *WTF* dalam hati.

Sudah pusing, saya putuskan cari solusi di pegelinux. Disana, disarankan untuk memasang `Xorg-libinput` karena diduga paket itu belum terpasang. Hmmm masuk akal, oke saya pasang di fedora dengan cara:
```shell
sudo dnf install xorg-x11-drv-libinput
```

dan jreng, bisa. Wow, awesome. :laughing:

Terima kasih pegelinux..... :+1: