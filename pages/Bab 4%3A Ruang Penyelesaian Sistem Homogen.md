## 1. [[Konsep Dasar Sistem Homogen]]
	- **Definisi**: Sistem Persamaan Linier (SPL) dikatakan homogen jika semua konstanta di ruas kanan persamaan bernilai nol.
		- Bentuk matriksnya ditulis sebagai: $Ax = 0$.
	- **Sifat Solusi**: SPL homogen **tidak pernah tak konsisten**. Artinya, sistem ini pasti memiliki minimal satu solusi.
		- **Solusi Trivial**: Solusi di mana semua variabel bernilai nol ($x_1=0, x_2=0, \dots, x_n=0$).
		- **Solusi Nontrivial**: Solusi di mana ada variabel yang bernilai selain nol. Ini terjadi jika sistem memiliki tak hingga banyaknya penyelesaian (biasanya jika jumlah variabel lebih banyak dari jumlah persamaan atau determinan matriks koefisiennya 0).
- ## 2. [[Ruang Penyelesaian (Ruang Solusi / Ruang Nol)]]
	- Jika $Ax = 0$ adalah SPL homogen dengan $m$ persamaan dan $n$ variabel, maka himpunan semua penyelesaiannya membentuk sebuah subruang dari ruang vektor $R^n$.
	- Subruang penyelesaian ini sering juga disebut sebagai **Ruang Nol (Null Space)** dari matriks $A$.
- ## 3. [[Basis dan Dimensi]]
	- Untuk mendeskripsikan ruang penyelesaian yang memiliki tak hingga banyaknya solusi, kita menggunakan konsep **Basis** dan **Dimensi**.
	- **Basis**: Sekumpulan vektor yang memiliki dua syarat mutlak:
	  1. **Merentang (Membangun) Ruang**: Setiap solusi dalam ruang tersebut dapat ditulis sebagai kombinasi linier dari vektor-vektor basis.
	  2. **Bebas Linier**: Tidak ada vektor basis yang bisa dinyatakan sebagai kombinasi atau kelipatan dari vektor basis lainnya.
	- **Dimensi**: Jumlah vektor yang ada di dalam sebuah Basis. Dimensi dari ruang solusi SPL homogen juga dikenal dengan istilah **Nullity**.
		- *Catatan Praktis*: Dimensi ruang solusi sama persis dengan **jumlah parameter bebas** (seperti $s, t, r$) yang muncul saat kita mencari penyelesaian umum.
- ## 4. [[Langkah-Langkah Menentukan Basis dan Dimensi Ruang Penyelesaian]]
	- Berikut adalah algoritma standar penyelesaian masalah SPL homogen:
	  1. **Selesaikan SPL $Ax = 0$**: Gunakan metode Eliminasi Gauss atau Gauss-Jordan pada matriks augmented untuk mereduksi matriks menjadi bentuk Eselon Baris Tereduksi.
	  2. **Tuliskan Penyelesaian Umum**: Nyatakan variabel terikat (leading variables) dalam bentuk variabel bebas (parameters). Misalkan variabel bebasnya adalah $s, t$.
	  3. **Pisahkan Parameter**: Tulis ulang vektor solusi $x$ dengan memisahkan bagian yang mengandung parameter $s$, bagian yang mengandung $t$, dst.
	  4. **Tentukan Vektor Basis**: Faktorkan atau keluarkan parameter tersebut. Vektor-vektor skalar yang tertinggal pengali parameter itulah yang menjadi pembentuk himpunan **Basis**.
	  5. **Hitung Dimensi**: Hitung berapa banyak vektor basis yang didapat dari langkah ke-4.
- ## 5. [[Contoh Kasus (Ilustrasi Pemecahan)]]
	- Misalkan setelah dilakukan eliminasi Gauss-Jordan pada SPL homogen 5 variabel ($x_1$ sampai $x_5$), didapatkan persamaan:
		- $x_1 = -3s - 4t$
		- $x_2 = s$
		- $x_3 = -2t$
		- $x_4 = 0$
		- $x_5 = t$
	- **Membentuk Vektor Solusi**:
		- Kita tulis solusi dalam bentuk vektor kolom:
		- $$x = \begin{pmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{pmatrix} = \begin{pmatrix} -3s - 4t \\ s \\ -2t \\ 0 \\ t \end{pmatrix}$$
	- **Pemisahan Parameter**:
		- Kita pecah menjadi penjumlahan dua vektor berdasarkan parameternya:
		- $$x = \begin{pmatrix} -3s \\ s \\ 0 \\ 0 \\ 0 \end{pmatrix} + \begin{pmatrix} -4t \\ 0 \\ -2t \\ 0 \\ t \end{pmatrix} = s\begin{pmatrix} -3 \\ 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} + t\begin{pmatrix} -4 \\ 0 \\ -2 \\ 0 \\ 1 \end{pmatrix}$$
	- **Kesimpulan**:
		- **Basis** ruang penyelesaiannya adalah: $\left\{ \begin{pmatrix} -3 \\ 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} -4 \\ 0 \\ -2 \\ 0 \\ 1 \end{pmatrix} \right\}$
		- **Dimensi** ruang penyelesaiannya adalah **2** (karena ada dua vektor dalam basis).
- ## 🧠 6. Mini Quiz: Uji Pemahaman Bab 4
	- **Soal 1**: Mengapa sebuah himpunan penyelesaian dari sistem $Ax = b$ (di mana $b \neq 0$) **tidak** membentuk sebuah subruang vektor?
		- *Jawaban*: Karena subruang vektor harus selalu mengandung vektor nol (solusi trivial). Pada sistem non-homogen $Ax = b$, jika kita masukkan $x = 0$, hasilnya adalah $0 = b$ (yang mana salah karena $b \neq 0$). Oleh karena itu, hanya sistem homogen $Ax = 0$ yang ruang solusinya memenuhi aksioma subruang.
	- **Soal 2**: Apa syarat suatu himpunan vektor bisa disebut sebagai "basis" dari sebuah ruang solusi?
		- *Jawaban*: Himpunan vektor tersebut harus memenuhi dua syarat: (1) saling bebas linier (tidak bisa dibentuk dari kombinasi vektor lain di himpunan itu), dan (2) merentang/membangun seluruh ruang solusi tersebut.
	- **Soal 3**: Sebuah SPL homogen terdiri dari 4 variabel ($x_1, x_2, x_3, x_4$). Setelah dilakukan eliminasi, ditemukan bahwa $x_1$ dan $x_3$ adalah *leading variables*, sedangkan $x_2$ dan $x_4$ adalah variabel bebas. Berapakah dimensi dari ruang penyelesaiannya?
		- *Jawaban*: Dimensinya adalah 2. Dimensi sama dengan jumlah parameter atau variabel bebas yang ada dalam sistem (dalam hal ini, $x_2$ dan $x_4$).