# [[Object Oriented Programming]]
	- Deskripsi:: Catatan komprehensif materi Pemrograman Berorientasi Objek menggunakan C#, mencakup dasar OOP, enkapsulasi, constructor, list, serialization, overloading, relasi antar-kelas, inheritance, dan polymorphism.
	- **Tags**: #OOP #CSharp #Programming #kuliah #semester2
	- ## 1. [[Intro to OOP]]
		- ### Apa itu OOP?
			- Teknik pemrograman di mana program bekerja melalui interaksi antar **objek** (seperti dunia nyata di mana mobil bisa bergerak karena interaksi mesin, ban, dsb).
			- **Keuntungan:** Lebih mudah dipahami, mudah di-maintenance, dan mudah digunakan kembali (*reusable*).
		- ### Konsep Dasar OOP
			- **Class:** Cetakan (*template* / *blueprint*) untuk membuat objek. Class mendefinisikan atribut dan perilaku.
			- **Object:** Instansi (wujud nyata) dari sebuah *Class*.
			- **Data Member (Field/Atribut):** Variabel di dalam class yang menyimpan status atau data (Contoh: `name`, `phoneNumber`, `balance`).
			- **Method:** Fungsi atau prosedur di dalam class yang mendefinisikan perilaku atau tindakan (Contoh: `Register()`, `TopUp()`, `Transfer()`).
		- ### Abstraction & Access Modifiers
			- Menyembunyikan kerumitan dan hanya menampilkan antarmuka yang dibutuhkan.
			- **Private:** Hanya bisa diakses dari dalam class itu sendiri. (Biasa digunakan untuk Data Member).
			- **Public:** Bisa diakses oleh class mana saja. (Biasa digunakan untuk Method dan Property).
			- **Protected:** Bisa diakses oleh class itu sendiri dan *child class* (kelas turunannya).
		- ### Properties (Properti)
			- Properti adalah cara aman (enkapsulasi) untuk membaca (`get`) atau menulis (`set`) nilai dari sebuah Data Member yang bersifat *private*.
			- **Read & Write Property:** Memiliki blok `get` dan `set`.
			- **Read-Only Property:** Hanya memiliki blok `get`. Data tidak boleh diubah dari luar, hanya bisa dibaca (Contoh: Poin, ID unik).
			- **Write-Only Property:** Hanya memiliki blok `set`. Data bisa dimasukkan tapi tidak boleh dibaca (Contoh: PIN, Password).
			- **Naming Convention:** Data Member menggunakan `camelCase` (misal: `ovoCash`), sedangkan Property dan Method menggunakan `PascalCase` (misal: `OvoCash`).
	- ## 2. [[Checking Properties, Exception & Error Handling]]
		- ### Mengapa Perlu Mengecek Properti?
			- Agar data yang dimasukkan ke dalam objek selalu valid (*Validasi Data*). Pengecekan dilakukan di dalam blok `set` pada Property, bukan langsung pada Data Member (*field*).
		- ### Menggunakan Exception
			- Jika validasi gagal, kita melempar (*throw*) sebuah error agar aplikasi tahu bahwa ada yang salah.
			- Sintaks: `throw new Exception("Pesan Error Anda");`
			- Pemanggilan pada form harus diapit dengan blok **`try-catch`** untuk menangkap error tersebut dan menampilkan pesan (*MessageBox*) tanpa membuat aplikasi *crash*.
			- ### 💡 Info Tambahan & Penyelesaian Masalah:
				- **Masalah:** Saldo (`ovoCash`) tidak boleh bernilai negatif dan tidak boleh diubah secara manual dari luar (harus read-only, tapi class butuh update saat top up).
				- **Penyelesaian:**
					- Buat properti dengan `private set`.
					- ```csharp
					  public int OvoCash { 
					      get => ovoCash; 
					      private set { 
					          if (value >= 0) { ovoCash = value; } else { ovoCash = 0; } 
					      } 
					  }
					  ```
					- Buat method `TopUp(int nominal)` untuk memanipulasi saldo tersebut.
	- ## 3. [[Constructors]]
		- ### Konsep Constructor
		- *Special method* yang digunakan untuk menginisialisasi nilai awal dari sebuah objek saat pertama kali dibuat.
		- **Ciri-ciri Constructor:** 1. Namanya harus **sama persis** dengan nama Class.
		  2. Tidak memiliki *return type* (bahkan tidak memakai `void`).
		  3. Dipanggil secara otomatis menggunakan *keyword* `new` (contoh: `new BankAccount()`).
		- ### Jenis-jenis Constructor
		- **Default Constructor:** Tidak memiliki parameter. Biasanya menginisialisasi dengan nilai kosong atau nilai standar. Jika tidak ditulis, C# membuatnya secara otomatis (selama tidak ada constructor lain).
		- **Parameterized Constructor:** Memiliki parameter. Memungkinkan kita mengirim data langsung saat objek dibuat (contoh: `BankAccount acc = new BankAccount("123", "Budi");`).
	- ## 4. [[List of Objects & BindingList]]
		- ### List of Objects
		- Digunakan untuk menyimpan banyak objek sejenis dalam satu wadah yang ukurannya dinamis (bisa bertambah/berkurang).
		- ### BindingList
		- Turunan dari list yang berfungsi sebagai mekanisme *two-way data-binding*.
		- **Kelebihan:** Jika ada objek yang ditambahkan, dihapus, atau diubah di dalam `BindingList`, elemen antarmuka pengguna (UI) seperti `ListBox` atau `DataGridView` yang terhubung akan **otomatis me-refresh/update** datanya.
		- Deklarasi: `BindingList<ClassName> listName = new BindingList<ClassName>();`
	- ## 5. [[Serialization & Deserialization]]
		- ### Konsep Dasar
		- **Serialization:** Mengubah objek (atau List of Objects) yang ada di memori RAM menjadi aliran *byte* (Stream of Bytes) agar bisa **disimpan ke dalam file** (Write/Save).
		- **Deserialization:** Mengubah kembali aliran *byte* dari file menjadi objek di memori RAM (Read/Load).
		- ### Syarat & Implementasi
		- Tambahkan atribut `[Serializable]` tepat di atas deklarasi `class`.
		- Namespace yang dibutuhkan: `using System.IO;` dan `using System.Runtime.Serialization.Formatters.Binary;`
		- ### 💡 Info Tambahan & Penyelesaian Masalah:
		- **Langkah Menyimpan File (Serialization):**
		  1. Gunakan `FileStream` (Mode `FileMode.Create`).
		  2. Siapkan `BinaryFormatter`.
		  3. Panggil `formatter.Serialize(fileStream, objekYangDisimpan)`.
		  4. Tutup `fileStream.Close()`.
		- **Masalah Visual Studio "Not Recognized":** Jika class Formatter tidak dikenali, arahkan kursor, klik *Show Potential Fixes*, dan otomatis tambahkan `using` namespace yang tepat.
	- ## 6. [[Method Overloading, Static Method, & Operator Overloading]]
		- ### Method Overloading
		- Membuat beberapa method dengan **nama yang sama** di dalam satu class, tetapi dengan **parameter yang berbeda** (*signature* berbeda: tipe, jumlah, atau urutannya).
		- **Tujuan:** Memberikan fleksibilitas. (Contoh: Method `Add(int a, int b)` dan `Add(double a, double b)`).
		- ### Static Method
		- Method yang menjadi milik **Class itu sendiri**, bukan milik objek.
		- Dipanggil langsung dari Class tanpa perlu membuat objek (*instantiate*) menggunakan `new`. Contoh bawaan: `Math.Sqrt()`.
		- Method static hanya bisa mengakses *member* class yang juga bersifat *static*.
		- ### Operator Overloading
		- Mendefinisikan ulang cara kerja operator standar (seperti `+`, `-`, `*`, `==`) untuk custom object (tipe data buatan sendiri).
		- Harus menggunakan tipe **`public static`** diikuti *keyword* `operator` lalu simbol operatornya.
		- **Penyelesaian Masalah:** Saat membuat `FractionalNumber` (Pecahan), kita tidak bisa langsung mengalikan objek `A * B`. Dengan Operator Overloading:
			- `public static FractNumber operator* (FractNumber num1, FractNumber num2)`
			- Didalamnya, kita kalikan pembilang dengan pembilang, penyebut dengan penyebut, lalu return objek hasilnya.
	- ## 7. [[Aggregation & Composition]]
		- ### Konsep Asosiasi (Hubungan Antar Kelas)
		- Dalam sistem nyata, sebuah class jarang berdiri sendiri. Mereka saling berinteraksi dan menggunakan objek dari class lain.
		- ### Aggregation (Agregasi)
		- Hubungan "Has-A" yang **TIDAK KUAT (Weak)**. Kelas anak bisa berdiri sendiri secara independen.
		- **Aturan:** Jika kelas Owner (*Parent*) dihapus, kelas anak (*Child*) **TIDAK ikut terhapus**.
		- **Contoh:** `Building` (Gedung) punya kumpulan `Location` (Alamat). Jika gedung dibongkar, lokasi/tanahnya tetap ada. `University` dan `Student`.
		- **UML:** Dilambangkan dengan garis berujung **Empty Diamond (Belah Ketupat Kosong)** di sisi Owner.
		- **Implementasi C#:** Objek anak dibuat di luar class parent, dan disuplai masuk (lewat parameter).
		- ### Composition (Komposisi)
		- Hubungan "Has-A" yang **SANGAT KUAT (Strong)**. Kelas anak bergantung mutlak pada keberadaan kelas Owner.
		- **Aturan:** Jika kelas Owner dihapus, kelas anak **IKUT TERHAPUS**.
		- **Contoh:** `Building` punya `Room` (Ruangan). Jika Gedung dihancurkan, ruangannya ikut hancur.
		- **UML:** Dilambangkan dengan garis berujung **Filled Diamond (Belah Ketupat Penuh)** di sisi Owner.
		- **Implementasi C#:** List of Child atau objek anak diinisialisasi (`new List()`) secara eksklusif *di dalam* Constructor parent-nya. Anak tidak diekspos secara bebas (*Private Set*).
	- ## 8. [[Inheritance]]
		- ### Konsep "Is-A" Relationship
		- Mengizinkan sebuah class baru (Child / Subclass) mewarisi atribut dan method dari class yang sudah ada (Parent / Baseclass / Superclass).
		- Contoh: Mobil "adalah sebuah" Kendaraan (*Car is a Vehicle*).
		- ### Generalization vs Specialization
		- **Generalization (Bottom-Up):** Menyatukan atribut yang sama dari beberapa class spesifik ke dalam satu Parent class yang baru (misal: Atribut Id dan Nama di Dosen dan Mahasiswa diangkat ke class User).
		- **Specialization (Top-Down):** Membuat class anak yang lebih spesifik dari sebuah Parent class (misal: Parent `Employee` diturunkan jadi `RegularEmployee` dan `TemporaryEmployee`).
	- ## 9. [[Polymorphism & Abstract Class]]
		- ### Polymorphism (Banyak Bentuk)
		- Kemampuan suatu metode untuk mengambil bentuk eksekusi yang berbeda-beda tergantung pada objek *child* mana yang memanggilnya.
		- ### Virtual dan Override Method
		- **`virtual`:** Keyword pada method di class Parent yang menandakan "method ini boleh ditumpuk/diganti oleh anak-anaknya".
		- **`override`:** Keyword pada method di class Child yang menandakan "method ini mengganti perilaku method dari Parent".
		- **Penyelesaian Masalah:** Jika kita punya list `Shape`, dan di dalamnya ada objek `Circle` dan `Rectangle`. Saat kita memanggil `shapeList[i].CalculateArea()`, program otomatis memanggil rumus luas lingkaran atau luas persegi panjang sesuai objek asli saat *Runtime*.
		- ### Abstract Class
		- Sebuah class yang **TIDAK BISA dibuat objeknya secara langsung** (`new Shape()` tidak diperbolehkan). Ia hanya berfungsi sebagai kerangka/template dasar untuk class turunannya.
		- **Abstract Method:** Method tanpa isi (tanpa blok `{ }`) di dalam abstract class. Memaksa/mewajibkan semua *child class* untuk meng-implementasikan (*override*) method tersebut.
	- ## Studi Kasus: Konser Aplikasi (DateTime)
		- **Kasus:** Membuat sistem penyimpanan konser musik (Artis, Judul, Venue, Tanggal Mulai, Tanggal Berakhir).
		- **Komponen Windows Form Penting:**
		- Menggunakan `DateTimePicker` di Form untuk input tanggal.
		- Di class, simpan data tersebut dalam tipe data `DateTime`.
		- **Penyelesaian Masalah Operasi Waktu:**
		- Menghitung sisa hari menuju konser: `DateTime.Now.Subtract(tanggalKonser).Days`
		- Mengubah tipe waktu ke format string tanggal pendek: `myDate.ToShortDateString()`