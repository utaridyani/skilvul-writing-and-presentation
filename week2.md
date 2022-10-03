# SCOPE
---

**Scope** merupakan konsep flow variable dimana akan ditentukan variable tersebut bisa diakses oleh scope yang mana saja. Sedangkan blocks adalah kode yang terdapat di dalam tanda **{}**.

Ada 2 jenis scope, yaitu :
1. **Global Scope** yaitu scope yang memungkinkan variable yang kita deklarasikan bisa diakses oleh seluruh bagian kode dalam suatu file. Pada global scopr, variable di deklarasikan diluar blocks.
Berikut merupakan contoh Global Scope :
```sh
let words = "halo"

function greet(){
    return words
}

console.log(greet) //menampilkan halo
```
2. **Local Scope** yaitu scope yang memungkinkan variable bisa diakses oleh sebuah block dimana variable tersebut dideklarasikan.
Berikut merupakan contoh Local Scope :
```sh
function greet(){
    let words = "halo"
    return words
}

console.log(greet) //menampilkan halo
```

Jika sebuah variable dideklarasikan di dalam sebuah block tapi dipanggil di blok lain maka akan mengghasilkan error atau variable tersebut tidak dapat diakses. Berikut adalah contohnya :
```sh
function greet(){
    let words = "halo"
    return words
}

function greet2(){
    return words
}
console.log(greet2) //menampilkan Uncaught ReferenceError: words is not defined
```
**Error** tersebut muncul dikarenakan variable word terletak pada block function greet dan menyebabkan variable tersebut tidak bisa diakses oleh function atau block lainnya. Agar variable tersebut bisa diakses oleh blocks lainnya maka variable tersebut bisa dideklarasikan di luar blocks (global scope)

---
# FUNCTION
---
**Function** adalah kumpulan kode yang menjalankan perintah tertentu dan bisa dipanggil atau digunakan berulang kali.

#### Struktur Function
```sh
keyword identifier(parameter){
    kode yang akan dijalankan
}
```
Keyword yang digunakan untuk membuat function adalah **function** dan identifier adalah nama dari function yang akan dibuat. Parameter adalah jenis input yang diperlukan oleh sebuah function. Seluruh kode yang akan dieksekusi oleh sebuah function terletak pada body (di dalam tanda {}). Berikut merupakan contoh deklarasi sebuah funtion :
```sh
function luasPersegi(sisi){
    return sisi*sisi
}
```

#### Memanggil Function
Berikut merupakan sintaks yang digunakan untuk memanggil sebuah function
```sh
luasPersegi(5) //memanggil sebuah fungsi dan melemparkan argumen ke dalamnya
console.log(luasPersegi(5)) //menampilkan hasil dari sebuah fungsi dengan nama luasPersegi dan melemparkan argumen dengan value "5" ke dalamnya.
```

#### Parameter dan Argumen
**Parameter** merupakan jenis inputan yang diperlukan dan bisa diterima oleh sebuah function untuk melakukan sebuah tugas. 

Sedangkan **Argumen** adalah nilai atau data yang dimasukkan ke dalam sebuah function untuk di proses. Jumlah argumen harus sama dengan jumlah parameternya. Berikut merupakan contoh penggunaan parameter dan function.
```sh
function luasPersegiPanjang(panjang, lebar){
    return panjang*lebar
}

console.log(luasPersegiPanjang(2, 5)
```
Parameter dari kode di atas adalah panjang dan lebar, sedangkan argumennya adalah 2 dan 5.

#### Default Parameter
Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function. Default parameters bisa digunakan jika kita ingin menjaga function agar tidak error saat dipanggil tanpa argumen. Berikut merupakan contoh penggunaan Default Parameter :
```sh
function greet(words = "mr/ms"){
    return "hi" + words;
}

//jika user memberikan argumen
console.log(greet("utari")); //hi utari

//jika user tidak memeberikan argumen
console.log(greet()); //hi mr/ms
```

#### Function Helper
Yang dimaksud dengan function helper adalah kita bisa menggunakan function yang sudah dibuat pada function lain. Berikut merupakan contoh penerapannya :
```sh
function luasPersegi(panjang, lebar){
    return panjang*lebar;
}

function volumeBalok(tinggi){
    //memanggil fugsi luas persegi
    return luasPersegi*tinggi;
}

//panjang = 2
//lebar = 3
console.log(volumeBalok(2)) //12
```

#### Arrow Function
Arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version). Berikut merupakan contoh penulisan kode menggunakan Arrow Function.
```sh
//tanpa argumen
const greet = () =>{
    return "Selamat Pagi";

//contoh dengan argumen
const luasPersegiPanjang = (panjang, lebar) => {
    return panjang*lebar
}
}
```

---
# BUILT IN DATA TYPES
---

JavaScript memiliki tipe data primitif dan non primitif. Tipe data primitif pada JavaScript adalah sebagai berikut :
1. String
2. Number
3. BigInt
4. Boolean
5. Undefined
6. Null
7. Symbol

Sedangkan tipe data non primitif pada JavaScript adalah sebagai berikut :
1. Array
2. Object

#### Dinamic Language
JavaScript merupakan bahasa pemrograman yang bersifat dinamis karena variable pada JavaScript tidak terikat pada satu jenis tipe data dan bisa diubah tipe datanya menjadi tipe data lain. Contohnya adalah sebagai berikut :
```sh
let testing = 1; //number
testing = "satu"; //menjadi string
testing = true; //menjadi boolean
```

#### Mengecek Tipe Data
Jika kita tidak mengetahui tipe data dari sebuah variable kita bisa menggunakan **typeof**. Berikut merupakan contoh penggunaannya :
```sh
let testing = 1;
typeof testing //number
```

#### String
==**Menghitung Jumlah Karakter String**==
Jika kita ingin mengetahui jumlah karakter dari sebuah string ataupun tipe data lainnya, kita bisa menggunakan **length**. Berikut merupakan contoh penggunaanya :
```sh
let testing = "satu";
console.log(testing.length) //4
```

==**Mengubah String menjadi Uppercase**==
Jika kita ingin mengubah sebuah string menjadi Uppercase, kita bisa menggunakan properties **toUpperCase**. Berikut merupakan contoh pengguanaannya :
```sh
let testing = "satu";
console.log(testing.toUpperCase()) //SATU
```

==**Mengubah String menjadi Lowercase**==
Jika kita ingin mengubah sebuah string menjadi Lowercase, kita bisa menggunakan properties **toLowerCase**. Berikut merupakan contoh pengguanaannya :
```sh
let testing = "SATU";
console.log(testing.toLowerCase()) //satu
```

==**Mengambil Salah Satu Karakter String**==
Jika kita ingin mengambil sebuah karakter dari sebuah string, kita bisa menggunakan properties **charAt**. Properties ini akan mengambil karakter berdasarkan index dari karakter tersebut. Index dari sebuah string dimulai dari 0 sampai dengan length-1. Berikut merupakan contoh dari penggunaannya :
```sh
let testing = "SATU";
console.log(testing.charAt(1)) //A
console.log(testing[1]) //A
```

==**Mencari Sebuah Karakter**==
Jika kita ingin mengetahui apakah sebuah data memiliki huruf tertentu, kita bisa menggunakan properties **includes**. Berikut adalah contoh penggunaanya, kita akan  mencoba mencari huruf A pada kata satu.
```sh
let testing = "SATU";
console.log(testing.includes("A")) //true
```

==**Mengubah String menjadi Array**==
Jika kita ingin mengubah sebuah string menjadi array, kita bisa menggunakan properties **split**. Berikut adalah contoh penggunaanya :
```sh
let testing = "Ini adalah percobaan untuk writing test";
const test = testing.split(" ")
console.log(test[1]) //adalah
```

#### Number
Value atau tipe data lain bisa diubah menjadi number dengan menggunakan **Number**. Berikut merupakan contoh penggunaannya :
```sh
let testing = "123"; //string 123
console.log(Number(testing)); //number 123
```

==**Mengecek Apakah Sebuah Data Adalah Number**==
Untuk mengecek sebuah data apakah number atau tidak kita bisa menggunakan **NaN** (Not-A-Number). Properties ini akan mereturn true apabila data tersebut bukanlah number dan akan mereturn false apabila data tersebut adalah number. Berikut merupakan contoh pengguanaannya :
```sh
console.log(isNaN(123)) // false
console.log(isNaN("satu")) // true
```

==**Mengubah Penulisan Angka**==
Untuk mengubah angka desimal yang memiliki angka dengan koma. Kita bisa menggunakan **toFixed** untuk menentukan berapa angka dibelakang koma yang ingin kita tulis. Berikut merupakan contohnya :
```sh
let angka = 3.12345

//satu angka di belakang koma
console.log(angka.toFixed(1)) // 3.1

//satu angka di belakang koma
console.log(angka.toFixed(2)) // 3.12
```

#### Math
Math merupakan sebuah built-in object yang memiliki properti dan method untuk mengoperasikan operasi matematika.

**Properties** yang dimiliki oleh Math contohnya adalah **Math.PI** yang merepresentasikan bilangan 3.14. Bilangan ini digunakan dalam operasi matematika untuk lingkaran dan bola

Adapun **Method** yang dimiliki oleh Math contohnya adalah :
```sh
//Menambilkan nilai absolute dari sebuah angka (nilai positive dari angka yang negatif)
console.log(Math.abs(-5)) // 5

//Pembulatan bilangan ke atas
console.log(Math.ceil(5.2)) // 6

//Pembulatan bilangan ke bawah
console.log(Math.floor(5.6)) // 5

//Pembulatan ke bilangan terdekat
console.log(Math.round(5.6)) // 6
console.log(Math.round(5.2)) // 5

//Menampilkan angka random di antara 0 dan 1
console.log(Math.random()) // 0.123342
```

#### Prototype
Dengan menggunakan prototype, kita bisa membuat method baru untuk mengoperasikan data sesuai dengan yang kita inginkan. Berikut adalah salah satu prototype yang dibuat untuk memanipulasi string dimana method yang dibuat akan mengubah urutan sebuah string dari akhir ke awal (reverse).
```sh
// method baru
String.prototype.reverse = function(){
  let s = ""
  for (let i = String(this).length-1; i >= 0 ; i--) {
    s = s + String(this)[i]
  }

  return s
}

// penggunaan method
console.log("hallo".reverse())
console.log("selamat datang".reverse())
```

---
DOM

---

DOM adalah singkatan dari **Document Object Model**. Dengan adanya DOM ini, JavaScript diberi akses untuk membuat HTML menjadi dinamis, seperti:
1. Mengubah element HTML pada halaman website.
2. Mengubah attribute HTML pada halaman website.
3. Mengubah CSS style pada halaman website.
4. Menambah dan/atau menghapus element maupun attribute HTML.
5. Menambah HTML event (contoh: efek klik pada mouse, hover pada mouse, dan lain-lain) pada halaman website.
6. Berinteraksi dengan semua HTML event di website

Secara singkatnya DOM adalah jembatan supaya bahasa pemrograman dapat berinteraksi dengan HTML. Dengan adanya DOM, JavaScript dapat memanipulasi HTML.

#### DOM Manipulation
Berikut merupakan beberapa sintaks yang digunakan untuk memanipulasi HTML menggunakan DOM.

==**Mengambil Sebuah Elemen**==
Untuk mengambil sebuah elemen, kita bisa menggunakan **getElementById**
```sh
let app = document.getElementById("app")
```

==**Memberikan Konten**==
Untuk memberikan konten pada elemen yang sudah diambil, kita bisa menggunakan innerText dan innerHTML. innerText akan menyisipkan string atau text kedalam elemen tersebut, sedangkan innerHTML bisa menyisipkan tag HTML.
```sh
app.innerText = "apa kabs"
app.innerHTML = "<h1>Hallo</h1>"
```

==**Membuat Elemen Baru**==
Untuk membuat elemen baru, kita bisa menggunakan **createElement**
```sh
let p = document.createElement("p")

//menambahkan konten
p.innerText = "ini adalah paragraf"
```

==**Menambahkan Child ke Parent**==
Sintaks yang digunakan untuk menambahkan child ke parent adalah sebagai berikut :
```sh
app.append(p)

let p2 = document.createElement("p")
p2.innerText = "paragraf ke-2"
app.appendChild(p2)
```
Pada contoh di atas, terdapat 2 cara yang digunakan untuk menambahkan child ke parent, yaitu **append** dan **appendChild**. Perbedaan antara 2 hal tersebut adalah appendChild tidak bisa menginputkan data string.

==**Menghapus Elemen**==
Untuk menghapus sebuah elemen HTML, kita bisa menggunakan **remove**. Berikut merupakan contoh penggunaannya :
```sh
let end = document.getElementById("end")
end.remove()
```

```sh
let link = document.getElementsByClassName("link")[0]
```
Source code di atas merupakan sintaks untuk mengambil elemen pertama yang memiliki nama kelas "link".

==**Atribute**==
Sintaks untuk melihat list atribute :
```sh
console.log(link.attributes) // [] list attribute
```

Mengambil isi dari sebuah atribute :
```sh
console.log(link.getAttribute("href")); // ambil isi attribute
```

Menambahkan sebuah atribute :
```sh
link.setAttribute("id", "google") // add attribute
```

==**Memberikan Style**==
Dengan menggunakan DOM, kita juga bisa memanipulasi style dari setiap elemen HTML. Berikut merupakan yang beberpaa yang sering digunakan, yaitu **color** untuk merubah warna, **border** untuk mengatur border, **padding** untuk mengatur padding, **backgroungColor** untuk menambahkan warna pada background.
```sh
link.style.color = "black"
link.style.border = "1px solid black"
link.style.padding = "5px 20px"
link.style.backgroundColor = "aqua"
```

==**Mengambil Style**==
Untuk mengambil dan melihat style dari sebuah elemen HTML, kita bisa menggunakan method getComputedStyles.
```sh
let tess = document.getElementById("tess")
let tessStyle = getComputedStyle(tess)
console.log(tessStyle.height)
```

==**Class**==
Sintaks yang digunakan untuk mengakses kelas, mengecek list kelas yang tersedia, menambahkan kelas, dan juga remove atau menghapus elemen juga bisa dilakukan oleh DOM. Berikut merupakan contoh penggunaan sintaksnya :
```sh
let container = document.getElementsByClassName("container")[0]
console.log(container.classList); // [] list of class
container.classList.add("home") // menambahnkan class
container.classList.remove("container") // menghapus class
```

#### DOM Events
Event adalah kegiatan/interaksi yang terjadi pada suatu website. Beberapa jenis events yang sering digunakan adalah :
1. click
2. submit
3. focus
4. blur
5. hover
6. change
7. scroll

==**Menambahkan Events**==
Untuk menambahkan events ke dalam HTML, kita bisa menggunakan 3 cara, yaitu :
1. HTML Atribute
2. Event Property
3. addEventListener()

==**Contoh**==
Berikut merupakan contoh penerapan **addEventListener** pada HTML dan JavaScript.
HTML :
```sh
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>

  <script src="counter.js" defer></script>
</head>
<body>
  <div>
    <button id="decrement">-</button>
    <span id="counter">0</span>
    <button id="increment">+</button>
  </div>
  
</body>
</html>
```

JavaScript :
```sh
let btnDecrement = document.getElementById("decrement")
let btnIncrement = document.getElementById("increment")
let counter = document.getElementById("counter")

let angka = 0

btnIncrement.addEventListener("click", function() {
  angka = angka + 1
  counter.innerText = angka
})

btnDecrement.addEventListener("click", function() {
  angka--
  counter.innerText = angka
})
```
Pada file JavaScript di atas, terdapat addEventListener() yang akan dipanggil ketikan btnIncrement (button dengan ID increment) mendapatkan event berupa "click". Maka hal yang terjadi pada tampilan website saat button increment diklik adalah muncul string "angka" pada counter (elemen HTML yang memiliki ID counter)

Selain itu, Events juga bisa diletakkan langsung pada elemen HTML. Berikut merupakan contoh penggunaan cara ini :
```sh
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>

  <script src="index.js" defer></script>
</head>
<body>
  <h1 onclick="alert('selamat datang')">Hallo</h1>

  <p id="paragraf">click me</p>

  <button id="btn">klik saya</button>

</body>
</html>
```
Berdasarkan kode di atas, pada saat tulisan Hallo di-click maka akan muncul alert dengan tulisan "selamat datang"

Sedangkan cara ke 2 yaitu **Event Property**, kita bisa menggunakan cara di bawah :
```sh
let paragraf = document.getElementById("paragraf")

paragraf.onclick = function () {
  alert("ini dari paragraf")
}

// paragraf.onclick = tampilkanAlert
function tampilkanAlert () {
  alert("ini alert")
}
```
