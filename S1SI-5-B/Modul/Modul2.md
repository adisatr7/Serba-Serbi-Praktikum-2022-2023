# Modul 2 - Java Basics

Pada pertemuan kali ini, kita akan belajar sedikit tentang dasar-dasar dari bahasa pemrograman Java.

## Variables

Di bahasa pemrograman Java, *variable* ada ***banyak sekali*** jenisnya. Pada pertemuan ini, kita hanya akan belajar yang sering dipakai saja, di antaranya adalah sebagai berikut:

 Tipe Data | Data yang dapat diterima     |
-----------|------------------------------|
 int       | Bilangan bulat (tanpa koma)  |
 float     | Bilangan desimal (koma)
 String    | Kata/kalimat (panjangnya bebas)
 char      | 1 digit huruf/angka/simbol
 boolean   | Hanya dapat bernilai `TRUE` atau `FALSE`

Buatlah sebuah Java class baru, beri nama **Variables.java**
```Java
public class Variables {
  public static void main(String[] args) {
    String nama = "Satria Adi Nugraha";
    int usia = 21;
    
    System.out.println("Nama saya: " + nama);
    System.out.println("Usia saya: " + usia + " tahun");
  }
}
```
Lalu jalankan kodenya!

## Input & Output

Bahasa Java tidak secara *native* mendukung inputan user. Untuk itu, kita perlu melakukan *import* dari *Library* lain. Ada banyak *Library* yang dapat kita pakai, tetapi yang akan diajarkan di modul ini adalah *Library* yang cara pakainya paling mudah.

Buatlah Java class baru dan beri nama **Input.java**
```Java
import java.util.Scanner;

public class Input {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.print("Masukkan nama Anda: ");
    String nama = input.nextLine();

    System.out.println("Selamat pagi, " + nama + "!");
  }
}
```
Lalu jalankan kodenya!

## If-Else

Buatlah sebuah Java class baru dan beri nama **Conditions.java**
```Java
public class Conditions {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.print("Masukkan sebuah bilangan: ");
    int bilangan = input.nextInt();
    
    
    if(bilangan > 0) {
      System.out.println(bilangan + " adalah bilangan positif!")
    }
    
    else if(bilangan < 0) {
      System.out.println(bilangan + " adalah bilangan negatif!")
    }
    
    else {
      System.out.println(bilangan + " adalah nol!")
    }
  }
}
```
Lalu jalankan kodenya!

## Loop (For, While, Do-While)

Buatlah sebuah Java class baru dan beri nama **Loop.java**
```Java
public class Loop {
  public static void main(String[] args) {
  
    // For
    for(int i=0; i<10; i++) {
      System.out.println("Looping... (" + i + ")");
    }
    System.out.println("Looping For selesai! \n");


    // While
    int j = 1;
    while(j <= 100) {
      System.out.println("Loading... (" + j + "%)");
      j += 10;
    }
    System.out.println("Looping While selesai! \n");


    // Do-While
    int k = 10;
    do {
      System.out.println("Looping... (" + k + ")");
      k--;
    } while(k > 0);
    System.out.println("Looping Do-While selesai! \n")
  }
}
```
Lalu jalankan kodenya!

### Bonus: Break!

Anda dapat menghentikan sebuah looping yang sedang berjalan (walaupun syarat berhentinya belum terpenuhi) dengan menggunakan `break;`. Sebagai contoh, penulis akan menambahkan `break;` di kode looping `while` di atas.

```Java
    // While
    int j = 1;
    while(j <= 100) {
      System.out.println("Loading... (" + j + "%)");
      j += 10;

      if(j == 50) {
        System.out.println("Udah ah, capek!");
        break;
      }
    }
    System.out.println("Looping While selesai! \n");
```
Lalu jalankan kodenya!

# Tugas!

Buatlah sistem login sederhana. Nilai plus jika:
- Program dapat menerima lebih dari 1 akun login
- User dapat melakukan pendaftaran akun melalui program
- Jika user gagal melakukan login sebanyak 3x, program akan keluar