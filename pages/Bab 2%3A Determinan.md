## 1. Definisi dan Konsep Dasar
	- **Determinan** adalah sebuah nilai skalar (bilangan real) yang secara unik dikaitkan dengan sebuah **matriks bujur sangkar** (jumlah baris dan kolom sama, misal 2x2, 3x3, dst.).
	- Notasi determinan untuk matriks $A$ ditulis sebagai $\det(A)$ atau $|A|$.
	- **Penting**: Matriks yang bukan bujur sangkar (misal 2x3 atau 3x4) **tidak memiliki determinan**.
- ## 2. Metode Perhitungan Dasar (Orde 2x2 dan 3x3)
	- ### A. Matriks 2x2
		- Untuk matriks $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, determinannya dihitung dengan selisih hasil kali elemen diagonal utama dan diagonal samping.
		- **Rumus**: $\det(A) = ad - bc$
	- ### B. Matriks 3x3 (Aturan Sarrus)
		- Aturan Sarrus adalah cara visual dan cepat khusus untuk matriks 3x3.
		- **Langkah-langkah**:
		  1. Salin dua kolom pertama matriks dan letakkan di sebelah kanan kolom ketiga.
		  2. Kalikan elemen-elemen pada 3 diagonal utama (dari kiri atas ke kanan bawah) dan jumlahkan.
		  3. Kalikan elemen-elemen pada 3 diagonal samping (dari kiri bawah ke kanan atas) dan jumlahkan.
		  4. Kurangi jumlah hasil kali diagonal utama dengan diagonal samping.
		-
		- *Peringatan*: Aturan Sarrus **hanya berlaku** untuk matriks 3x3. Jangan gunakan untuk matriks 4x4 atau lebih besar.
- ## 3. Ekspansi Kofaktor (Metode Laplace)
	- Digunakan untuk menghitung determinan matriks berukuran berapapun ($n \times n$), sangat direkomendasikan untuk matriks 4x4 ke atas.
	- **Minor ($M_{ij}$)**: Determinan dari sub-matriks yang tersisa setelah baris ke-$i$ dan kolom ke-$j$ dihapus.
	- **Kofaktor ($C_{ij}$)**: Nilai minor yang telah diberikan tanda positif atau negatif berdasarkan posisinya.
		- **Rumus Kofaktor**: $$C_{ij} = (-1)^{i+j}M_{ij}$$
		- *Pola Tanda*: Selalu selang-seling (mulai dari $+$ di pojok kiri atas).
	- **Cara Menghitung Determinan dengan Ekspansi Kofaktor**:
		- Pilih satu baris atau satu kolom sembarang (pilih yang paling banyak angka nol-nya agar hitungan lebih cepat).
		- Kalikan setiap elemen pada baris/kolom tersebut dengan kofaktornya, lalu jumlahkan.
		- Contoh ekspansi sepanjang baris pertama: $\det(A) = a_{11}C_{11} + a_{12}C_{12} + a_{13}C_{13}$
- ## 4. Sifat-sifat Penting Determinan
	- Memahami sifat ini bisa menghemat waktu perhitungan secara drastis:
	- $\det(A) = \det(A^T)$ (Determinan matriks sama dengan determinan transposenya).
	- Jika sebuah matriks memiliki satu baris atau kolom yang **semua elemennya nol**, maka $\det(A) = 0$.
	- Jika sebuah matriks memiliki dua baris atau kolom yang **sama persis atau berkelipatan**, maka $\det(A) = 0$.
	- $\det(AB) = \det(A) \cdot \det(B)$
	- Jika matriks $A$ memiliki invers, maka $\det(A^{-1}) = \frac{1}{\det(A)}$. Jika $\det(A) = 0$, matriks **tidak memiliki invers** (disebut matriks singular).
	- Determinan dari matriks segitiga (atas/bawah) atau matriks diagonal adalah **hasil kali elemen-elemen diagonal utamanya**.
- ## 5. Info Tambahan & Penjelasan Penyelesaian Masalah
	- ### Pengaruh Operasi Baris Elementer (OBE) pada Determinan
		- Alih-alih langsung menggunakan kofaktor untuk matriks 4x4 yang rumit, kita bisa menggunakan OBE untuk menyederhanakan matriks menjadi matriks segitiga atas, lalu mengalikan diagonalnya. Tapi perhatikan aturan ini:
		  1. **Menukar 2 baris**: Mengubah tanda determinan (kalikan dengan -1).
		  2. **Mengalikan 1 baris dengan konstanta $k$**: Mengalikan nilai determinan dengan $k$.
		  3. **Menambahkan kelipatan suatu baris ke baris lain**: **Tidak merubah** nilai determinan (Ini operasi yang paling aman dan sering digunakan!).
	- ### Aplikasi Determinan: Aturan Cramer
		- Digunakan untuk mencari solusi SPL. Jika sistem $Ax = b$ memiliki $\det(A) \neq 0$, maka solusi untuk variabel $x_j$ adalah:
		- $$x_j = \frac{\det(A_j)}{\det(A)}$$
		- *Penjelasan*: Matriks $A_j$ adalah matriks $A$ di mana kolom ke-$j$ diganti dengan vektor konstanta $b$.
- ## 🧠 6. Mini Quiz: Uji Pemahaman Bab 2
	- **Soal 1**: Jika diketahui matriks $A$ berukuran 3x3 memiliki determinan 5, berapakah nilai determinan dari matriks transposenya ($A^T$)?
		- *Jawaban*: 5. (Sifat determinan: $\det(A) = \det(A^T)$).
	- **Soal 2**: Anda diberikan matriks 4x4, namun baris ke-2 dan baris ke-4 memiliki angka yang persis sama. Tanpa menghitung panjang, berapakah determinannya dan mengapa?
		- *Jawaban*: 0. Berdasarkan sifat determinan, jika ada dua baris atau kolom yang sama persis (atau berkelipatan), maka determinannya dipastikan bernilai 0.
	- **Soal 3**: Mengapa metode Aturan Cramer tidak bisa digunakan jika determinan matriks koefisien utama ($A$) bernilai 0?
		- *Jawaban*: Karena rumus Aturan Cramer adalah membagi determinan matriks modifikasi ($A_j$) dengan determinan matriks utama ($\det(A)$). Dalam matematika, pembagian dengan 0 tidak terdefinisi, yang juga berarti SPL tersebut mungkin tidak memiliki solusi tunggal (bisa tak konsisten atau solusinya tak hingga).
	- **Soal 4**: Apa bedanya Minor dan Kofaktor?
		- *Jawaban*: Minor adalah nilai determinan dari sub-matriks setelah menghilangkan baris dan kolom tertentu. Kofaktor adalah nilai Minor yang sudah dikalikan dengan tanda tempatnya (plus atau minus) berdasarkan rumus $(-1)^{i+j}$.