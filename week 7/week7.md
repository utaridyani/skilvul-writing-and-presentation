# SEQUELIZE
----
#### Step-step untuk menggunakan Sequelize
1. Install sequalize dan driver ke database yang kita miliki
    ```sh
	npm install sequelize mysql2
	```
    Terdapat 2 cara untuk menggunakan sequelize, yaitu dengan migration dan tanpa migration. Kali ini kita akan mencoba dengan menggunakan migration.

2. Install migrations (hitory perubahan pada table hal ini akan bermanfaat saat kita menemukan sebuah masalah pada database, kita bisa kembali ke versi sebelumnya)
    ```sh
	npm install -D sequelize-cli
	```
3. Inisialisasi project (proses ini akan akan membuat folder config yang digunakan sebagai directiory untuk settingan database, models yang akan digunakan sebagai representasi table, migrations adalah tempat yang menyimpan perubahan pada table, seeders-tempat untuk data demo).
    ```sh	
    npx sequelize-cli init
    ```
    Pada configuration ada settingan untuk database yang akan disesuaikan dengna env node. Sesuaikan username, password, dan nama database. jika belum memiliki database, maka bisa menggunakan db:create agar database tersebut dibuat terlebih dahulu.
3. Membuat model pertama dan juga migrationnya.
    ```sh
    npx sequelize model:create --name User --attributes name:string,email:string,password:string
    ```
4. Jalankan perintah yang sudah masuk migration sehingga tabel yang sebelumnya dibuat masuk kedalam database
    ```sh
	npx sequelize-cli db:migrate
	```
5. Setelah menjalankan kode ternyata ada yang salah? Jalankan perintah berikut untuk meng-undo perintah migrate terakhir.
    ```sh
	npx sequelize-cli db:migrate:undo
	```
6. Syntaks untuk menambahkan migration tanpa model baru
    ```sh
	npx sequelize migration:create --name add-column-user
	```
    Setelah itu pada file migration yang telah dibuat, tambahkan query yang diinginkan. Contohnya adalah **addcolumn**pada async up
    ```sh
    await queryInterface.buildInMethod("nama_tabel", "nama kolom", tipe data)
    
	await queryInterface.addColumn("Users", "username", Sequelize.STRING)
	```
    Jika tidak jadi di up, harus di remove dengan menambahkan kode berikut pada asynce down
    ```sh
	await.queryInterface.removeColumn("Users", "username")
	```
7. Cara menambahkan seeders
    ```sh
	npx sequelize-cli seed:generate --name demo-user
	```
    Data seeder bisa dimasukkan pada folder seeders dengan kode berikut.
    ```sh
    await queryInterface.bulkInsert("Users", [
      {name: "utari", email:"utari@gmail.com", password: "utari", createdAt: new Date(), updatedAt: new Date()},
      {name: "dyani", email:"dyani@gmail.com", password: "dyani", createdAt: new Date(), updatedAt: new Date()}
    ])
    ```
8. Cara Run seednya
    ```sh
	npx sequelize db:seed --seed namaseed
	```
9. Menuliskan query pada Router (router-> controller)
    Endpoint GetAllUser
    ```sh
    getAllUser: async (req, res) => {
        const user = await User.findAll()
        res.json({
        message: "succeed get data",
        data: user})}
    ```
    Endpoint getUserByID
    ```sh
    getUserByID: async (req, res) => {
        //menangkap id req
        const { id } = req.params
        const user = await User.findByPk(id)
        res.json({
          message: "succeed get data",
          data: user
    })
    ```
10. Untuk menampilkan data dengan hubungan maka kita gunakan assosiation.
Contoh untuk menampilkan penulis dari sebuah blog maka asosisasi yang kita gunaakn adalah BelongsTo. Asosiasi ini kita tambahkan pada model (pada function associate).
	contoh : this.belongsTo(models.User)
---
# MONGO DB
---
**MongoDB** adalah database yang berbasis NO SQL. Selain mongodb juga ada yang lain seperti Casandra dan lainnya. Sering digunakan untuk big data karena datanya bersifat flexible. MongoDB kita menyimpan document dengan format JSON, kita tidak memerlukan query untuk mengolah database. 

**Istilah** yang perlu diketahui saat menggunakan MongoDB :
1. Database, yaitu wadah dengan struktur penyimpanan yang disebut collection. 
2. Collection, yaitu tempat kumpulan informasi data yang berbentuk dokumen. Collection dipadankan seperti tabel-tabel yang berisi data pada database SQL. 
3. Document, yaitu satuan unit terkecil dalam MongoDB. 

MongoDB memiliki collection di dalam databasenya. Pada collection akan terdapat document.

Terdapat 2 cara menggunakan compass, yaitu **GUI dan CLI.**

>ODM mongoDB adalah mongoose

Struktur data MongoBD disebut sebagai Schema. Pembuatan Schema ini dapat dilakukan dengan 2 cara, yaitu embedd dan reference.
1. Embedd merupakan schema yang lansung menyatukan child document pada parent documentnya. Berikut merupakan contoh dari embedded document.
    ```sh
    {
      "_id": 1,
      "name": "Ashley Peacock",
      "addresses": [
        {
          "address_line_1": "10 Downing Street",
          "address_line_2": "Westminster",
          "city": "London",
          "postal_code": "SW1A 2AA"
        },
        {
          "address_line_1": "221B Baker Street",
          "address_line_2": "Marylebone",
          "city": "London",
          "postal_code": "NW1 6XE"
        }
      ]
    }        
    ```
2. Reference merupakan schema yang membuat referensi untuk child document pada parent documentnya. Berikut merupakan contoh dokumen yang menggunkan konsep Reference.
    ```sh
    // Stored in the user collection
    {
      "_id": 1,
      "name": "Ashley Peacock",
      "addresses": [
        1000,
        1001
      ]
    }
    // Stored in the address collection
    {
      "_id": 1000,
      "address_line_1": "10 Downing Street",
      "address_line_2": "Westminster",
      "city": "London",
      "postal_code": "SW1A 2AA"
    }
    // Stored in the address collection
    {
      "_id": 1001,
      "address_line_1": "221B Baker Street",
      "address_line_2": "Marylebone",
      "city": "London",
      "postal_code": "NW1 6XE"
    }
    ```

#### Mongoose
Mongoose adalah library yang bisa dibilang sebagai Object Modelling MongoDB untuk NodeJS. Mongoose bisa digunakan untuk mengelola hubungan antara data, menyediakan validasi. Mongoose juga bisa digunakan untuk menerjemahkan antara objek dalam kode dan representasi Objek tersebut di MongoDB. 

**Langkah Awal Penggunaan Mongoose**
1. Install Mongoose
    ```sh
    npm install mongoose
    ```
2. Create Connection pada file .env
3. Membuat Schema

**Pupulate**
Populate ada kaitannya dengan relasi database. Populate adalah proses penggabungan 2 collection atau lebih menjadi satu objek JSON.

**Syntax Dasar Mongoose**
1. Membuat Collection
    ```sh
    db.createCollection("nama_coll")
    
    <!--contoh-->
    db.createCollection("books")
    ```
2. Menggunakan atau Berpindah Collection
    ```sh
    use nama_coll
    
    <!--contoh-->
    use books
    ```
3. Insert Data
    ```sh
    db.books.insertOne({title: "selamat mencoa", page: 123})
    ```
4. Mengambil Data
    ```sh
    db.books.find()
    ```
    
>Schema mongodb dapat dibuat sebagai embedd / reference

#### STEP MENGGUNAKAN MONGODB DENGAN EXPRESS :
1. Siapkan file dengan express terlebih dahulu
2. Persiapkan mongoose (ODM untuk MongoBD)
3. Install mongoose
    ```sh
	npm install mongoose
	```
4. Membuat koneksi
    -Buat folder config dan dialamnya buat file db.js. Berikut merupakan kode dasar yang diperlukan pada file db.js.
    ```sh
    const mongoose = require('mongoose')

    //url db
    const DB_URL = 'mongodb://localhost:27017/latihan-mongoose'
    
    const db = mongoose.connect(DB_URL)
    
    module.exports = db
    ```
    -Test koneksi. Test koneksi dapat dilakukan pada file utama. Berikut merupakan kode yang terdapat pada file utama.
    ```sh
    const express = require('express');
    const db = require('./config/db');
    const app = express()
    
    const allRoutes = require('./routes');
    
    //menentukan port, dia akan mengambil port dari env (jika sudah ada,
    //ini biasanya ketika sudah di deploy maka server akan memakai
    //nomor port sendiri), jika tidak ada maka akan memakai port 3000
    const PORT = process.env.PORT || 3000
    
    //test koneksi database
    db.
    then(() => {
      console.log("database_terkoneksi")
    })
    .catch((err) => {
      console.log(err)
    })
    
    app.use(express.json())
    app.use(allRoutes)
    
    app.listen(PORT, () => {
      console.log("server running on port " + PORT);
    })
    ```
5. Buat schema model 
    -Buat schema. Berikut merupakan kode yang diperlukan untuk membuat schema.
    ```sh
    const userSchema = new Schema({
    nama: String,
    email: {
        type: String,
        required: true
    },
    password: String
    })
    ```
    -Buat model. Berikut merupakan kode yang diperlukan untuk membuat model
    ```sh
    const User = mongoose.model("User", userSchema)
    ```
6. Coba menambah data
    Berikut merupakan contoh kode yang digunakan untuk menambahkan data ke dalam collection.
    ```sh
     addUser: (req, res) => {
        //mengambil data dari req
        const data = req.body

        const user = new User(data)
        user.save()
    
        res.json({
          message: "data has been created"
        })
     }
    ```

7. Mengambil data
    Berikut merupakan contoh kode yang digunakan untuk mengambil data dari dalam collection.
    ```sh
     getAllUser: async (req, res) => {
        //menampilkan seluruh data kecuali password
        const users = await User.find({}, "-__v -password")
    
        res.json({
          message: "data already collected",
          data: users
        })
      }
    ```
8. Enkripsi password
    -Gunakan **npm bcrypt**
    ```sh
	npm install bcrypt
	```
    -Cara penggunaan penggunaan pada saat penyimpanan data ke dalam collection:
    ```sh
     addUser: (req, res) => {
        //mengambil data dari req
        const data = req.body
    
        //hashing dan enksripsi password
        const saltRounds = 10
        const hash = bcrypt.hashSync(data.password, saltRounds)
        data.password = hash
    
        const user = new User(data)
        user.save()
    
        res.json({
          message: "data has been created"
        })
     }
    ```
9. Contoh Syntax untuk login jika penyimpanan password menggunakan Bcrypt
    ```sh
    login: async (req, res) => {
        const data = req.body
    
        //ambil data email
        const user = await User.findOne({email: data.email})
    
        //decrypt password untuk cek password
        const checkPwd = bcrypt.compareSync(data.password, user.password)
    
        if (checkPwd) {
          res.json({
            message:"anda berhasil login",
            token: "disini tempat token yang kemarin sudah dipelajari"
          })
        } else {
          res.json({
            message: "kamu siapa yank?"
        })
        }
    }
    ```
9. Untuk validasi password misalnya minimlan password 8 huruf, tambahkan pada schema (jika mau diambil backend)

----
# DOCKER
----

**Docker** adalah software untuk yang menjalankan suatu aplikasi menggunakan container. Dengan docker kita bisa menjalankan aplikasi yang sama dengan OS yang berbeda. Aplikasi yg berjalan di dalam container docker tidak terpengaruh oleh faktor luar karena terisolasi. Docker berfungsi sebagai penyedia layanan virtual bagi aplikasi yg diinstall pada sebuah host. 

Docker sangat penting karena dengan menggunakan Docker, kita bisa mengoperasikan aplikasi yang kita miliki dengan mengabaikan perbedaan konfigurasi maupun sistem operasi, karena docker akan menyediakan hal-hal yang diperlukan untuk aplikasi mulai dari akses file, koneksi internet, hingga port agar aplikasi dapat berjalan dengan mulus

**Perbedaan Docker dengan VM**
VM memakan banyak resource dan waktu utk booting karena melakukan virtualisasi pada host hardware-nya. Sedangkan container kebalikannya dari vm, container melakukan virtualisasi pada host OS-nya

Docker memiliki beberapa komponen penting, yaitu :
**Docker registry** (tempat menyimpan docker image pada cloud. tempat untuk upload download image) memiliki 3 bagian, yaitu :
1. **Docker File** yang merupakan blue print dimana kita bisa menuliskan hal-hal yang ingin kita lakukan. Blueprint untuk membuat image.
2. **Docker Image**, template untuk menjalankan container
3. **Docker Container**, yaitu hal yang akan kita running. Container merupakan tempat untuk merunning aplikasi yang kita inginkan secara terisolasi. Satu container bisa menampung lebih dari satu image tapi satu container hanya bisa merunning satu hal.

#### Basic Syntax Docker
1. Download image dari docker hub, syntax yang digunakan adalah **docker pull**
    ```sh
    docker pull chuannen/comsay
    ```
2. Melihat kumpulan images yang sudah terdownload, syntax yang digunakan adalah **docker images**
    ```sh
    docker images
    ```
3. Menjalankan sebuah container, syntax yang digunakan adalah **docker run**
    ```sh
    docker run chuannen/comsay
    ```
4. Melihat container yang sedang berjalan
    ```sh
    docker ps
    ```

#### Dockerfile
**Dockerfile** adalah sebuah blueprint untuk membuat image dan juga costum image. Berikut merupakan langkah-langkah yang harus dilakukan :
1. Buat file dockerfile pada project
2. Tuliskan beberapa perintah di dalam dockerfile
3. Jalankan dockerfile dengan menggunakan perintah berikut
    ```sh
    docker build -t nama_image:tag
    
    <!--contoh-->
    docker build -t my-app:1.0
    ```
Menjalankan **react app** dengan container via dockerfile :
1. Siapkan project react
2. Siapkan dockerfile di dalam project react
3. Lengkapi dengan perintah berikut :
    ```sh
    FROM node:alpine
    WORKDIR /usn/src/app
    COPY..
    RUN npm install
    CMD ["npm", "start"]
    ```
4. Buat image dengan perintah berikut :
    ```sh
    docker build -t react-app:1.0 . 
    ```
5. Jalankan image yang sudah dibuat dengan menggunakan perintah berikut :
    ```sh
    docker run -d -p 3000:3000 react-app:1.0 
    ```

#### Docker Compose
**Docker compose** adalah cara untuk menjalankan lebih dari 1 container secara bersamaan dan saling terhubung. Adapun cara untuk menggunakan docker compose adalah sebagai berikut :
1. Buat file NAMA_FILE.yaml di dalam project yang sudah dibuat
2. Tuliskan beberapa perintah
3. Jalankan menggunakan perintah berikut :
    ```sh
    docker-compose NAMA_FILE.yaml up
    ```
