# MYSQL
----
**Database** merupakan tempat untuk menyimpan data dalam model kolom dan baris pada komputer atau bersifat elektronik. Untuk mengakses data, biasanya kita menggunakan yang namanya **DBMS** (Database Management Server). DBMS ini (yang saya pelajari) berbasis **SQL** (Standard Query Language).

**DBMS** yang akan saya gunakan sekarang adalah MySQL. Selain MySQL juga ada DBMS lainnya seperti :
1. Oracle
2. Postgre
3. IBM DB2 dan lain-lain

**MySQL** merupakan DBMS yang bersifat open source dan dapat berjalan stabil pada berbagai sistem operasi.

Hal yang harus diperhatikan sebelum menggunakan MySQL adalah memastikan sudah memiliki **MySQL Server**. Port MySQL Server umumnya adalah **3306**. Pastikan juga tidak ada running port yang berbentrokan dengan port MySQL Server.

#### Tipe Data
SQL memiliki beberapa tipe data, yaitu sebagai berikut : 
1. **Number**, tipe data ini akan menampung data. Contohnya adalah **integer, float**
2. **String**, tipe data yang akan menampung data berupa karakter baik satu maupun lebih dari satu. Contohnya adalah **char** (menampung satu karakter), **varchar** (menampung banyak karakter), dan **enum** (berupa pilihan)
3. **Boolean**, tipe data yang meanapung pilihan True/False
4. **Date time**, tipe data yang akan menampung data yang berkaitan dengan waktu. Contohnya adalah **DATE** untuk menyimpan tanggal, **TIME** untuk menyimpan waktu, dan **DATETIME** untuk menyimpan waktu dan tanggal.

#### Istilah Pada SQL
SQL memiliki beberapa istilah yang digunakan untuk mempermudah pembacaan data, yaitu :
1. **Table**, di dalam database akan terdapat kumpulan tabel yang dapat dibayangkan sebagai sebuah object.
2. **Field**, dapat dikatakan juga sebagai atribut atau kolom (kesamping) yang terdapat pada sebuah tabel.
3. **Record**, dapat dikatakan sebagai baris (ke bawah) yang akan menyimpan data pada sebuah tabel. Untuk mengetahui banyak data yang terdapat pada sebuah tabel, maka kita akan menghitung recordnya.

#### Perintah Dasar SQL
SQL memiliki 3 perintah dasar, yaitu :
1. **DDL** (Data Definition Language), digunakan untuk membuat tabel, menambahkan data, mengupdate data
2. **DML** (Data Manipulation Language), digunakan untuk memanipulasi tabel.
3. **DCL** (Data Control Language), digunakan untuk melakukan pengontrolan database dan server.

#### Query DDL (Data Definition Language)
1. **Membuat Database**
Berikut merupakan query yang digunakan untuk membuat database baru.
    ```sh
    create database nama_database;
    
    <!--contoh jika nama database yang ingin dibuat adalah db_toko-->
    create database db_toko;
    ```

2. **Menggunakan Database**
Berikut merupakan query yang digunakan untuk menggunakan sebuah database.
    ```sh
    use nama_database;
    
    <!--contoh jika nama database yang ingin digunakan adalah db_toko-->
    use db_toko;
    ```

3. **Menampilkan Seluruh Tabel**
Berikut merupakan query yang digunakan untuk menampilkan seluruh tabel pada database.
    ```sh
    show tables;
    ```

4. **Menampilkan Atribut Sebuah Table**
Berikut merupakan query yang digunakan untuk menampilkan atribut sebuah tabel.
    ```sh
    desc nama_table;
    
    <!--contoh jika nama tabel yang digunakan adalah user-->
    desc user;
    ```
    
5. **Menghapus Table**
Berikut merupakan query yang digunakan untuk menghapus sebuah tabel.
    ```sh
    drop table nama_table;
    
    <!--contoh jika nama tabel yang digunakan adalah user-->
    drop table user;
    ```

6. **Menambah Kolom**
Berikut merupakan query yang digunakan untuk menambahkan kolom pada sebuah tabel.
    ```sh
    alter table nama_tabel add nama_kolom_baru tipe_data;
    
    <!--contoh jika nama kolom baru yang ingin di tambahkan adalah email dengan tipe data varchar-->
    alter table user add email varchar(50);
    ```

#### Query DML (Data Manipulation Language)
1. **Menambahkan Data**
Berikut merupakan query yang digunakan untuk menambahkan data pada sebuah tabel.
    ```sh
    INSERT INTO students (nama, email, jurusan) VALUES
    ("utari", "utari@gmail.com", "TI"),
    ("dyani", "dyani@gmail.com", "TI);
    ```
2. **Melihat Data**
Berikut merupakan query yang digunakan untuk melihat data pada sebuah tabel.
    ```sh
    SELECT * FROM students;
    ```

3. **Mengubah Data**
Berikut merupakan query yang digunakan untuk mengubah data pada sebuah tabel.
    ```sh
    //mengubah data jurusan menjadi teknologi informasi pada data dengan id 1
    UPDATE students SET jurusan = "Teknologi Informasi" WHERE id = 1;
    ```sh
    
4. **Menghapus Data**
Berikut merupakan query yang digunakan untuk menghapus data pada sebuah tabel.
    ```sh
    DELETE student WHERE id = 9;
    ```

5. **Mengambil Data Menggunakan Alias**
Berikut merupakan query yang digunakan untuk mengambil data pada sebuah tabel dengan menampilkan kolom nama menjadi nama_mahasiswa.
    ```sh
    SELECT nama as nama_mahasiswa, jurusan FROM students;
    ```

6. **Mencari Data yang Mengandung Huruf / Karakter Tertentu**
Berikut merupakan query yang digunakan untuk mengambil data pada sebuah tabel yang memiliki nama berawalan huruf U.
    ```sh
    SELECT * FROM students WHERE nama like "U%";
    ```

7. **Menampilkan Data Berurutan**
Berikut merupakan query yang digunakan untuk menampilkan data pada sebuah tabel dengan urutan dari kecil - besar.
    ```sh
    SELECT * FROM student ORDER BY nama ASC;
    ```
    Selain itu, berikut merupakan query yang digunakan untuk menampilkan data pada sebuah tabel dengan urutan dari besar - kecil.
    ```sh
    SELECT * FROM student ORDER BY nama DESC;
    ```

----
# MYSQL LANJUTAN
----
MySQL memiliki beberapa jenis relasi antar tabel, yaitu :
1. **One to One**, artinya tabel tersebut memiliki satu sama lain. Jenis relasi ini jarang digunakan.
2. **One to Many**, artinya satu entitas / tabel memiliki banyak relasi. Jenis relasi ini paling sering digunakan.
3. **Many to Many**, artinya ada conjuction tambahan (tabel tambahan di dalamnya)

#### Normalisasi Database
**Normalisasi** adalah teknik analisis data yang mengorganisasikan atribut-atribut data dengan cara mengelompokkan sehingga terbentuk entitas yang non-redundant, stabil, dan fleksible. Normalisasi digunakan ketika adanya anomali pada sebuah data, baik itu insert anomali, delete anomali, atau update anomali. 

Tujuan dari normalisasi database adalah sebagai berikut : -
1. Menghilangkan redundan data pada database.
2. Memudahkan juka ada perubahan struktur table database.
3. Memperkecil pengaruh jika ada perubahan dari struktur table database.

Efek yang ditimbulkan jika kita tidak melakukan normalisasi adalah sebagai berikut :
1. Insert Anomali, yaitu situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
2. Delete Anomali, yaitu penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
3. Update Anomali, yaitu situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.

Bentuk-bentuk Normalisasi :
1. **First Normal Form (1NF)**
Bentuk normalisasi ini akan menghilangkan multiple value pada sebuah kolom table database. Sebuah table memenuhi kaidah 1NF jika setiap kolom bernilai tunggal (single value), setiap kolom memiliki nama yang unik, dan urutan penyimpanan data tidak menjadi masalah.
2. **Second Normal Form (2NF)**
Database harus sudah dalam bentuk 1NF untuk mendapatkan 2NF. Bentuk ini akan menghapus beberapa subset data yang ada pada tabel dan menempatkan mereka pada tabel terpisah.
3. **Third Normal Form (3NF)**
Bentuk ini akan menghilangkan seluruh atribut atau field yang tidak berhubungan dengan primary key. Dengan demikian tidak ada ketergantungan transitif pada setiap kandidat key.

#### Key pada MySQL
1. **Primary Key**, yaitu identitas dari sebuah row atau record
2. **Unique Key**, yaitu data yang bersifat unique
3. **Foreign Key**, yaitu primary key yang terdapat pada tabel lain

Berikut merupakan query yang digunakan untuk membuat query pada sebuah tabel
```sh
CREATE TABLE CATEGORY (
	id INT PRIMARY KEY NOT NULL AUTO_INCREMENT,
	nama VARCHAR(50)
);

CREATE TABLE product (
	id INT PRIMARY KEY NOT NULL AUTO_INCREMENT,
	nama VARCHAR(50),
	price INT,
	category_id INT,
	FOREIGN KEY (category_id) REFERENCES category(id)
);
```

#### Join
**Join** merupakan cara untuk mengambil records dari dua atau lebih table database yang memiliki relationship dan akan di sajikan dalam single result set. Terdapat beberapa jenis join, yaitu :
1. **Inner Join**, semua baris akan diambil dari kedua table yang akan di join, selama columns cocok dengan kondisi yang sudah di tentukan.Jenis join ini akan memungkinkan baris dari salah satu tabel muncul di hasil jika dan hanya jika kedua tabel memenuhi kondisi yang ditentukan dalam klausa ON.
2. **Left Join**,  semua records dari table di sisi kiri JOIN statement akan di pilih. Jika record yang di pilih dari table kiri tidak memiliki record yang cocok pada table JOIN yang kanan, maka record tersebut masih dipilih, dan kolom pada table yang kanan akan bernilai NULL. 
3. **Right Join**, semua records dari table di sisi kiri JOIN statement akan di pilih, bahkan jika table di sebelah kiri tidak memiliki record yang cocok.

Berikut merupakan contoh kode yang digunakan dengan menggunakan JOIN. Kode ini akan menampilkan id product, nama product, harga product, serta kategori product yang datanya diambil dari tabel kategori :
```sh
SELECT product.id, product.nama, product.price, category.nama AS kategori FROM product INNER JOIN category ON product.category_id = category.id;
```

#### Aggregate Function
**Aggregate Function** adalah mengambil satu nilai setelah melakukan perhitungan pada sekumpulan nilai. Terdapat beberapa jenis aggregate function, yaitu MAX (untuk mendapatkan nilai tertinggi), MIN (untuk mendapatkan nilai terendah), SUM (untuk menjumlahkan value), COUNT (menghitung jumlah row)
Berikut merupakan contoh dari aggregate function.
```sh
<!--Untuk menghitung total harga pada tabel product-->
SELECT SUM(price) as total_price FROM product;

<!--Untuk mencari harga tertinggi pada tabel product-->
SELECT MAX(price) AS max_price FROM product;

<!--Untuk menghitung jumlah setiap kategori-->
SELECT COUNT(category_id) FROM product GROUP BY category_id;

SELECT category.nama as category, count(category_id)
FROM product INNER JOIN category
ON product.category_id = category.id
GROUP BY category_id;
```

#### Union
Digunakan untuk menggabungkan kumpulan hasil dari dua atau lebih pernyataan select.  Setiap pernyataan SELECT dalam UNION harus memiliki jumlah kolom yang sama. Kolom juga harus memiliki tipe data yang serupa. Kolom dalam setiap pernyataan SELECT juga harus dalam urutan yang sama. Berikut merupakan contoh kode yang menggunakna UNION.
```sh
SELECT kota FROM mahasiswa UNION SELECT kota FROM user
```

#### Group By
Mengelompokkan baris yang memiliki nilai yang sama ke dalam baris ringkasan
Sering digunakan dengan fungsi agregat untuk mengelompokkan kumpulan hasil dengan satu atau lebih kolom. Berikut merupakan kode yang menggunakan GROUP BY.
```sh
SELECT category.nama as category, count(category_id)
FROM product INNER JOIN category
ON product.category_id = category.id
GROUP BY category_id;
```

#### Having
HAVING ditambahkan ke SQL karena kata kunci WHERE tidak dapat digunakan dengan aggregate functions. Berikut merupakan contoh kode yang menggunakan HAVING.
```sh
SELECT username, COUNT(id) FROM order GROUP BY username HAVING COUNT(username) > 1; 
```

#### Like and Wildcards
Operator LIKE digunakan dalam klausa WHERE untuk mencari pola tertentu dalam kolom. Sedangkan karakter wildcard digunakan untuk menggantikan satu atau lebih karakter dalam sebuah string.
Berikut merupakan contoh kode yang menggunakan like dan wildcards.
```sh
SELECT * FROM students WHERE nama LIKE "U%";
```
----
# AUTHORIZATION DAN AUTHENTICATION
--------------------------------------
#### Authorization
**Authorization** adalah menentukan izin untuk melakukan apa sajakah yang dimiliki oleh user. Jika user tidak memiliki izin untuk melakukan sebuah hal, maka response yang didapatkan adalah 403.


#### Authentication
**Authentication** adalah sebuah step yang dilakukan untuk mengecek identitas user. Jika identitas user tidak ditemukan pada database, maka responsenya adalah 401. Terdapat beberapa jenis Authentication, yaitu :
1. Session Based Authentication, session akan berisi beberapa data unik dari user untuk memungkinkan server melacak status user. Session Based Authentication akan memungkinkan status pengguna disimmpan dalam memori server atau database.
2. Token Based Authentication Using JWT (JSON Web Token), JWT merupakan self-contained JSON yang bisa membawa informasi kepada kedua belah pihak dengan aman karena JWT ini telah ditandatangani secara digital menggunakan pasangan kunci rahasia atau publik atau pribadi.
3. Password Authentication (Bcrypt), Bcrypt adalah sebuah algroritma hashing. Hash function berfungsi secara satu arah yang artinya setelah nilai di-hash, maka dia tidak akan bisa dikembalikan lagi. Hal inilah yang menyebabkan kita tidak dapat dengan mudah mengambil kata sandi plaintext tanpa mengetahui hal lainnya.

Berikut merupakan contoh kode untuk route authentication :
```sh
const express = require("express");
const router = express.Router();
const jwt = require("jsonwebtoken");

const users = [
  { id: 1, email: "dollong@gmail.com", password: "123" },
  { id: 2, email: "kiki@gmail.com", password: "123" },
];

const KEY = "asdfjsdaklf234234";

<!--http://localhost:3000/auth/login-->
router.post("/login", (req, res) => {
  const { email, password } = req.body;

  const userData = users.find(
    (item) => email === item.email && password === item.password
  );

  const token = jwt.sign(
    {
      id: userData.id,
    },
    KEY
  );

  if (userData) {
    res.json({
      message: "success login",
      token,
    });
  } else {
    res.status(401).json({
      message: "email or password are incorrect",
    });
  }
});

<!--http://localhost:3000/auth/register-->
router.post("/register", (req, res) => {
  res.json({
    message: "success regis",
  });
});

module.exports = router;
```

#### Encryption
**Encryption** adalah sebuah tools utama yang diperlukan untuk melakukan authentication dan authorization. Enkripsi adalah sebauh proses untun mentransformasi data kedalam sebuah format yang tidak bisa dibaca kecuali seseorang memiliki kunci yang tepat untuk melakukan dekripsi. Enkripsi dibedakan menjadi 2, yaitu Symmetric Encryption dan Asymmetric Encription.

-----
# SEQUELIZE
-----
**Sequelize** adalah framework yang menganut atau menerapkan konsep ORM (Object Relation Mapping). ORM adalah suatu metode atau teknik pemrograman yang digunakan untuk mengkonversi data dari lingkungan bahasa pemrograman berotientasi object (OOP) dengan lingkungan database relational.

Secara singkat, ORM adalah sebuah cara untuk mengkonversi data (table) yang kita miliki menjadi sebuah object.

**Kenapa ORM?**
- Memisahkan kode SQL dari logic aplikasi, kita tidak perlu memikirkan query SQL karena sudah ada method dan fungsi yang siap pakai yang akan melakukan hal yang sama dengan query SQL.
- Mempermudah maintenance
- Menghindari ketergantungan aplikasi terhadap vendor database. ORM akan menghindari ketergantungan atas database yang berbeda. Contohnya adalah jika kita ingin connect dengan MySQL, maka perlu library mysql2 dan jika ingin connect dengan PostgreSQL harus memiliki library pg. Dengan menggunaan ORM, kita tidak memerlukan library tersebut. ORM akan otomatis menyesuaikan query dan cara untuk connect dengan vendor yang diinginkan.

Terdapat 2 cara untuk menggunakan sequelize :
1. Dengan migration
2. Tanpa migration

**Tahapan Menggunakan Sequelize**
1. Install sequalize dan driver ke database punya kita (mysql2)
	``` npm install sequelize mysql2```
2. Install migrations (hitory perubahan pada table hal ini akan bermanfaat saat kita menemukan sebuah masalah pada database, kita bisa kembali ke versi sebelumnya)
	```npm install -D sequelize-cli ```
3. Inisialisai project (akan membuat folder config untuk settingan database, models untuk representasi table, migrations untuk tempat menyimpan perubahan pada table, seeders untuk tempat untuk data demo)
	```npx sequelize-cli init```
Pada configuration ada settingan untuk database yang akan disesuaikan dengan env node. Sesuaikan username, password, dan nama database dengan yang kalian miliki. Jika belum memiliki database, maka bisa menggunakan db:create.
Untuk membuat database, jalankan kode berikut :
```npx sequelize db:create```
Kode tersebut akan meng-create database yang telah dimasukkan namanya pada file configuration.
Untuk membuat file pertama sekaligus migrationnya, maka jalankan kode berikut :
```npx sequelize model:create --name User --attributes name:string,email:string,password:string```
4. Jalankan perintah yang sudah masuk migration sehingga tabel yang tadi dibuat masuk kedalam database
	```npx sequelize-cli db:migrate```
5. Jika ingin membatalkan bisa menggunakan undo (meng-undo model migration yang paling baru)
    ```npx sequelize-cli db:migrate:undo```
6. Menambahkan migration tanpa model baru
	```npx sequelize migration:create --name add-column-user```
Lalu pada file migration yang telah dibuat, tambahkan query yang diinginkan. Contohnya adalah addcolumn. pada async up
	```await queryInterface.addColumn(//nama tabel"Users", //nama kolom"username", //tipedata Sequelize.STRING)```
Jika tidak jadi di up, harus di remove dengan menambahkan kode beriikut pada async down
	```await.queryInterface.removeColumn("Users", "username")```
7. Menambahkan seeders
	```npx sequelize-cli seed:generate --name demo-user```
Datanya bisa dimasukkan pada folder seeders seperti berikut :
    ```sh
    await queryInterface.bulkInsert("Users", [
          {name: "utari", email:"utari@gmail.com", password: "utari", createdAt: new Date(), updatedAt: new Date()},
          {name: "dyani", email:"dyani@gmail.com", password: "dyani", createdAt: new Date(), updatedAt: new Date()}
        ])
    ```
8. Run Seeder untuk input data ke dalam database
	```npx sequelize db:seed --seed namaseed```
9. Masukan query pada router-> controller
**getAllUser**
    ```sh
    getAllUser: async (req, res) => {
    const user = await User.findAll()
    res.json({
         message: "succeed get data",
         data: user
        })
    }
    ```
    **getUserByID**

        ```
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