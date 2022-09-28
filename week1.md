# UNIX COMMAND LINE
___
### Introduction to CLI
**Shell** adalah program yang menerima perintah dan akan meneruskan perintah tersebut ke sistem untuk kemudian dijalankan. Sedangkan Command Line Interface (CLI) merupakan shell yang berbasis teks.

Unix command line dipelajari karena perintah-perintah yang digunakan karena Unix bersifat open source dimana hal tersebut menyebabkan banyak developer yang menggunakannya.

Untuk mengakses CLI, pada windows bisa menggunakan **PowerShell** atau Command **Prompt**. Selain itu, pengguna juga bisa menggunakan **GitBash**.

### File Structure
**Filesystem** adalah pengaturan bagaimana file disimpan pada sebuah sistem. Sistem operasi Windows dan Unix menyusun file menggunakan struktur yang mirip seperti tree. Berikut adalah contoh dari susunan penyimpanan file.
```sh
|--Folder1
|--Folder2
|   |----File1
|   |----File2
|--Folder3
```
Berdasarkan contoh di atas, untuk mengakses File1 dan File2 maka pengguna harus melalui Folder2.

### Basic Command
**Melihat Current Working Directory**
Untuk melihat current working directory, command yang digunakan adalah **pwd**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 ~
$ pwd
/c/Users/ASUS
```
**Melihat Isi sebuah directory**
Untuk melihat isi dari sebuah directory, command yang digunakan adalah **ls**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d
$ ls
'$RECYCLE.BIN'             
'Alprog 3 & 21'   
Data    
'MBKM - Skilvul'
```
Berdasarkan contoh di atas, kita bisa melihat bahwa dengan menggunakan command **ls** pada directory d, kita bisa melihat file dan folder yang terdapat disana, yaitu $RECYCLE.BIN, Alprog 3 & 21, Data, dan MBKM - Skilvul.

**Berpindah Directory**
Untuk berpindah directory, command yang digunakan adalah **cd**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 ~
$ cd D:

Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d
$
```
Berdasarkan contoh di atas, bisa kita lihat bahwa dengan menggunakan command cd D: bisa membuat kita berpindah directory ke directory D.

**Melihat Isi files**
Untik melihat sebuah file, terdapat 3 command yang bisa digunakan, yaitu **cat** untuk melihat sebuah file, **head** untuk melihat beberapa line di awal sebuah file, **tail** untuk melihat beberapa line di akhir sebuah file.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul
$ cat 'Pertemuan 4.txt'
```

**Membuat File dan Directory**
Untuk membuat sebuah file, command yang digunakan adalah **touch**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ touch contohfile.txt
```

Untuk membuat sebuah direktori, command yang digunakan adalah **mkdir**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul
$ mkdir contohfolder
```
**Menyalin File dan Directory**
Untuk menyalin file dan Directory, command yang digunakan adalah **cp**. Berikut merupakan contoh cara menyalin file pada folder yang sama.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ cp contohfile.txt hasilcopy.txt
```
Berikut merupakan contoh cara menyalin file dan meletakkannya pada folder yang berbeda
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ cp contohfile.txt /d/
```

**Memindahkan atau Me-rename file dan directory**
Untuk memindahkan file, command yang digunakan adalah **mv**
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ mv contohfile.txt /d
```
Selain untuk memindahkan file, command **mv** juga bisa digunakan untuk mengubah nama file
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ mv hasilcopy.txt baliklagi.txt

Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ ls
baliklagi.txt
```

**Menghapus File dan Direktori**
Untuk menghapus file dan directory, command yang digunakan adalah **rm** dan **rf** untuk force remove.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder
$ rm baliklagi.txt
``` 

---
# GIT & GITHUB DASAR
---
**Git** adalah version control system yang paling sering digunakan oleh developer. Version control adalah sebuah sistem yang merekam perubahan terhadap sebuah file dalam waktu tertentu. Git sangat berguna ketika para developer ingin mengerjakan project secara bersamaan. Hal ini disebabkan semua developer akan memiliki history yang lengkap dari project yang dikerjakan baik itu perubahan yang dilakukan hingga siapa yang melakukan perubahan tersebut.

**Github** merupakan sebuah remote repository yang bisa dibayangkan seperti google drive yang bisa diakses oleh siapa saja. Pengguna bisa mengunggah, mendownload, menambahkan, atau menghapus file.

Git dan Github **penting** digunakan oleh developer karena pada saat bekerja umumnya developer tidak pernah sendiri. Git dan Github akan memberikan kemudahan untuk bekerja dalam sebuah tim dan berkolaborasi antara satu sama lain. Hal ini disebabkan developer tidak perlu copy paste folder aplikasi yang terupdate serta tidak perlu menunggu rekan lainnya menyelesaikan sebuah program terlebih dahulu untuk ikut berkolaborasi pada program tersebut.

**Tahapan** dalam bekerja dengan Git dan Github ada 3, yaitu :
1. Working Directory (membuat file, memodifikasi file, menghapus file)
2. Staging (file yang sudah siap disimpan)
3. Commit (perubahan file yang disimpan)

**Repository** merupakan direktori yang digunakan untuk menyimpan project kita. Satu repository digunakan untuk menyimpan satu project.

Command yang digunakan untuk membuat repository Git adalah *init*. Untuk membuat repository dengan membuat folder / direktori baru maka command yang digunakan adalah sebagai berikut.
```sh
git init project-baru
```
Namun, jika kita sudah memiliki folder untuk project tersebut maka command yang digunakan adalah sebagai berikut.
```sh
git init
```
Berikut merupakan contoh hasil dan inisialisasi Git pada direktori yang sebelumnya sudah ada.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git init
Initialized empty Git repository in D:/MBKM - Skilvul/contohfolder/.git/
```

Untuk melihat **status** file pada git bisa menggunakan command *status*. Berikut merupakan contoh penggunaan command *status*.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.md

nothing added to commit but untracked files present (use "git add" to track)
```
Lalu, setiap kali melakukan perubahan pada sebuah file command yang harus digunakan adalah *add* untuk mengubah untracked file dan unmodified menjadi modified. Command ini akan menjadikan file berada di dalam tahap staging. Berikut merupakan contoh penerapan command add.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git add .

Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.md


Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
```
Untuk melakukan commit sekaligus mempublish pada Github terdapat beberapa step yang harus dilakukan, seperti membuat sebuah repository pada Github, lalu menambahkan config remote pada Git menggunakan command *remote add origin* untuk menghubugnkan repository Github dengan direktori lokal. Berikut merupakan contoh dari penggunaan command tersebut.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git remote add origin https://github.com/utaridyani/writing-presentation.git~
```
Lalu untuk menyimpan perubahan pada version control, command yang diperlukan adalah *commit*. Berikut merupakan contoh penerapan dari command tersebut.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (master)
$ git commit -m "testing commit"
[master (root-commit) 716350d] testing commit
 1 file changed, 1 insertion(+)
 create mode 100644 test.md
```
Untuk mempublikasikan file serta setiap perubahannya pada repository github, command yang diperlukan adalah *push*. Berikut merupakan contoh penggunaan command tersebut.
```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul/contohfolder (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 217 bytes | 217.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/utaridyani/writing-presentation.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```
Untuk melakukan **cloning** repository Github ke lokal, kalian harus mendapatkan link web URL dari repository tersebut terlebih dahulu (jika akan menggunakan Git). URL tersebut dapat ditemukan pada bagian code yang terdapat pada Github.

Setelah itu, kalian perlu menuju lokal direktori yang akan menjadi folder kalian menyimpan atau mengcloning project tersebut. Setelah itu buka git bash pada foler tersebut dan gunakan command *git clone* yang dilanjutkan dengan URL yang sudah kalian dapatkan sebelumnya. Berikut merupakan contoh penggunaan dari command tersebut.

```sh
Utari Dyani@LAPTOP-5CJUBHVQ MINGW64 /d/MBKM - Skilvul (master)
$ git clone https://github.com/tech-4-impact-batch-3/materi.git
Cloning into 'materi'...
remote: Enumerating objects: 52, done.
remote: Counting objects: 100% (52/52), done.
remote: Compressing objects: 100% (44/44), done.
remote: Total 52 (delta 13), reused 44 (delta 5), pack-reused 0
Receiving objects: 100% (52/52), 897.13 KiB | 1.01 MiB/s, done.
Resolving deltas: 100% (13/13), done.
```
Selain menggunakan cara di atas, kalian juga bisa mendownload project tersebut dalam versi zip.

---
# HTML
---
HTML merupakan singkatan dari Hypertext Markup Language. HTML digunakan untuk menampilkan konten pada browser. Beberapa konten yang bisa ditampilkan dengan HTML adalah text, image, video, link, dan lain sebagainya.

HTML merupakan kerangka dari sebuah website dimana HTML hanya bertugas untuk menampilakan konten yang diminta oleh developer. Karena HTML bukan sebuah bahasa pemrograman, HTML tidak bisa dinamis dan mengolah data.

Untuk membuat HTML, terdapat 2 tools yang wajib disiapkan oleh seorang developer, yaitu :
1. Browser
2. Code Editor (pada pembelajaran ini saya menggunakan Visual Studio Code)

**Visual Studio Code** merupakan code editor yang bisa digunakan untuk menulis kode dengan bahasa pemrograman apapun. Visual Studio Code juga merupakan tools yang banyak digunakan komunitas sesama developer. Visual Studio Code memiliki beberapa keunggulan, yaitu bisa digunakan di Windows, Linux, ataupun Mac. Selain itu, Visual Studio Code juga memiliki banyak extentions yang bisa dimanfaatkan untuk mempermudah pekerjaan seorang developer.

Berikut merupakan struktur dasar dari HTML. Jika menggunakan Visual Studio Code dan text file sudah disimpan dengan ekstensi *.html*, kalian cukup mengetik tanda "!" lalu menekan enter untuk menghasilkan struktur ini.
```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

Berikut merupakan contoh HTML yang akan menampikan judul dan sebuah kalimat sederhana.
```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <title>Latihan HTML</title>
    <p>Ini adalah HTML untuk latihan</p>
    
</body>
</html>
```

HTML memiliki beberapa tag seperti beberapa contoh berikut :
1. head
2. body
3. p
4. br
5. img
6. video
7. table

Selain tag di atas, HTML juga memiliki hal yang disebut sebagai **Semantic HTML**, yaitu penggunaan elemen HTML sesuai dengan yang dibutuhkan. Beberapa contoh dari Semantic HTML adalah sebagai berikut :
1. header
2. footer
3. section
4. nav

Berikut merupakan contoh dari HMTL yang sederhana dan telah menerapkan Semantic HTML.
```sh
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Latihan</title>

  </head>
  <body>
    <h1>Hai.. Im <span>Utari</span></h1>
    
    <div class="deskripsi">
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa ipsam
        eligendi esse. Sequi officiis repellendus corporis itaque, et odit,
        expedita quae corrupti, aut labore totam dicta neque quibusdam harum
        numquam.
      </p>
      <img
        src="https://imgx.gridoto.com/crop/0x0:0x0/750x500/photo/2021/11/30/avanza-13-e-mt-astrajpg-20211130095920.jpg"
        alt="foto"
        width="300"
      />
    </div>

    <div class="deskripsi-flex">
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa ipsam
        eligendi esse. Sequi officiis repellendus corporis itaque, et odit,
        expedita quae corrupti, aut labore totam dicta neque quibusdam harum
        numquam.
      </p>
      <img
        src="https://imgx.gridoto.com/crop/0x0:0x0/750x500/photo/2021/11/30/avanza-13-e-mt-astrajpg-20211130095920.jpg"
        alt="foto"
        width="300"
      />
    </div>

  </body>
</html>
```

Untuk menjalankan dan melihat hasil dari HTML yang telah kita buat, Visual Studio Code memiliki sebuah extention yang mampu menampilkan HTML yang telah kita buat pada browser dan mengaplikasikan setiap perubahannnya secara realtime. Extention tersebut adalah **Live Server**

Cara menggunakan Extention Live Server sangat mudah, kalian hanya perlu menginstallnya pada bagian extention pada Visual Studio Code. Lalu jika kode HTML ingin kalian jalankan, kalian hanya perlu mengklik "live server" pada bagian kiri bawah tampilan VSCode untuk menjalankan HTML kalian.

Setelah menyelesaikan project HTML, kita bisa lanjut ke tahap **Deploy**. Deploy adalah sebuah proses untuk menyebarkan aplikasi yang sudah kita kerjakan agar bisa digunakan oleh orang lain. Karena yang kita kerjakan pada pembelajaran kali ini adalah HTML atau Web App, maka kita perlu mendeploynya ke server.

Tools yang akan kita gunakan untuk mendeploy project HTML ini adalah **Netlify**. Adapun langkah-langkah untuk mendeploy project pada Netlify adalah sebagai berikut :
1. Masuk ke Netlify (https://app.netlify.com/)
2. Register menggunakan email atau github
3. Masuk ke tab sites lalu drag and drop seluruh folder HTML yang telah kalian buat.
4. Setelah proses selesai, kalian bisa mengedit nama website kalian.

Selain menggunakan metode drag and drop, kita juga bisa mendeploy project yang ada pada repository github kita. Berikut merupakan step by stepnya :
1. Masuk ke Netlify (https://app.netlify.com/)
2. Register menggunakan github
3. Masuk ke tab sites lalu pilih "Import From Git"
4. Pilih GitHub
5. Jika itu merupakan pertama kali kalian mendeploy menggunakan repository github maka akan ada beberapa verfifikasi data dari github yang perlu kalian lengkapi
6. Pilih repository yang ingin kalian deploy
7. Klik Deploy Sites
8. Kalian bisa mengganti nama website pada tab "Site Settings"
9. Pilih "Change Sites Name"


---
# CSS
---
**CSS** merupakan singkatan dari Cascading Sheets Style. Jika HTML digunakan untuk membuat kerangka website, CSS digunakan untuk mendesain tampilan halaman website agar terlihat lebih menarik. Dengan CSS, kita bisa mengubah warna, menggunakan font custom, editing text format, mengatur tata letak, dan lainnya.

Terdapat 3 cara untuk **menggunakan CSS**. Tiga cara tersebut adalah :
1. Inline CSS
Inline CSS merupakan cara penggunaan CSS pada file HTML dan kode CSS akan dituliskan pada tag HTML yang ingin diberikan pengaturan tampilan. Contohnya adalah sebagai berikut.
```sh
<!-- inline CSS -->
    <h1 style="background-color: aqua">Hai></h1>
```
2. Internal CSS
Internal CSS merupakan cara penggunaan CSS dengan menuliskan kode CSS pada file HTML dan menggunakan tag <style>
```sh
<!-- internal CSS-->
    <!-- <style>
    h1 {
      border: black 3px solid;
    }
    </style> -->
```
3. External CSS
External CSS merupakan penggunaan CSS dengan menuliskan kode CSS pada file terpisah. File tersebut kemudian dihubungkan dengan file HTML dengan menggunakan tag <link>.
```sh
<!-- external CSS-->
    <link rel="stylesheet" href="latihan.css" />
```

 ### Flexbox
Flexbox adalah cara untuk mengatur layout. Penerapan flexbox sangat disarankan karena penggunaanya  yang mudah dan sudah disupport oleh banyak browser.

Konsep dari flexbox adalah memiliki 1 parent/container dan bisa memiliki beberapa child/item. Secara sederhananya, bisa kita banyangkan sebagai box di dalam box.

### Properti Flexbox
**Flex-direction** merupakan properti yang digunakan untuk mengatur letak item child.  Ada 4 value flex-direction, yaitu :
1. Row (default) : secara default letak item child membentuk sebuah baris dari kiri ke kanan.
2. Row-reverse : letak item child membentuk sebuah baris dari kanan ke kiri
3. Column : letak item child membentuk sebuah baris dari atas ke bawah
4. Column-reverse : letak item child membentuk sebuah baris dari bawah ke atas

**Flex-wrap**  merupakan properti yang digunakan untuk membatasi jumlah item child dalam 1 line dan membuat child lainnya berpindah posisi ke line yang baru. Ada 4 value dari flex-wrap, yaitu :
1. No-wrap (default) : secara default , flex tidak menggunakan flex-wrap
2. Wrap : flex item akan memiliki beberapa line dari atas ke bawah  jika space dalam 1 line sudah full width.
3. Wrap-reverse : kebalikan dari wrap yaitu lex item akan memiliki beberapa line dari bawah ke atas  jika space dalam 1 line sudah full width

**Flex-flow** adalah properti yang digunakan sebagai shortcut untuk set up flex-direction dan flex-wrap bersamaan. Terdapat 4 value flex-flow, yaitu :
1. Row nowrap
2. Column wrap
3. Column reverse
4. Row-reverse wrap-reverse

**Order** adalah properti yang berfungsi untuk ordering item mana yang ingin kita atur posisinya berdasarkan urutan order. Terdapat 3 value dari properti order, yaitu :
1. -1 : Item child yang di set order -1, maka item child tersebut akan berada di ordering paling awal atau paling kiri.
2. 0 (default) : Flex secara default memiliki order 0 pada setiap item child. Ini berarti 0 akan membuat item child sesuai urutan pada html.
3. 1: Item child yang di set order 1, maka item child tersebut akan berada di ordering paling akhir atau paling kanan.

**Alignment** pada flex memiliki properti properti **justify-content** digunakan untuk mengatur tata letak dan space antar item child secara horizontal atau main axis. Justify-content memiliki 6 value yaitu:
1. flex-start
2. flex-end
3. center
4. space-between
5. space-around
6. space-evenly

Untuk membuat website menjadi responsive, kita bisa menggunakan CSS untuk mengatur lebar viewport. Contohnya adalah ketika lebar layar berukutan x-px atau kurang dari itu, maka jalankan script A. Berikut merupakan contoh penerapannya.
```sh
/* Jika ukuran layar 680px atau kurang dari itu */

@media screen and (max-width:680px){

	#maincontent{
		width: auto;
		float: none;
	}
	#sidebar{
		width: auto;
		float: none;
	}
}
```

Berikut merupakan **contoh** penulisan CSS dengan cara external CSS atau menuliskan CSS pada file yang berbeda (file HTML bisa dilihat pada contoh HTML di atas).
```sh
h1 {
  padding: 10px 20px 30px;
  /* margin: 0 100px; */
  display: inline-block;
  /* visibility: hidden; */
  width: 50% ;
  border: black solid 5px;
}

/* img {
  position: relative;
  left: 100px;

} */

.deskripsi {
  position: relative;
}

.deskripsi img {
  position: absolute;
  top: 0;
  right: 0;
  /* margin-top:  20px; */
  z-index: -1;
}

.deskripsi-flex {
  margin: 200px 0 0;
  display: flex;
  border: 1px solid black;
  align-items: center;
}
```

---
# ALGORITMA
---
**Algoritma** adalah langkah-langkah yang diperlukan untuk menyelesaikan sebuah masalah.
Algoritma yang baik harus memiliki beberapa kualitas, yaitu :
1. Input dan output harus didefinisikan terlebih dahulu dengan tepat
2. Setiap step harus benar-benar clear dan tidak ambigu
3. Algoritma seharusnya tidak mengandung suatu code pada bahasa pemograman tertentu. Algoritma harus dibuat agar dapat digunakan dalam bahasa pemograman apapun.

Algoritma penting untuk kita pelajari karena programming itu adalah **algoritma dan struktur data**. Data struktur digunakan untuk mengelola/manajemen sebuah data, sedangkan algoritma yang akan menyelesaikan suatu permasalahan menggunakan data tersebut. 

Hal yang penting diketahui dalam membuat sebuah program adalah waktu sangat berharga, memory perlu dihemat, mikirkan jangka panjang (scalability). Oleh karena itu, menentukan algoritma adalah salah satu proses yang penting pada saat mendevelop sebuah program.

Contoh dari **algoritma sederhana** adalah algoritma menentukan bilangan genap. Algoritmanya adalah sebagai berikut :
>Start
>Mendeklarasikan variabel bilangan
>Input angka
>Melakukan pengecekan dengan cara dibagi 2
>Jika hasil modulusnya adalah 0 (bilangan genap), tampilkan Bilangan Genap
>Jika hasil modulusnya bukan 0, maka tampilkan Bukan Bilangan Genap

**Pseudocode** adalah menuliskan algoritma dengan umumnya bahasa inggris sebelum kita implementasikan ke bahasa pemograman tertentu.
Pseudocode dari contoh algoritma di atas adalah sebagai berikut :
```sh
Even Number :

Read number

num = number % 2
    if num = 0 :
        write "Bilangan Genap"
    else :
        write "Bilangan Ganjil"
```

Adapun kode Javascript dari algoritma dan pseudocode di atas adalah sebagai berikut.
```sh
function ganjilGenap(number){
    if(number%2 == 0){
        console.log("Bilangan Genap")
    }else{
        console.log("Bilangan Ganjil")
    }
}
```

---
#  JAVASCRIPT
---
**Javascript** adalah bahasa pemograman yang sangat powerful yang digunakan untuk logic pada sebuah website. Javascript juga dapat membuat website menjadi interaktif dan dinamis. 

Untuk menjalankan Javascript bisa dilakukan melalui **browser** pada device setiap user. Umumnya browser Chrome dan Mozilla yang sudah support untuk semua fitur Javascript.

### Data Types
Tipe data adalah klasifikasi yang kita berikan untuk berbagai macam data yang digunakan dalam programming.
Berikut merupakan 6 tipe data fundamental pada Javascript :
1. Number, tipe data yang mengandung semua angka termasuk angka desimal. Contohnya adalah 1,2,100.
2. String, grup karakter yang ada pada keyboard laptop/PC kita yaitu letters (huruf), number (angka), spaces (spasi), symbol, dan lainnya. Tipe data ini harus diawali dan diakhiri oleh single quotes '...' atau double quotes "...".
3. Boolean, tipe data yang hanya mempunyai 2 buah nilai yaitu true dan false.
4. Null, tipe data yang diartikan bahwa sebuah variable/data tidak memiliki nilai. Null berbeda dengan string kosong. String kosong masih memiliki tipe data string.
5. Undefined, tipe data yang merepresentasikan varibel/data yang tidak memiliki nilai. Undefined berbeda dengan null. Undefined didapat dari hasil berikut, seperti nilai dari pemanggilan variabel yang belum didefinisikan, nilai dari pemanggilan element array yang tidak ada, nilai dari pemanggilan property objek yang tidak ada, nilai dari pemanggilan fungsi yang tidak mengembalikan nilai (return), nilai dari parameter fungsi yang tidak memiliki argumen.
6. Object, koleksi data yang saling berhubungan (related). Tipe data pbject dapat menyimpan data dengan tipe data apapun (number, string, boolean, dan lainnya). Tipe data object mempunyai key dan value.

### Variable
Variable adalah container/tempat untuk menyimpan sebuah nilai. Hal-hal yang dapat dilakukan dengan variabel adalah sebagai berikut :
1. Membuat variabel dengan nama yang jelas dan menggambarkan tentang data tersebut
2. Menyimpan dan mengupdate informasi/data yang disimpan
3. Mendapatkan/menampilan data yang tersimpan

Pada Javascript, terdapat 3 cara untuk mendeklarasikan variabel, yaitu var, let, dan const. Jika menggunakan **const** maka nilai dari variabel tersebut tidak akan bisa diubah lagi. Adapun perbedaan antara var dan let adalah let dikenalkan pada versi javascript terbaru ES6 dan mendukung kaidah global variabel dan local variabel.Jadi, dianjurkan untuk menggunak let untuk variabel yang dinamis/dapat diubah. 

Aturan penamaan variabel adalah harus mendeskripsikan tentang data yang disimpan, tidak bisa menggunakan number pada awal nama variabel, dan menggunakan camelcase untuk penamaan yang lebih dari 1 kata. 

### Operator
Operator adalah simbol yang digunakan untuk melakukan operasi pada suatu nilai dan variabel.
1. Assignment Operator (=).
Operator ini digunakan untuk menyimpan sebuah nilai pada variabel.
2. Mathematical Assignment Operator.
Operator ini digunakan untuk mendapatkan hasil dari operasi yang dilakukan pada variabel.
3. Increment dan Decrement (++, --)
Operator ini digunakan untuk menambah atau mengurangi sebesar 1 nilai.
4. Arithmetic Operator.
Yaitu operator yang melibatkan operasi matematika. Operator ini meliputi Tambah (+), Kuramg (-), Perkalian (*),Pembagian (/), dan Modulus (%).
5. Comparison Operator. Operator adalah operator yang membandingkan satu nilai dengan nilai lainnya. Hasil operasi yang melibatkan comparison operator adalah antara true or false. Operator ini meliputi Lebih kecil dari (<), Lebih besar dari (>) , Lebih kecil atau sama dengan (<=), Lebih besar atau sama dengan (>=), Sama dengan (=== ), Tidak sama dengan (!==).
6. Logical Operator. Operator yang biasa digunakan untuk sebuah CONDITIONAL pada pemograman dan menghasilkan nilai BOOLEAN yaitu TRUE or FALSE. Operator ini meliputi
AND operator (&&), OR operator (||), NOT operator (!)

### Conditional
**Conditional** merupakan statement percabangan yang menggambarkan suatu kondisi. Conditional statement akan mengecek kondisi spesifik dan menjalankan perintah berdasarkan kondisi tersebut. Yang dicek adalah apakah kondisi tersebut TRUE (benar). Jika TRUE maka code didalam kondisi tersebut dijalankan.

**If Statement**
If statement memiliki 3 kata kunci utama, yaitu if, else if, dan else. Berikut merupakan contoh penggunaan if statement.
```sh
let nilai = 80

if(nilai >= 95){
    console.log("A")
}else if(nilai >=80){
    console.log("B")
}else{
    console.log("C")
}
```

**Switch Case Conditional**
Switch case conditional digunakan ketika percabangan yang ada terlalu banyak. Berikut merupakan contoh penggunaan switch case conditional.
```sh
let warna = merah

switch(buttonPushed){
    case merah :
        console.log("anda menekan tombol merah");
        break;
    case kuning :
        console.log("anda menekan tombol kuning");
        break;
    case hijau :
        console.log("anda menekan tombol hijau");
        break;
    case biru :
        console.log("anda menekan tombol biru");
        break;
    case hitam :
        console.log("anda menekan tombol hitam");
        break;
    default :
        console.log("Anda tidak menekan tombol berwarna");
}
```

**Ternary Operator**
Ternary operator merupakan short-syntax dari statement if … else. Berikut merupakan contoh dari penggunaan ternary operator.
```sh
let nilai = 80

nilai >=70 ? console.log("A") : console.log("B");
```

### Loop
Looping adalah statement yang mengulang sebuah instruksi hingga kondisi terpenuhi atau jika kondisi stop/berhenti tercapai. 

**For Loop**
FOR LOOP merupakan instruksi pengulangan yang dapat kita berikan pada program yang kita kembangkan. For loop digunakan jika developer sudah mengetahui berapa banyak perulangan yang ingin dilakukan. Berikut merupakan parameter yang dimiliki oleh for loop :
1. Starting Value : Sebagai inisialisasi awal dari mana mulainya sebuah pengulangan. Kita memberikan nilai awal/default pada parameter ini
2. Stop Value: For loop akan terus berjalan selama kondisi ini terpenuhi. Selama kondisi bernilai TRUE.
3. Step Value (Increment/Decrement): Iterasi statement yang digunakan untuk mengupdate variabel yang menjadi kontrol pada pengulangan

Contoh sederhana dari for loop adalah sebagai berikut :
```sh
for (let i=0; i<=10; i++){
    console.log(i)
}
```

**While Loop**
While loop akan menjalankan instruksi pengulangan kondisi bernilai TRUE. While loop digunakan jika developer tidak mengetahui berapa banyak perulangan yang akan dilakukan.

Contoh sederhana dari while loop adalah sebagai berikut :
```sh
let i = 0
while (i <= 10){
    console.log(i)
    i++
}
```

**Do While**
Do while hampir mirip dengan while loop. Hal yang membedakannya adalah do while akan melakukan satu perulangan terlebih dahulu baru mengecek kondisi. Jika kondisi bernilai true maka perulangan akan berlanjut. Namun, jika kondisi bernilai false maka perulangan akan berhenti.

Berikut merupakan contoh sederhana dari do while :
```sh
let i = 0

do{
    console.log(i)
    i++
}while(i <= 10)
```

**Nested Loop**
Nested loop adalah perulangan yang terdapat pada perulangan lainnya atau bahasa sederhanya dapat dikatakan sebagai perulangan dalam perulangan. Berikut meruapkan contoh dari Nested Loop.
```sh
for(let i=0; i<3; i++){
    for(let j=0; j<3; j++){
        console.log(i, j)
    }
}
```














