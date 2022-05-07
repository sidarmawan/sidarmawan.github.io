---
layout: post
title: "Hapus Aplikasi Bloatware Tanpa root"
author: "Sidar"
categories:
    - Blog
tags:
    - Android
    - Linux
---

<p>Saya akan membagikan catatan pribadi saya, saat menghapus aplikasi bawaan smartphone tanpa root.</p><br>
<p>Pertama kita bahas dulu apa itu <b>Bloatware?</b>.</p><br>
<p>Bloatwware menurut saya adalah kumpulan aplikasi bawaan smartphone yang tidak kita butuhkan dan kita tidak bisa menghapusnya dari pengaturan aplikasi. sehingga aplikasi bloatware sendiri mengkonsumsi memory ram dan memory internal yang dimana semakin kesini aplikasi-aplikasi smartphone semakin besar ukurannya dan semakin banyak mengkonsumsi memory ram oleh karena itu saya igin menghapus aplikasi bloatware tanpa melakukan root pada smartphone</p>
<p>oke langsung saja ke tutoriallnya </p><br>
pada tutorian ini saya menggunakan sistem operasi linux (ubuntu) yang menurut saya sangat mudah dan kebetulan saya menggunakan sistem operasi linux (ubuntu) untuk daily dan kerja.

1. Install adb 
```bash
sudo apt install -y adb
```

2. Aktifkan usb debugging (sesuai smartphone masing)
3. Install aplikasi link2sd dari playstore
4. Hubungkan smartphone ke laptop/pc<br>
ketika ada pesan 
- izinkan akses pencet YA
- izinkan debugging USB? pencet YA
5. Buka terminal jalankan command 
```bash
$ adb device
List of devices attached
IDDEVICE  device
```
![adb-device](/images/adb-device.png)<br>
sampai sini ketika menjalankan adb device sudah muncul list devicenya berarti kita bisa lanjut untuk menghapus aplikasi.
6. Buka aplikasi link2sd untuk mencari nama aplikasi yang akan dihapus, sebagai contoh saya akan menghapus aplikasi cuaca.
![link2sd](/images/link2sd.png)<br>
7. Buka terminal jalankan command
```bash
$ adb shell
SOV39:/ $ 
#SOV39:/ $  pm uninstall -k --user 0 'nama.aplikasi' < contoh
SOV39:/ $  pm uninstall -k --user 0 'com.sonymobile.xperiaweather'
Success
```
<br>
jika muncul pesan succes berarti sudah berhasil menghapus aplikasi. mungkin sekian dulu untuk catatan dari saya semoga bermanfaat. 
