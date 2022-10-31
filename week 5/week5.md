# WEB SERVER DAN RESTFUL API
---

**Web Server** adalah tempat untuk meletakkan kodingan baik itu front-end ataupun back-end. Web server juga bisa dikatakan sebagai gabungan software dan hardware tempat aplikasi berada. Bagian software tersebut adalah bagaimana web server mengelola bagaimana web users mengakses file yang telah dihosting. Sedangkan bagian hardware adalah computer yang menyimpan software dari web server dan komponen file yang bersangkutan. Aplikasi tersebut akan bisa diakses melalui HTTP.

Terdapat 2 jenis Web Server, yaitu Static Web Server dan Dynamic Web Server. Berikut merupakan penjelasan lengkapnya.
1. **Static Web Server** adalah sebuah hardware (komputer) dengan HTTP Server (software). Dipanggil static karena server langsung mengirim file yang telah dihosting kepada web browser.
2. **Dynamic Web Server** adalah sebuah static web server yang dilengkapi dengan ekstra software yang umumnya adalah aplication server dan database. Dipanggil dynamic karena aplication server akan mengupdate file yang dihosting sebelum dikirim ke web browser.

**Single Page Aplication / Client Side Server** adalah seluruh proses yang dilakukan pada web browser. Data yang direquest adalah dalam bentuk JSON dan akan diberikan ke web browser untuk ditampilkan.

**Dynamic Site / Server Side** adalah proses yang dilakukan sebagian pada server. Urutannya adalah meminta data, lalu server akan menyiapkan halaman dan data, lalu akan diberikan kepada web browser.

**Arsitektur Web Service**
1. COBRA (1991)
2. RDA (1993)
3. XML - RPC (1998)
4. SOAP (1999)
5. REST (2000)
6. JSON - RPC (2005)
7. ODATA (2007)
8. GRAPHQL (2015)
9. GRPC (2016)

**REST** (Representational State Transfer) 
- Format data : XML, JSON, HTML, Plain Text
- Public APIs
- Simple resource driven apps

**Rule REST**
1. Uniform interface, bentuk API 1 dan 2 mirip
2. Berbasis Client Server
3. Stateless
4. Cacheable
5. Layered System
6. Code on Demand

**REST** (Representational State Transfer) : Arsitektur yang memiliki beberapa rule. Arsitektur ini menggunakan metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi. Tujuannya untuk menjadikan sistem memiliki performa yang baik, cepat dan mudah untuk dikembangkan terutama dalam pertukaran dan komunikasi.
**RESTFUL** : API yang menerapkan arsitektur dan rule REST. RESTFUL API memiliki 4 komponen utama, yaitu : URL Design, HTTP Verbs, HTTP Response Code, Format Response. 

**HTTP Method**
1. GET : Menggambil data
2. POST : Mengirim data baru ke server
3. DELETE : Menghapus
4. PUT / PATCH : Mengupdate sebagian data

**API**
-Api bisa disetting sistem keamanan jadi tidak semua orang bisa mengakses database.
-API tidak langsung mengakses database, mealinkan melalui server.

**Software Architecture**
1. Monolith : Database, back-end, front-end menajadi satu.
2. Front-End dan Back-End
3. Microservice : Back-End dibagi menjadi layanan yang lebih kecil lagi.

**Alamat API yang Bagus**
1. Menggunakan S (Plurals) untuk merepresentasikan data. Contohnya adalah user**s**
2. Singelton dan Collection Resorce
    - Menggambil data collection -> /users
    - Mengambil single data -> /users/identififier
3. Jika lebih dari satu kata, maka disambung menggunakan strip (kebab case) dan kalau bisa huruf kecil semua (contohnya adalah /user-devices)

**Status Code**
- 2xx : success
- 3xx : redirected
- 4xx : client error (kesalahan user)
- 5xx : server error

---
# NODE JS
---
**Node Js** adalah JavaScript runtime (tempat untuk menjalankna atau mengeksekusi kode) yang dibangun di atas V8 Engine.

> Masing-masing browser memiliki engine sendiri untuk menjalankan JavaScript. Engine yang dimiliki oleh Chrome adalah V8.

**Arsitektur Node Js**
1. Single Thread : menjalankan beberapa tugas secara bersamaan dalam satu tumpuukan atau panggilan
2. Event Loop : karena menggunakan konsep single thread, muncul event queue yang digunakan untuk menampung perintah yang akan dieksekusi. Event loop ini akan digunakan untuk mengecek apakah terdapat antrian baru pada queue secara terus menerus hingga semua perintah selesai dieksekusi.
3. Server Side Scripting : bisa menjalankan javascript di server side dengan menggunakan terminal command line menggunakan perintah node.

**Fitur Utama** dari Node Js adalah sebagai berikut :
1. File System
2. HTTP dan HTTPS, yang artinya bisa membuat web service serta menerima dan membuat request
3. REPL (Read, Eval, Print, dan Loop), bisa dibayangkan sebagai terminalnya Node Js
4. Console, terminal yang bisa diakses melalui script

#### Node Js For Back End
Node Js memiliki beberapa Build in Method, yaitu :
1. **Console**, bisa menampilkan hasil pada terminal tanpa HTML.
    Berikut merupakan contoh perintah console untuk menampilkan sebuah kalimat :
    ```sh
    console.log("Ini adalah writing test")
    ```
    Berikut merupakan perintah untuk menjalankan file pada console. Jika file dengan ekstensi .js, maka ekstensinya tidak perlu ditulis :
    ```sh
    node namafile
    
    <!--contoh-->
    node app.js
    
    <!--cara lain-->
    node app
    ```
2. **Process**, module yang digunakan untuk menampilkan dan mengontrol proses Node Js yang sedang berjalan. Berikut merupakan contoh penggunaan process.
    ```sh
    <!--JavaScript versi 16 masih menggunankan require-->
    const {env} = require('process')

    console.log(env)
    ```
    Contoh kode yang digunakan untuk menampilkan salah satu proses :
    ```sh
    const process = require('process')
    
    console.log(process.env.APPDATA)
    ```
3. **OS**, module yang digunakan untuk mendapatkan informasi OS yang digunakan oleh user. Berikut merupakan contoh perintah untuk menampilkan informasi versi OS yang digunakan.
    ```sh
    const OS = require('os')

    console.log(OS.version())
    ```
4. FS (File System), bisa membaca hingga menghapus file. FS sering digunakan untuk berinteraksi dengan file dengan ekstensi .txt, .csv, .json. Berikut merupakan contoh kode untuk menggunakan FS untuk membaca sebuah file.
    ```sh
    const fs = require('fs')

    // fs.readFile('namafile', (err, data) )
    fs.readFile('os.js', (err, data) =>{
        // print data
        console.log(data.toString())
    })
    ```
5. **Events**, berikut merupakan contoh penggunaan events
    ```sh
    const EventEmitter = require('events')
    
    //inisialisasi
    const event = new EventEmitter()
    
    event.on('event', () => {
        console.log("ini event")
    })
    
    event.emit("event")
    ```
6. **Util**, alat bantu/utilities untuk membantu kebutuhan internal API di Node Js. Berikut merupakan contoh penggunaannya :
    ```sh
    const util = require('util')

    console.log(util.format("%s", "utari"))
    ```

>**env** akan digunakan untuk mengyimpan konfigurasi (bersifat secret)

>**Versi 16** masih menggunakan require (hal yang ingin di-assign ke variabel). Berikut merupakan contohnya :
    ```sh
    const {env} = require('process')
    ```

Ketika memulai project baru kita bisa melakukan **npm init** untuk menginisialisasi package baru. Perintah ini akan membuatkan kita file baru dengan nama **package.json**

Untuk test package ini, kita bisa menambahkan sebuah script pada package.json seperti berikut :
```sh
{
  "name": "intro-node-js",
  "version": "1.0.0",
  "description": "",
  "main": "console.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    <!--code ini ditambahkan untuk run file events.js ketika events dipanggil-->
    "events": "node events"
  },
  "author": "",
  "license": "ISC"
}
```

Lalu untuk memanggilnya, kita bisa menggunakan kode **npm run** seperti berikut :
```sh
npm run events
```

---
# EXPRESS JS
---

**Express Js** adalah framework untuk membuat web server buil on Node Js. Framework ini bermanfaat untuk membantu mengelola aliran data dari server ke aplikasi. Kelebihan dari framework Express Js ini adalah fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.

**Install Express Js** dapat dilakukan dengan menjalankan sintaks berikut pada terminal :
```sh
npm i express
```

**Back End Web Aplication** adalah aplikasi yang berjalan pada server-side yang akan memberikan informasi berupa hal yang diperlukan sesuai dengan request dari client atau browser. Umumnya server-side aplication akan membuat REST API.

#### Basic Routes
**Routes** adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan. 

**Method** yang dapat kita gunakan adalah GET, POST, DELETE, PATCH seperti yang ada pada REST API. Berikut merupakan contoh penggunaan method POST.
```sh
contoh method
```

**Response** adalah hal yang dapat kita kirim menggunakan parameter dari route express.js yaitu **res.Send()** untuk mengirim plain text ketika kita mengakses route tersebut. 

**Status Code** adalah penanda informasi apakah route yang kita akses berjalan sebagaimana mestinya dan tidak terjadi error.

**Query** adalah parameter yang digunakan untuk membantu menentukan tindakan yang lebih spesifik daripada hanya sekedar router biasa. Biasanya query ditaruh di akhir route dengan memberikan informasi diawali dengan “?” kemudian tedapat key dan data yang dapat ditindak lanjuti. Ex : “?q=hello&age=23”.

#### Express Middleware
**Middleware** adalah sebuah fungsi yang memiliki akses ke object request (req), object response (res), dan sebuah fungsi next didalam request-response cycle.

**Middleware** berfungsi untuk menentukan bahwa suatu HTTP Request adalah request yang buruk dan salah, maka middleware function memiliki kemampuan untuk menghentikan request-response cycle.

Sebaliknya, jika middleware function menentukan suatu HTTP Request baik dan benar, maka middleware function memiliki kemampuan untuk melanjutkan request-response cycle ke proses selanjutnya. Setelah sebuah HTTP Request melewati semua middleware yang ada di aplikasi, HTTP Request tersebut akan mencapai handler function.

**Hal yang Dapat Dilakukan Middleware**
1. Menjalankan kode apapun, artinya adalah function middleware bisa digunakan untuk mengeksekusi kode apapun untuk suatu tujuan tertentu.
2. Memodifikasi Object Request dan Object Response.
3. Menghentikan request-response cycle.
4. Melanjutkan ke middleware function selanjutnya atau ke handler function dalam suatu request response cycle.

**Jenis Express Middleware Berdasarkan Cara Penggunaan**
1. **Aplication Level Middleware**, sebuah function middleware yang melekat ke instance object Application Express. Penggunaannya dengan cara memanggil method app.use(). Application Level Middleware akan di jalankan setiap kali Express Application menerima sebuah HTTP Request.
2. **Router Level Middleware**, function middleware yang cara kerjanya sama persis dengan application level middleware, yang menjadikan perbedaan adalah middleware function ini melekat ke instance object Router Express. Penggunaannya dengan cara memanggil method express.Router(). Router Level Middleware hanya akan di jalankan setiap kali sebuah Express Router yang menggunakan middleware ini menerima sebuah HTTP Request, sedangan pada Router yang lain tidak akan dijalankan.
3. **Error Handling Middleware**, error Handling mengacu kepada bagaimana cara sebuah Express Application menangkap dan memproses error yang terjadi, baik itu berupa kesalahan yang synchronous maupun asynchronous. Error handle function default milik Express Application hanyalah kerangka functionnya saja, kita tetap harus menuliskan di dalam function ini bagaimana sebuah error akan di handle. Error Handling Middleware digunakan pada Application Level Middleware

**Jenis Express Middleware Berdasarkan Source Middleware Function**
1. **Express Build-in Middleware**, Express JS sudah menyediakan 3 buah build-in middleware function yang bisa digunakan, yaitu :
    - express.static(), memungkinkan sebuah express application melayani asset statis berupa file, seperti file HTML, gambar, video, dokumen, dan sebagainya.
    - express.json(), memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format JSON.
    - xpress.urlEncoded(), memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format urlencoded.
2. **Third Party (custom) Middleware**, memungkinkan kita untuk menambahkan fungsionalitas dari sebuah Express Application. 

---
# DESIGN DATABASE WITH MySQL
---
Berdasarkan materi yang telah dipelajari pada hari Kamis dan Jumat, saya akan mendesain sebuah database dengan studi kasus **Peminjaman Buku pada Perpustakaan** dan **Film Favorit (challenge pada saat kelas)**

#### Menentukan Entity
Beberapa kandidat yang paling sering menjadi sebuah entity : peoples, things, events, locations. 

Berikut merupakan entitas yang terdapat pada studi kasus peminjaman buku perpustakaan.
1. Mahasiswa
2. Buku
3. Peminjaman

Berikut merupakan entitas yang terdapat pada studi kasus peminjaman buku perpustakaan.
1. Mahasiswa
2. Film
3. Genre

#### Menentukan Atribut dari Setiap Entity
Berikut merupakan atribut dari masing-masing entitas yang sebelumnya telah disebutkan pada database pinjam buku.
1. Mahasiswa
    - id_mahasiswa
    - nama
    - jurusan
    - fakultas
2. Buku
    - id_buku
    - judul
    - tahun_terbit
    - penulis
3. Peminjaman
    - id_mahasiswa
    - id_buku
    - tanggal_pinjam
    - tanggal_kemballi

Berikut merupakan atribut dari masing-masing entitas yang sebelumnya telah disebutkan pada database film favorit.
1. Mahasiswa
    - nim
    - nama
    - alamat
2. Film
    - id_film
    - judul
    - tgl_rilis
3. Genre
    - id_genre
    - nama

#### Menentukan Relasi Antar Entity
1. Relasi antara **mahasiswa** dan **buku** adalah many to many. Hal ini disebabkan satu orang mahasiswa bisa meminjam banyak buku dan buku dapat dipinjam oleh banyak mahasiswa. Dikarenakan relasinya adalah many to many, maka diperlukan entitas pelengkap, yaitu table peminjaman.

2. Relasi antara **mahasiswa dan film** adalah many to many karena seorang mahasiswa bisa menyukai lebih dari satu lagu dan satu lagu bisa disukai oleh banyak ornag. Relasi antara **film dan genre** adalah many to many karena sebuah film bisa memiliki lebih dari satu genre dna satu genre bisa dimilii lebih dari satu orang.

**ERD database dapat dilihat pada folder gambar**

#### Normalisasi Database
Normalisasi database adalah pengelompokan atribut data yang akan membentuk entitas sederhana, non redundant, fleksible dan mudah beradaptasi sehingga dapat dipastikan bahwa database yang dibuat adalah database yang berkualitas baik.

**Tujuan Normalisasi Database**
1. Menghilangkan dan mengurangi redudansi data.
2. Memastikan dependensi data (data berada pada tabel yang tepat).

**Tahapan Normalisasi**
1. 1NF, inti dari normalisasi 1NF adalah tidak boleh ada grouping data ataupun duplikasi data. Suatu tabel dikatakan 1NF jika dan hanya jika setiap atribut dari data tersebut hanya memiliki nilai tunggal dalam satu baris.
2. 2NF, pada tahap normalisasi 2NF ini tabel tersebut harus dipecah berdasarkan primary key. Syarat 2NF adalah tidak diperkenankan adanya partial “functional dependency” kepada primary key dalam sebuah tabel.
3. 3NF, jika terdapat suatu atribut yang tidak bergantung pada primary key tapi bergantung pada field yang lain maka atribut-atribut tersebut perlu dipisah ke tabel baru. Pada 3NF tidak diperkenankan adanya partial “transitive dependency” dalam sebuah tabel.





















