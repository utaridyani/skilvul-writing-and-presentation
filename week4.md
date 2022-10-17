# ASYNCRONOUS FETCH DAN ASYNC WAIT
---
Web dinamis pada umumnya akan berinteraksi dengan server menggunakan API. Jika kita ingin mengembangkan sebuah website menjadi bentuk mobile, kita juga bisa memanfaatkan API yang sama dengan yang kita gunakan pada websitenya.

API tersebut nantinya akan ditangkap menggunakan Promise. Berikut merupakan contoh kode penulisan object promise :
```sh
let nonton = (kondisi) => {
  return new Promise((resolve, reject) => {
    if (kondisi == "jalan") {
      resolve("nonton terpenuhi")
    }
    reject("batal nonton")
  })
}
```
Berikut merupakan cara pemanggilan object tersebut menggunakan promise (then catch) :
```sh
nonton("jalan")
.then(result => {
  console.log(result);
}).catch(err => {
  console.log(err)
})
```

#### Async Await
Cara menangkap dengan menggunakan Async Await adalah membuat terlebih dahulu functionnya. Pembuatan functionnya hampir sama dengan membuat function biasa hanya saja harus menambahkan keyword **async** di depannya. Jika function berupa arrow function maka keyword diletakkan di depan parameter. Berikut merupakan contoh penulisan kodenya :
```sh
async function asyncNonton() {
  try {
    let result = await nonton("jalan")
    console.log(result);
  } catch (error) {
    console.log(error)
  }
}
asyncNonton()
```

#### Fetch
Fetch adalah object promise yang disediakan oleh JavaScript. Cara menangkap Fetch masih sama seperti sebelumnya, yaitu menggunakan Then Catch atau Async Await. Berikut merupakan contoh penerapan Fetch :
```sh
fetch("https://digimon-api.vercel.app/api/digimon")
.then(result => result.json())
.then(result => {
  console.log(result)
})
```
Pada kode di atas merupakan penerapan **fetch** yang digunakan untuk mendapatkan data dari API digimon.

---
# GIT GITHUB LANJUTAN
---
Untuk berkolaborasi dengan teman dalam tim, kita bisa memanfaatkan fitur Organization yang dimiliki oleh Github. Pada organization, tim kita bisa membuat banyak repository yang nantinya bisa dikerjakan bersama-sama. Secara tidak langsung sebuah organization bisa disebut sebagai akun kelompok. 

Berikut merupakan step-step yang kita lakukan untuk berkolaborasi :
1. Membuat sebuah organization (bisa dilakukan oleh satu orang perwakilan saja / ketua kelompok)
2. Menginvite anggota kelompok
3. Memberikan access owner kepada anggota kelompok
4. Membuat repository untuk project yang akan dikerjakan pada Organization tersebut
5. Pastikan repository bersifat public
6. Membuat Branch. Branch main akan digunakan sebagai branch utama sedangkan branch baru adalah branch development dimana branch ini akan diupdate terus menerus saat masih ada perubahan yang akan dilakukan. Jika perubahan tersebut sudah selesai maka akan digabung ke branch utama (main)
7. Masing-masing anggota kelompok melakukan clone terhadap repository yang telah dibuat
8. Sebelum mulai ngoding setiap anggota kelompok harus melakukan pull untuk mendapatkan kode-kode yang sebelumnya.
9. Setiap anggota membuat branch dari branch baru yang sebelumnya telah dibuat (kita anggap namanya adalah dev). Penamaan branch dari masing-masing anggota bisa menyesuaikan. Contohnya adalah jika A mengerjakan fitur registrasi maka branchnya bisa namakan A_Registrasi.

Step-step yang harus dilakukan pada VSCode :
1. Setiap anggota harus pindah ke branch dev terlebih dahulu. Kode yang digunakan adalah sebagai berikut :
```sh
git switch dev

<!--atau-->
git checkout dev
```
2. Membuat branch baru dari dev, dimana branch ini akan digunakan untuk mendevelop sebuah fitur yang akan dikerjakan. Kode yang digunakan adalah sebagai berikut :
```sh
git branch namabranchbaru
```
3. Pindah ke branch yang baru. Kode yang digunakan adalah sebagai berikut :
```sh
git switch namabranchbaru
```
4. Mulai mengetik kode seperti biasa
5. Melakukan add dan commit seperti biasa
6. Sebelum melakukan push maka lakukan terlebih dahulu Dev Merge
7. Push
8. Pull Request, permintaan untuk menggabungkan branch kita dengan branch dev. Jika kira adalah seorang anggota maka harus memberi assign terlebih dahulu kepada leader yang membuat repository
9. Jika ingin menggabungkan data terbaru maka kita harus mengambil data dari dev lalu git merge dev.

---
# RESPONSIVE WEB DESIGN
---
**Responsive** adalah dimana sebuah website mungkin untuk diakses dari berbagai device dengan hasil tampilan yang masih bagus.

Cara membuat website menjadiresponsive :
1. Meta Viewport
2. Max-Width
3. Relative Unit
4. Media Query
5. Flex
6. Grid

**View Port** adalah area website yang bisa diakses oleh user. View port dapat diatur pada meta tag.

**Max-Width** merupakan cara untuk mengatur sebuah gambar menjadi responsive. Contohnya jika Max-Width dari sebuah gambar diatur menjadi 100% artinya tampilan gambar tersebut akan selalu 100% dari ukuran layar (view port).

**Relative Unit** adalah satuan unit yang bergantung pada sesuatu. Relative Unit yang sering dipakai adalah %, rem, em, vw, vh.
Berikut merupakan penjelasan dari relative unit yang sering dipakai :
1. % : mengikuti ukuran parent
2. em : mengkuti ukutan huruf dari elemen. Contohnya adalah jika elemen div memiliki ukuran font 12px dan elemen p didalamnya memiliki ukuran 2em, maka ukuran font pada elemen p tersebut adalah 24px.
3. rem : mengikuti ukuran huruf root elemen. Root elemen adalah html, jadi jika sebuah html memiliki ukuran huruf 12px dan elemen di dalamnya memiliki ukuran huruf 3rem maka ukuran asli dari huruf tersebut adalah 36px.
4. vw : mengikuti viewport

**Media Query** adalah salah satu penerapan relative yang akan menyesuaikan tampilan dengan ukuran layar. Berikut merupakan contoh penerapannya :
```sh
@media (max-width: 600px ) {
  .menu {
    display: none;
  }

  .toggle-menu {
    width: 40px;
    height: 40px;
    background: url(./menu.svg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: 30px;
    background-repeat: no-repeat;
  }
}
```
Kode tersebut akan berjalan jika ukuran lebar maksimal dari sebuah layar adalah sebesar 600px. Dimana jika ukuran layarnya 600px atau kurang maka website akan menampilkan sebuah toggle menu.

---
# BOOTSTRAP 5
---
Bootstrap adalah sebuah framework CSS untuk melakukan styling yang akan membantu kita untuk berkerja lebih cepat. 

Terdapat beberapa cara untuk menggunakan Bootstrap pada website kita adalah sebagai berikut :
1. Compile
2. Download Source File
3. CDN

**CDN** adalah cara termudah karena kita hanya perlu meng-copy CDNnya ke file kita. CDN ini akan dipasang pada **head** file HTML. Link CDN ini bisa didapatkan pada dokumentasi Bootstrap.

Untuk menggunakan item dari Bootstrap, kita hanya perlu mengcopy source code dari website bootstrap dan paste pada file HTML kita. Elemen tersebut juga bisa kita sesuaikan dengan kemauan kita sendiri.

#### Breakpoints Pada Bootstrap
1. Extra small dengan class infix None dan dimensi <576px
2. Small dengan class infix sm dan dimensi ≥576px
3. Medium dengan class infix md	dan dimensi ≥768px
4. Large dengan class infix lg dan dimensi ≥992px
5. Extra large dengan class infix xl dan dimensi ≥1200px
6. Extra extra large dengna class infix xxl dan dimensi ≥1400px

#### Container Pada Bootstrap
Container adalah komponen fundamental yang digunakan untuk membuat sebuah layout dimana jika kita ingin membuat sebuah layout kita bisa menggunakan container sebagai building block.

Container ini diperlukan jika kita ingin menggunakan sistem grid yang dimiliki oleh bootstrap.

Bootstrap menyediakan berbagai jenis ukuran untuk container, berikut merupakan beberapa di antaranya :
1. .container
2. .container-sm
3. .container-md
4. .container-lg
5. .container-xl
6. .container-xxl

Jenis-jenis container yang disebutkan sebelumnya memiliki breakpoint yang berbeda-beda, penjelasan lebih lanjut dapat kita baca pada dokumentasi bootstrap

#### Grid System pada Bootstrap
Grid System pada bootstrap merupakan komponen yang digunakan untuk membangun layout dengan berbagai bentuk dan ukuran. Grid System ini memiliki sistem 12 kolom. Grid System pada Bootstrap ini menggunakan konsep flexbox.

Berikut merupakan contoh grid system pada bootstrap yang akan menghasilkan 3 kolom yang memiliki ukuran yang sama.
```sh
<div class="container text-center">
  <div class="row">
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
  </div>
</div>
```
Berikut merupakan beberapa jenis pilihan Grid yang disediakan oleh Bootstrap :
1. Extra small (xs)
2. Small (sm)
3. Medium (md)
4. Large (lg)
5. Extra large (xl)
6. Extra extra large (xxl)