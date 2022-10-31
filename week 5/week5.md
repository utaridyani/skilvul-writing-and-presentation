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

**REST** : Arsitektur yang memiliki beberapa rule
**RESTFUL** : API yang menerapkan arsitektur dan rule REST

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
