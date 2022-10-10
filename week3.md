# ARRAY
---
**Array** adalah tipe data list order yang dapat menyimpan banyak data dengan berbagai tipe data di dalamnya. Sebuah array bisa menampung banyak data yang terdiri dari tipe data string, number, boolean, dan lain sebagainya. Berikut merupakan contoh dari array :
```sh
let jenisPekerjaan = ['Guru', 'Dokter', 'Presiden']
```

#### Mendeklarasikan Array
Berdasarkan contoh di atas, dapat kita lihat cara **mendeklarasikan** sebuah array hampir mirip dengan cara mendeklarasikan sebuah variable, bedanya sebuah array harus menggunakan bracket atau simbol **[]**.

Untuk **memanggil** sebuah array juga hampir mirip dengan cara memanggil variable. Berikut merupakan cara untuk memanggil data dalam array :
- Memanggil seluruh data dalam array
Untuk memanggil seluruh data, kita bisa melakukannya sama dengan cara memanggil variable, yaitu sebagai berikut :
```sh
console.log(namaArray)
console.log(jenisPekerjaan)
```
- Memanggil salah satu data
Untuk memanggil salah satu data kita bisa menggunakan index. Index pada array dimulai dari 0. Dari contoh array di atas kita akan mengambil data dengan value 'Guru'. Data tersebut terdapat pada index 1. Maka cara untuk mengambil data tersebut adalah sebagai berikut :
```sh
console.log(namaArray[index])
console.log(jenisPekerjaan[1])
```

#### Update Array
- Jika menggunakan keyword let, kita dapat mengubah array baik itu menambah data baru ataupun mengubah nilai yang telah terdapat pada array dengan nilai yang lain.
- Jika menggunakan keyword const, kita bisa mengubah nilai yang terdapat pada array dengan nilai lain tapi tidak bisa menambahkan nilai baru

Contoh cara untuk mengupdate array adalah sebagai berikut :
```sh
const jenisPekerjaan = ['Guru', 'Dokter', 'Presiden']

//mengubah nilai dari index 1
jenisPekerjaan[1] = "Pilot"

//menambahkan nilai
jenisPekerjaan = "Pramugari"
//akan menghasilkan error karena keyword yang digunakan adalah const
```

#### Properties
Array memiliki 5 properti yang sering digunakan, yaitu :
1. Constructor
2. Length
3. Index
4. Input
5. Prototype

.length merupakan properti yang digunakan untuk menghitung panjang array atau banyaknya data yang terdapat pada sebuah array. Berikut merupakan contoh penggunaannya :
```sh
console.log(jenisPerkerjaan.length) //output : 3
```

#### Method
Pada Javascript, array memiliki method atau yang disebut dengan built-in methods dimana dengan method tersebut JavaScript telah menyediakan function umum yang sering kita gunakan sehingga kita tidak perlu membuat function sendiri lagi. Berikut merupakan beberapa Built-in Method pada Array :
- **push()**
Push adalah method untuk menambahkan data pada akhir array.
```sh
let jenisPekerjaan = ['Guru', 'Dokter', 'Presiden']

jenisPekerjaan.push('Pilot')
console.log(jenisPekerjaan)

<!--Output :-->
<!--['Guru', 'Dokter', 'Presiden', 'Pilot']-->
```
- **pop()**
pop adalah method yang digunakan untuk menghapus atau mengeluarkan data dengan index terakhir pada sebuah array.
```sh
let jenisPekerjaan = ['Guru', 'Dokter', 'Presiden', 'Pilot']

jenisPekerjaan.pop()
console.log(jenisPekerjaan)

<!--Output :-->
<!--['Guru', 'Dokter', 'Presiden']-->
```
- **shift()**
shift merupakan method yang digunakan untuk menghapus data yang terdapat pada index pertama.
```sh
let jenisPekerjaan = ['Guru', 'Dokter', 'Presiden']

jenisPekerjaan.shift()
console.log(jenisPekerjaan)

<!--Output :-->
<!--['Dokter', 'Presiden']-->
```
- **unshift()**
unshift merupakan method yang digunakan untuk menambahkan data pada index pertama.
```sh
let jenisPekerjaan = ['Dokter', 'Presiden']

jenisPekerjaan.unshift('Pilot')
console.log(jenisPekerjaan)

<!--Output :-->
<!--['Pilot', 'Dokter', 'Presiden']-->
```
- **sort()**
sort merupakan method yang digunakan untuk mengurutkan data secara Ascending atau Descending Alphanumeric.
```sh
let angka = [1, 4, 2, 3]

angka.sort()
console.log(angka)

<!--Output :-->
<!--[1, 2, 3, 4]-->
```
#### Looping pada Array
Untuk melakukan looping pada array, terdapat 2 built-in method yang bisa digunakan, yaitu **forEach()**  dan **map()**
- **forEach()**
Method ini digunakan jika kita ingin melakukan perulangan pada setiap elemen dalam array
```sh
let angka = [1, 4, 2, 3]

angka.forEach()(element =>{
    console.log(element)
})

<!--Output :-->
<!--[1, 4, 2, 3]-->
```
- **map()**
Digunakan untuk melakukan perulangan yang hasilnya akan membuat array baru
```sh
let angka = [1, 4, 2, 3]

let doubled = angka.map(num =>{
    return num*2
})

console.log(doubled)

<!--Output :-->
<!--[2, 8, 4, 6]-->
```

**Tips**
>Gunakan forEach() hanya jika memerlukan looping untuk menampilkan atau menyimpan data ke dalam database. Gunakan map() jika ingin melakukan operasi pada array. 

---
# OBJECT
---

**Object** merupakan sebuah tipe data yang dapat menyimpan properti dan method. Properti adalah data yang dimiliki oleh sebuah object sedangkan Method merupakan hal yang dapat dilakukan oleh object tersebut.

Mirip seperti array, object diassign pada sebuah variable dan dapat menampung data yang memiliki berbagai tipe data primitive. Berikut merupakan contoh cara mendeklarasikan sebuah object.
```sh
let namaObject = {
    key1 : value,
    key2 : value,
}

let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
    <!--jika nama properti terdapat spasi maka gunakan tanda petik dalam penulisannya-->
}
```

#### Mengakses Sebuah Object
Untuk mengakses seluruh value dari sebuah object, kita bisa melakukan dengan cara berikut :
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
}

console.log(mahasiswa)
```

Untuk mengakses salah satu key, maka cara yang digunakan adalah sebagai berikut :
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
}

console.log(mahasiswa.nim)
<!--output : 200555100-->
```

Selain itu, juga terdapat cara lain untuk memanggil value dari sebuah key, yaitu menggunakan bracket notation seperti berikut :
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
}

console.log(mahasiswa['nim'])
<!--output : 200555100-->
```

#### Update Object
>Tips jika kedepannya kita mungkin banyak memerlukan atau mengupdate sebuah object, maka deklarasikan dia menggunakan **let**

Untuk **mengupdate** sebuah value, maka hal ini yang bisa kita lakukan :
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
}

mahasiswa.umur = 19
```

Untuk **menambah** key baru kita bisa melakukan hal ini :
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
}

mahasiswa.hobi = 'membaca'
```

#### Menghapus Sebuah Properti
Untuk menghapus sebuah properti kita bisa menggunakan operator delete. Berikut merupakan contoh penggunaannya.
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
    hobi : 'membaca'
}

delete mahasiswa.hobi;
<!--kode di atas digunakan untuk menghapus properti hobi-->
```

#### Nested Object
Nested object merupakan object yang terdapat di dalam sebuah object. Berikut merupakan contoh dari nested object.
```sh
let mahasiswa = {
    nim : 200555100
    nama : 'Ni Putu Utari Dyani Laksmi'
    umur : 20
    'golongan darah' : '0' 
    kendaraan : {
        motor : 'scoopy'
        perusahaan : 'honda'
    }
}
```
Untuk memanggil nama motor yang digunakan oleh mahasiswa tersebut maka syntax yang kita gunakan adalah sebagai berikut:
```sh
console.log(mahasiswa.kendaraan.motor)
```

#### Pass By Reference
Yang dimaksud dengan pass by reference adalah mengubah data yang terdapat pada sebuah objecr melalui sebuah function dan memasukkan object sebagai parameter function. Berikut merupakan contoh dari pass by reference :
```sh
let angka = {
    angka1 = 1,
    angka2 = 2,
}

function changeData(obj){
    obj.angka1 = 2
    obj.angka2 = 4
}
changeData(angka)
```

#### Looping Object
Untuk melakukan looping pada object, kita bisa menggunakan **for in**.
Berikut merupakan contoh penggunaanya.
```sh
let angka = {
    angka1 = 1,
    angka2 = 2,
}

for(let data in angka){
    console.log(angka[data])
}
```

#### Array of Object
Object sama seperti Array yang bisa menyimpan banyak data. Kita dapat menggunakan array of object untuk data yang lebih dari satu. Berikut merupakan contoh dari array of object.
```sh
let mahasiswa = [
    {
        nim : 200555100
        nama : 'Ni Putu Utari Dyani Laksmi'
        umur : 20
    },
    {
        nim : 200555101
        nama : 'Ni Putu Utari Dyan'
        umur : 21
    },
    {
        nim : 200555102
        nama : 'Ni Putu Utari'
        umur : 20
    }
]
```

---
# REKURSIF & MODULES
---
**Modules** pada JavaScript adalah sebuah cara untuk memisahkan kode ke file yang berbeda. Keuntungan dalam penggunaan module adalah file lebih mudah dibaca karena kode tidak menumpuk pada satu file dan lebih mudah untuk mengelola kode. 

Terdapat 2 istilah yang umum pada module, yaitu :
1. **Import**, yaitu mengambil data dari file lain.
2. **Export**, yaitu memberi data kepada file lain.

Beberapa hal yang perlu diperhatikan mengenai module adalah sebagai berikut :
- Untuk menggunakan module, kita harus menambahkan type="module" pada script utama.
- Terdapat 2 jenis export, yaitu export default (ditangkap tidak menggunakan kurung kurawal) dan export sekunder yang penulisannya menggunakna kurung kurawal. 
- Terdapat banyak hal yang bisa di-export, yaitu function, variable, class, dan lain sebagainya. 
- Module tidak bisa diexport sekaligun, melainkan harus satu persatu
- File yang terpasang pada script HTML hanya bisa melakukan import (tidak bisa export)
- Import default diletakkan di awal dan setelah itu baru dilanjutkan dengan import sekunder

Berikut merupakan contoh penggunaan module :
- File HTML
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
  <script src="./indonesia.js" type="module"></script>
</body>
</html>
```
- File Utama (Melakukan Import) - indonesia.js
```sh
import { motor as motorJepang, smartPhoneJepang} from "./jepang.js"
```
- File Kedua (Melakukan Export) - jepang.js
```sh
let motor = ["suzuki", "yamaha", "honda", "kawasaki"]
const smartPhone = ["sony", "samsung", "fujitsu", "LG"]

export { motor, smartPhone as smartPhoneJepang}
```
**Rekursif** merupakan fungsi yang memanggil dirinya sendiri secara terus menerus sampai pada kondisi tertentu.

Ciri-ciri rekursif :
1. Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
2. Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

Bagian-bagian dari rekursif adalah sebagai berikut :
1. **Base case**, yaitu titik paling kecil dimana perulangan akan berhenti
2. **Recursion case**, yaitu titik dia memanggil dirinya sendiri

Contoh rekursif adalah sebagai berikut :
- Fungsi rekursif untuk menghitung bilangan faktorial
> Contoh : 5! = 5 x 4 x 3 x 2 x 1

```sh
function faktorial(n) {
  if (n == 1) {
    return 1
  } else {
    return n * faktorial(n - 1)
  }
}
console.log(faktorial(5))
```
Berdasarkan kode di atas, function tersebut akan terus berulang hingga mencapai base case yang bernilai 1. Selama belum mencapai angka 1 maka fungsi tersebut akan terus mengalikan nilai n dengan hasil dari pemanggilan fungsi tersebut yang parameternya adalah n-1.

---
# ASYNCRONOUS
---

Pada umumnya sebuah kode akan dibaca dari atas ke bawah secara berurutan. Namun, **Asyncronous** merupakan pembacaan kode secara tidak berurutan. Hal tersebut dikarenakan terdapat beberapa proses yang memakan waktu lumayana lama. Agar tidak terlalu memakan waktu maka proses bisa dilanjutkan di tahap berikutnya terlebih dahulu. Contohnya adalah Web API. Jenis-jenis WEB APIs biasanya memerlukan waktu untuk berjalan, jadi bersifat asyncronous.

Terdapat beberapa istilah yang penting untuk dipahami dalam belajar asyncronous, yaitu :
- JS Single thread : satu antrian
- JS multi thread : banyak antrian
- JS Non-blocking : kalau dalam antrian dia merasa prosesnya lama, maka dia akan mengalah terlebih dahulu
- JS Blocking : proses tidak boleh disela
- JS Syncronous : eksekusi berurutan
- JS Asyncronous : eksekusi tidak berurutan, prosesnya bisa disela dan dia akan memanggil proses berikutnya yang belum dijalankan

Terdapat 3 cara yang dapat digunakan untuk **menghandle** Asyncronous, yaitu :
1. **Callback**, yaitu function yang kita letakan di dalam argumen/parameter pada function, dan function tersebut akan dieksekusi setelah function pertama menyelesaikan tugasnya.
2. **Promise**, yaitu fitur baru di ES6, biasa digunakan untuk melakukan http request/fetch data dari API. Dalam pengambilan data, promise memiliki 3 kemungkinan state, yaitu Pending(sedang dalam proses), Fulfilled (berhasil), dan Rejected (gagal).
3. **Async / Await**, yaitu salah satu fitur baru dari javascript yang digunakan untuk menangani hasil dari sebuah Promise.

Berikut merupakan contoh penggunaan **Promise** :
```sh
<!--Membuat promise-->
let nontonPromise = new Promise((resolve, reject) => {
  if (true) {
    <!--jika berhasil-->
    resolve("nonton terpenuhi") 
  } 
  <!--jika gagal-->
  reject("gagal");
});

<!--eksekusi-->
nontonPromise
  .then((result) => {
    console.log(result);
    return `${result} berhasil`
  })
  .then((result) => {
    console.log(result)
  })
  .catch((err) => {
    console.log(err);
  });
```
setTimeout digunakan untuk simulasi asynchronous. Karena sebenarnya kita tidak bisa membuat proses asynchronous murni.

---
# WEB STORAGE
---
**Cookies** merupakan data kecil yang dikirim dari situs web dan disimpan di komputer kita oleh web browser saat kita menjelajah. Disebut data kecil karena maksimum data yang dapat disimpan dalam cookies adalah 4096 bytes (4 KB).

Beberapa hal penting yang perlu diperhatikan mengenai cookies, yaitu :
1. Setiap kali mengakses sebuah situs maka cookies akan kembali dikirim sehingga akan memperlampat aplikasi website karena dia akan mengirimkan data yang sama.
2. Cookies disertakan pada setiap HTTP request sehingga mengirimkan data yang tidak dienkripsi melalui internet. Oleh karena itu, jika ingin menyimpan data dalam cookies kita harus mengenkripsinya terlebih dahulu.
3. Cookies maksimal menyimpan data sebesar 4KB.
4. Cookies memiliki tanggal expired.

Berdasarkan beberapa kekurangan cookies tersebut, kita bisa menutupinya menggunakan **web storage**.

#### Local Storage
Karakteristik local storage :
1. Menyimpan data tanpa tanggal kadaluarsa.
2. Data tidak akan dihapus ketika web browser ditutup dan akan tersedia seterusnya selama kita tidak menghapus data local storage pada web browser.
3. Dapat menyimpan data hingga 5MB.
4. Hanya dapat menyimpan data string.

Untuk **menyimpan** data pada local storage, kita menggunakan method setItem() yang membutuhkan 2 parameter. Parameter pertama adalah key yang ingin kita simpan dan parameter kedua adalah data (value) dari key yang akan disimpan. Berikut merupakan syntax penulisan untuk menyimpan data pada local storage :
```sh
localStorage.setItem('key', value);
```

Sedangkan untuk **mengambil** data yang telah tersimpan pada local storage, kita dapat menggunakan method getItem() yang membutuhkan 1 parameter. Parameter tersebut adalah key dari data yang kita inginkan. Berikut merupakan syntax penulisan untuk mengambil data dari local storage :
```sh
localStorage.getItem('key');
```

Dam terakhir, untuk menghapus data yang telah tersimpan pada local storage, kita dapat menggunakan method removeItem() yang membutuhkan 1 parameter. Parameter tersebut adalah key dari data yang ingin kita hapus. Berikut merupakan syntax penulisan untuk menghapus data yang tersimpan pada local storage :
```sh
<!--menghapus key tertentu-->
localStorage.removeItem("key");

<!--enghapus seluruh key-->
localStorage.clear();
```
#### Session Storage
Karakteristik session storage :
1. Data yang disimpan pada session storage akan terus tersimpan selama browser terbuka dan tidak hilang jika laman di-reload.
2. Membuka banyak tab/window dengan URL yang sama, akan menciptakan session storage yang berbeda di masing-masing tab/window.
3. Menutup tab/window akan mengakhiri session dan menghapus data yang tersimpan di session storage pada tab/window tersebut.
4. Data yang tersimpan dalam session storage harus berbentuk string.
5. Hanya dapat menyimpan data sebanyak 5MB.

Untuk menyimpan, mengambil dan menghapus data dari session storage kita perlu menggunakan syntax yang hampir sama dengan local storage. Perbedaannya hanya terletak pada keyword pertama, jika session storage maka menggunakan keyword **sessionStorage**. Berikut merupakan syntax penulisan dari session storage :
```sh
<!--menambah session storage-->
sessionStorage.setItem('key', value);

<!--mendapatkan session storage-->
sessionStorage.getItem('key');

<!--menghapus session storage satu persatu berdasarkan key-->
sessionStorage.removeItem('key');

<!--menghapus seluruh session storage sekaligus-->
sessionStorage.clear();
```