---
layout: post
title: Apa yang dimaksud dengan Object?
date: 2019-12-02 00:00:00 +0300
description: Part 1 - Konsep Pemrograman Berorientasi Objek - Apa yang dimaksud dengan Object?
#img: bicycle-object.png # Add image post (optional)
tags: [Java,OOP,Object] # add tag
---

> Tulisan ini diadaptasi dari dokumentasi https://docs.oracle.com/javase/tutorial/java/concepts/object.html
> . Jika ada kesalahan penulisan mohon hubungi admin melalui kolom diskusi.

## Part 1 - Konsep Pemrograman Berorientasi Objek

### Apa yang dimaksud dengan Object?
Object atau Objek adalah kunci untuk memahami teknologi object-oriented (teknologi berorientasi objek). Lihat disekeliling sekarang dan kita akan menemukan banyak contoh dari real-world object / objek dunia nyata, contoh: anjing, kursi, televisi, sepeda, dan lain-lain.

Objek dunia nyata memiliki dua karakteristik: Mereka semua memiliki state/keadaan dan behavior/perilaku. Anjing mempunyai state/keadaan (nama, warna, jenis, lapar) dan perilaku (menggongong, mengibaskan ekor, dan lainnya). Sepeda juga memilki state (gear saat ini, pedal cadence saat ini, kecepadan saat ini) and perilaku (ubah gear, ubah pedal cadence, mengerem). Mengidentifikasi state dan behavior pada objek dunia nyata adalah sebuah cara yang baik untuk memulai berpikir dalam istilah dari Pemrograman berorientasi objek (Object-oriented programming).

Luangkan waktu sebentar untuk mengamati objek dunia nyata yang ada di area terdekat kita. Setiap objek yang kita lihat, tanyakan pada diri sendiri dua pertanyaan ini: "Apa state/keadaan kemungkinan bisa ada dalam objek tersebut?" dan "Apa kemungkinan behavior/perilaku yang bisa dilakukan objek ini?". Pastikan untuk menuliskan pengamatan kita. Seperti yang kita lakukan, kita akan memperhatikan  bahwa objek dunia nyata berbeda dalam kompleksitas; lampu yang kita milki mungkin hanya memiliki dua kemungkinan state/keadaan (on dan off) dan dua kemungkinan perilaku (nyalakan lampu, matikan lampu), tapi berbeda jika kita memilki sebuah radio yang mungkin mempunyai keadaan/state tambahan(on, off, volume saat ini, stasiun saat ini) dan perilaku (nyalakan, matikan, kencangkan volume, kecilkan volume, mencari stasiun, tune, dan lainnya). Kita juga mungkin memperhatikan bahwa beberapa objek, pada gilirannya juga akan mengandung objek lain. Pengamatan dunia nyata ini semua diterjemahan kedalam dunia pemrograman berorientasi objek.

![Objek dunia nyata](/assets/img/concepts-object.gif){: .center-image }

Software objek secara konsep mirip dengan objek dunia nyata: mereka juga mengandung state/keadaan dan perilaku terkait. Sebuah objek menyimpan keadaannya dalam field (variable dalam beberapa bahasa pemrograman) dan menampakan perilakunya melalui methods(function dalam beberapa bahasa pemrograman). Method beroperasi pada sebuah state objek internal dan berfungsi sebagai mekanisme utama untuk komunikasi objek ke objek (object-to-object communication). Menyembunyikan state internal dan memerlukan semua interaksi untuk dilakukan memlalui sebuah method objek dikenal sebagai data encapsulation -- Prinsip dasar dari pemrograman berorientasi objek.

Kita ambil contoh Sepeda :

![Object Sepeda](/assets/img/concepts-bicycleObject.gif){: .center-image }

Dengan menghubungkan state (kecepatan saat ini, pedal cadence saat ini, dan gear saat ini) dan menyediakan method untuk mengubah state tersebut, object tetap dalam kendali dari bagaimana dunai luar diizinikan untuk menggunakannya. Sebagai contoh, jika sepeda hanya memiliki 6 gear, sebuah method untuk mengubah gear bisa menolak nilai apapun yang kurang dari 1 atau lebih dari 6.

Menggabungkan kode kedalaman objek software individu memberikan sejumlah manfaat:

1. Modularitas, kode sumber untuk sebuah objek bisa di tulis dan dirawat secara independen dari sumber kode objek lain. Sekali dibuat, sebuah objek bisa dengan mudah dilewatkan didalam sistem.

2. Information-hiding/Menyembunyikan Informasi: Dengan menginteraksikan hanya dengan sebuah objek method, detail dari impelmentasi internal objek tersebut tetap tersembunyi dari dunia luar.

3. Code re-use/dapat digunakan kembali: Jika sebuah objek sudah ada (mungkin dibuat oleh developer lain), kita bisa menggunakan objek tersebut dalam program kita. Ini memungkinkan spesialis untuk mengimplementasi/test/debug yang kompleks, task-specific object (tugas khusus), yang kemudian bisa dipercaya untuk dijalankan didalam kode yang kita buat sendiri.

4. Pluggability dan kemudahan debug, jika objek tertentu ternyata bermasalah, kita bisa dengan mudah menghapusnya dari aplikasi kita dan memasang objek lain sebagai penggantinya. Ini adalah analogi untuk memperbaiki masalah mekanik dalam dunia nyata. Jika sebuah baut rusak, kita menggantinya, bukan mengganti seluruh mesin.
