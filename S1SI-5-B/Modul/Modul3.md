# Modul 3 - Object-Oriented Basics

Pada pertemuan kali ini, kita akan belajar sedikit tentang dasar-dasar dari konsep Pemrograman Berorientasi Objek atau *Object Oriented Programming*.

## Introduction to Class & Object

Di Pemrograman Berorientasi Objek, Anda perlu mengenal terlebih dahulu konsep *Class* dan *Object*. Sederhananya, *Class* adalah sebuah cetakan atau *template* sedangkan *Object* adalah hasil akhir atau produk dari sebuah *Class*.

Misalnya, terdapat sebuah *Class* bernama `Pegawai`. Dari *Class* tersebut dibuat sebuah *Object* bernama `pegawai1`, `pegawai2`, dst...

Dalam implementasinya, *Class* adalah sebuah tipe data dan *Object* adalah sebuah *variable*. Jadi dengan membuat sebuah *Class* baru, bisa dikatakan Anda membuat sebuah tipe data baru untuk program yang sedang Anda kerjakan.

### UML Class Diagram 📈

Dalam mengerjakan sebuah proyek, biasanya ada lebih dari satu orang yang terlibat dalam pengembangan proyek tersebut. Untuk mempermudah komunikasi dan perencanaan antar *programmer* dibuatlah yang namanya *Class Diagram*. 

*Class Diagram* adalah sebuah diagram yang didesain sebagai pedoman seorang atau sekelompok *programmer* dalam mendesain dan mengimplementasikan sebuah *Class* di program atau proyek yang sedang dikerjakan.

Perhatikan contoh *Class Diagram* berikut:

![img](https://cdn.discordapp.com/attachments/629457937965907979/1031704534059327528/ClassDiagramTemplate.jpg)

**Keterangan:**
- ***Attribute*** atau ***Property*** adalah "Apa saja yang dimiliki oleh *Object* yang dihasilkan dari *Class* tersebut".
- Pada dasarnya ***Attribute*** atau ***Property*** adalah sebuah ***variable***. Anda boleh menggunakan tipe data primitif maupun tipe data kompleks. Contoh tipe data kompleks adalah tipe data atau *Class* yang Anda buat sendiri.
- ***Method*** pada dasarnya adalah ***Function***.
- Di sebuah *Class*, *method* mewakili "Apa saja yang bisa dilakukan oleh *Object* yang dihasilkan dari *Class* tersebut".
- Setiap *Class* wajib memiliki sebuah ***Constructor method***.
- ***Constructor method*** adalah *method* atau *function* yang kita panggil saat kita ingin membuat sebuah *Object* dari *Class* tersebut.

### Aturan Penamaan *Class* 📚

1. Huruf pertama **wajib** menggunakan huruf kapital.
2. Jika nama *Class* terdiri dari lebih dari satu kata, huruf pertama kata berikutnya **wajib** menggunakan huruf kapital.
3. Nama *Class* **wajib** menggunakan kata benda tunggal, **bukan** kata kerja ataupun kata benda jamak.

## Let's Create Our Custom Classes! 🤩

Buatlah sebuah *package* baru dengan format penamaan:
`com.nama.praktikumpbo.pertemuan3.animal`

Di dalam *package* tersebut, buat Java *Class* baru dan beri nama **Animal.java**
```Java
public class Animal {
  // Attributes
  String name;
  int age;
  String color;

  public Animal() {}

  public void showProfile() {
    System.out.println("Name : " + name);
    System.out.println("Age  : " + age);
    System.out.println("Color: " + color);
    System.out.println();
  }
}
```
Seperti yang Anda lihat, *class* di atas tidak memiliki *method* berikut: 
`public static void main(String[] args)`

Ini dikarenakan *class* yang barusan kita buat akan kita gunakan sebagai *template* atau tipe data baru. Sebelumnya, *class-class* yang kita buat, kita gunakan sebagai program utama atau *main program*. Agar program kita bisa dijalankan, kita memerlukan sebuah program utama. Untuk itu, buatlah sebuah Java *Class* baru dan beri nama **Main.java**
```Java
public class Main {
  public static void main(String[] args) {
    // -- Pembuatan Class --
    Animal cat = new Animal();
    Animal dog = new Animal();
    Animal rabbit = new Animal();

    // Mengisi nilai attribute object 'cat'
    cat.name = "Miyu";
    cat.age = 3;
    cat.color = "Black";

    // Mengisi nilai attribute object 'dog'
    dog.name = "Shepard";
    dog.age = 2;
    dog.color = "Brown";

    // Mengisi nilai attribute object 'rabbit'
    rabbit.name = "Snowball";
    rabbit.age = 1;
    rabbit.color = "White";

    // Menjalankan method 'showProfile()' masing-masing object
    cat.showProfile();
    dog.showProfile();
    rabbit.showProfile();
  }
}
```
Lalu jalankan kodenya!

### Constructor with Parameter 🛠

Daripada melakukan pengisian attribute satu per satu seperti di atas, kita bisa melakukan sedikit modifikasi untuk mempermudah kerja kita!

Kembali ke **Animal.java**, lalu tambahkan **Constructor method** baru di kodenya. (**Keterangan:** Anda dapat membuat *method* dengan nama sama tanpa menyebabkan error asalkan *method-method* tersebut memiliki parameter berbeda!)
```Java
public Animal(String name, int age, String color) {
  this.name = name;
  this.age = age;
  this.color = color;
}
```
Lalu kembali ke **Main.java**, lakukan modifikasi ke seluruh isi kodenya hingga hasil akhirnya seperti ini:
```Java
public class Main {
  public static void main(String[] args) {
    // -- Pembuatan Class --
    Animal cat = new Animal("Miyu", 3, "Black");
    Animal dog = new Animal("Shepard", 2, "Brown");
    Animal rabbit = new Animal("Snowball", 1, "White");

    // Menjalankan method 'showProfile()' masing-masing object
    cat.showProfile();
    dog.showProfile();
    rabbit.showProfile();
  }
}
```
Jauh lebih ringkas, bukan? Sekarang jalankan kodenya!

## Public? Private? Protected!? 💢

Di Java, ada yang namanya *Modifier* yang menentukan apakah sebuah *method* atau *attribute* dapat diakses oleh *class* atau *file* lain atau tidak. Terdapat tiga *Modifier* di bahasa Java:
1. **Public:** *Attribute* atau *method* tersebut dapat diakses oleh *class* atau *file* manapun. Simbolnya di *class diagram* adalah `+`.
2. **Private:** *Attribute* atau *method* tersebut hanya dapat diakses oleh *class* atau *file* itu sendiri. Simbolnya di *class diagram* adalah `-`.
3. **Protected:** *Attribute* atau *method* tersebut haya dapat diakses oleh *class* atau *file* yang berada di *package* yang sama. Simbolnya di *class diagram* adalah `#`.

![img](https://cdn.discordapp.com/attachments/629457937965907979/1031714972683735080/OOPPrivatePublic.jpg)

Sebagai *refresher*, mari kita lihat lagi contoh *class diagram* tadi.

![img](https://cdn.discordapp.com/attachments/629457937965907979/1031704534059327528/ClassDiagramTemplate.jpg)

Pada *class diagram* di atas, `var1` dan `var2` memiliki *modifier* ***Private*** sedangkan sisanya memiliki *modifier* ***Public***.

## Let's Set Some Privacy in Our Attributes! 🐱‍👤

Lakukan modifikasi ke *class* **Animal.java** hingga hasil akhirnya terlihat seperti berikut:
```Java
public class Animal {
  // Attributes
  private String name;
  private int age;
  private String color;

  // Constructor 1
  public Animal() {}

  // Constructor 2
  public Animal(String name, int age, String color) {
    this.name = name;
    this.age = age;
    this.color = color;
  }

  // Method untuk menampilkan semua isi attribute
  public void showProfile() {
    System.out.println("Name : " + name);
    System.out.println("Age  : " + age);
    System.out.println("Color: " + color);
    System.out.println();
  }
}
```
Sekarang, coba jalankan **Main.java**-nya!

### Getter & Setter

Mencoba mengakses *private attribute* di *class* lain tentunya akan menghasilkan error. Jika Anda tetap ingin melakukannya, Anda bisa mencoba pendekatan ***Getter & Setter***.

Di **Animal.java**, tambahkan *method-method* berikut:

```Java
public String getName() {
  return name;
}

public void setName(String name) {
  this.name = name;
}

public int getAge() {
  return age;
}

public void setAge(int age) {
  this.age = age;
}

public String getColor() {
  this.color = color;
}
```
Untuk uji coba, tambahkan beberapa kode berikut di **Main.java**
```Java
System.out.println("Dog's name (before): " + dog.getName());
dog.setName("Cheddar");
System.out.println("Dog's name (after) : " + dog.getName());
```
Coba jalankan programnya!

# ☆ Challenge ☆

Buatlah sebuah *package* baru dengan format penamaan sebagai berikut:
`com.nama.praktikumpbo.pertemuan3.challenge`

Lalu buatlah implementasi Java dari *class diagram* berikut:

![img](https://cdn.discordapp.com/attachments/629457937965907979/1031721130538573884/PBO_SI_Library.jpg)

# Tugas! 📝

Sertakan di laporan praktikum kalian jawaban dari soal berikut:

1. Buatlah *package* baru (penamaan bebas) di dalam *package* `pertemuan3`. Anda berada di jalan yang benar jika hasil akhir nama *package* Anda terlihat seperti ini:
`com.nama.praktikumpbo.pertemuan3.package_baru_anda`

2. Di dalam *package* baru tersebut, buatlah minimal satu *class* baru untuk digunakan sebagai *template* atau tipe data baru dan satu *class* **Main.java** untuk menjalankan program Anda nantinya.

**Ketentuan:**
- Nilai *plus* jika Anda membuat dan menyertakan *class diagram* juga di laporan praktikum Anda.
- Anda membuat lebih dari satu *class template*.
- Silakan bekerja sama, tetapi **DILARANG KERAS** melakukan tindakan *copy-paste*. Jika mengerjakan bersama, setidaknya beri sedikit variasi di kode dan laporan Anda! Jika tidak ada, pihak-pihak yang terlibat nilainya akan dibagi tergantung ada berapa pihak yang terlibat.
