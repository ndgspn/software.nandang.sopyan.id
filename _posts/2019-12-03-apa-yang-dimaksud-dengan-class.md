---
layout: post
title: Apa yang dimaksud dengan Class?
date: 2019-12-03 00:00:00 +0300
description: Part 1 - Konsep Pemrograman Berorientasi Objek - Apa yang dimaksud dengan Class?
#img: software.jpg # Add image post (optional)
tags: [class,java] # add tag
---

> Tulisan ini diadaptasi dari dokumentasi https://docs.oracle.com/javase/tutorial/java/concepts/class.html
> . Jika ada kesalahan penulisan mohon hubungi admin melalui kolom diskusi.

## Part 2 - Konsep Pemrograman Berorientasi Objek

### Apa yang dimaksud dengan Class?

Dalam dunia nyata, kita sering menemukan banyak objek individu yang semuanya dari jenis yang sama. Sebagai contoh adalah Sepeda. Mungkin ada ribuan sepeda yang ada, semua dalam merk dan model yang sama. Setiap sepeda dibuat dariset blueprint (cetak biru) yang sama dan oleh karena itu mengandung komponen yang sama. Dalam istilah object-oriented, kita menyebut sepeda adalah sebagai instance dari class suatu object. Sebuah class adalah blueprint (cetak biru) dari mana objek individu dibuat.

Sytanx Class Sepeda berikut adalah salah satu kemungkinan implementasi dari sepeda:

{% highlight java %}
public class Sepeda {

    // state/fields dari objek sepeda
    int cadence = 0;
    int kecepatan = 0;
    int gear = 1;

    // method/behavior dari Sepeda
    void ubahCadence(int cadence) {
        this.cadence = cadence;
    }

    void ubahGear(int gear) {
        this.gear = gear;
    }

    void tambahKecepatan(int tambahNilai) {
        kecepatan = kecepatan + tambahNilai;
    }

    void kurangiKecepatan(int kurangiNilai) {
        kecepatan = kecepatan - kurangiNilai;
    }

    void cetakStatus() {
        System.out.println("Cadence:" + cadence + 
        "Kecepatan:" + kecepatan + 
        " Gear:" + gear);
    }
}
{% endhighlight %}

Syntax dari bahasa pemrograman Java diatas mungkin terlihat baru, tapi desain dari class ini adalah berdasarkan pada diskusi kita sebelumnya dari objek Sepeda. Variable/fields cadence, kecepatan, dan gear menggambarkan keadaan/state objek, dan method (ubahCadence, ubahGear, tambahKecepatan, kurangiKecepatan dan lainnya) mendefinisikan interksinya dengan dunia luar.

Kita mungkin telah memperhatikan bahwa class Sepeda diatas tidak mengandung sebuah main method. Itu karena kode diatas bukan kode aplikasi yang lengkap; itu hanya blueprint (cetak biru) untuk sepeda yang mungkin digunakan dalam sebuah aplikasi. Tanggung jawab untuk membuat dan menggunakan objek baru Sepeda dimiliki beberapa class lain dalamaplikasi kita.

Dibawah ini adalah contoh class DemoSepeda yang didalamnya terdapat dua object Sepeda terpisah (sepeda1, sepeda2) dan memanggil method dari objek tersebut:

{% highlight java %}
public class DemoSepeda {
    public static void main(String [] args) {
    // Buat dua objek sepeda yang berbeda

        Sepeda sepeda1 = new Sepeda();
        Sepeda sepeda2 = new Sepeda();

        // panggil method
        // untuk objek-objek tersebut
        sepeda1.ubahCadence(50);
        sepeda1.tambahKecepatan(10);
        sepeda1.ubahGear(2);
        sepeda1.cetakStatus();

        sepeda2.ubahCadence(50);
        sepeda2.tambahKecepatan(10);
        sepeda2.ubahGear(2);
        sepeda2.ubahCadence(40);
        sepeda2.tambahKecepatan(40);
        sepeda2.ubahGear(3);;
        sepeda2.cetakStatus();
    }
}
{% endhighlight %}

Hasil dari tes ini adalah menampilkan hasil akhir dari cadence, kecepatan, dan gear untuk dua objek sepeda:

```
Cadence:50 Kecepatan:10 Gear:2
Cadence:40 Kecepatan:50 Gear:3
```
