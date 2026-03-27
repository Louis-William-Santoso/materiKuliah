- Dua konsep ini merupakan teknik pembuktian fundamental dalam Matematika Diskrit. Induksi digunakan untuk membuktikan kebenaran sebuah deret atau properti bilangan, sedangkan Pigeonhole digunakan untuk membuktikan eksistensi (keberadaan) suatu kondisi ekstrem dalam kombinatorika.
- ## 1. [[Induksi Matematis (Mathematical Induction)]]
	- **Definisi:** Induksi matematis adalah teknik pembuktian baku di dalam matematika yang dipakai untuk membuktikan pernyataan-pernyataan yang terkait dengan himpunan bilangan bulat positif atau bilangan asli ($n \ge 1$ atau $n \ge 0$).
	- **Analogi Logika (Efek Domino):**
		- Bayangkan deretan kartu domino yang diberdirikan berdekatan. Jika kita bisa memastikan dua hal: (1) Kartu pertama jatuh, dan (2) Jika sembarang kartu ke-$k$ jatuh, maka ia pasti akan menjatuhkan kartu ke-$(k+1)$ di depannya. Maka, kita dapat menyimpulkan bahwa **seluruh** kartu domino tak hingga tersebut pasti akan jatuh.
	- **Tiga Langkah Baku Induksi Matematis:**
	  1. **Basis Induksi (Base Case):** Membuktikan bahwa pernyataan bernilai benar untuk nilai awal $n$ (biasanya $n = 1$ atau $n = 0$, dinotasikan sebagai $n_0$).
	  2. **Hipotesis Induksi (Inductive Hypothesis):** Mengasumsikan (menganggap benar) bahwa pernyataan tersebut berlaku untuk suatu bilangan bulat sembarang $n = k$.
	  3. **Langkah Induksi (Inductive Step):** Menggunakan asumsi pada langkah ke-2 untuk membuktikan secara aljabar bahwa pernyataan tersebut juga benar untuk $n = k + 1$.
	- **Penyelesaian Masalah 1: Pembuktian Deret Geometri**
		- *Masalah:* Buktikan bahwa untuk semua bilangan bulat tidak-negatif $n$, berlaku deret: $2^0 + 2^1 + 2^2 + \dots + 2^n = 2^{n+1} - 1$.
		- *Penyelesaian:*
			- **Basis Induksi:** Untuk $n = 0$, ruas kiri adalah $2^0 = 1$. Ruas kanan adalah $2^{0+1} - 1 = 2 - 1 = 1$. Karena $1 = 1$, basis induksi bernilai **Benar**.
			- **Hipotesis Induksi:** Asumsikan benar untuk $n = k$, maka:
			  $2^0 + 2^1 + 2^2 + \dots + 2^k = 2^{k+1} - 1$
			- **Langkah Induksi:** Akan dibuktikan benar untuk $n = k+1$. Tambahkan elemen ke-$(k+1)$ yaitu $2^{k+1}$ pada kedua ruas di persamaan hipotesis:
			  $(2^0 + 2^1 + \dots + 2^k) + 2^{k+1} = (2^{k+1} - 1) + 2^{k+1}$
			  Sederhanakan ruas kanan:
			  $= 2 \cdot (2^{k+1}) - 1$ (karena $x + x = 2x$)
			  $= 2^{(k+1)+1} - 1$
			  $= 2^{k+2} - 1$.
			  *Kesimpulan:* Bentuk akhirnya sesuai dengan rumus awal jika $n$ diganti $k+1$. (Terbukti Sah).
	- **Penyelesaian Masalah 2: Pembuktian Keterbagian**
		- *Masalah:* Buktikan dengan induksi matematis bahwa untuk $n \ge 1$, ekspresi $n^3 + 2n$ selalu habis dibagi 3.
		- *Penyelesaian:*
			- **Basis Induksi:** Untuk $n = 1 \implies 1^3 + 2(1) = 3$. Karena 3 habis dibagi 3, maka pernyataan ini **Benar**.
			- **Hipotesis Induksi:** Asumsikan benar untuk $n = k$, maka $k^3 + 2k$ habis dibagi 3. Kita bisa menuliskannya sebagai: $k^3 + 2k = 3M$ (dimana $M$ adalah suatu bilangan bulat).
			- **Langkah Induksi:** Akan dibuktikan benar untuk $n = k+1$, yaitu $(k+1)^3 + 2(k+1)$ juga habis dibagi 3.
			  Jabarkan secara aljabar:
			  $= (k^3 + 3k^2 + 3k + 1) + 2k + 2$
			  Kelompokkan ulang agar memunculkan bentuk hipotesis $(k^3 + 2k)$:
			  $= (k^3 + 2k) + 3k^2 + 3k + 3$
			  Substitusikan nilai hipotesis $(k^3 + 2k = 3M)$:
			  $= 3M + 3(k^2 + k + 1)$
			  Keluarkan angka 3 (faktorisasi):
			  $= 3 \cdot (M + k^2 + k + 1)$
			  *Kesimpulan:* Karena ekspresi tersebut merupakan kelipatan dari 3, maka terbukti bahwa $(k+1)^3 + 2(k+1)$ habis dibagi 3.
- ## 2. [[Prinsip Sarang Merpati (Pigeonhole Principle)]]
	- **Definisi Dasar (Dirichlet's Box Principle):** Jika terdapat $n+1$ ekor burung merpati yang ditempatkan ke dalam $n$ buah sarang, maka secara logis pasti ada *setidaknya satu sarang* yang menampung *dua ekor merpati atau lebih*.
	- **Definisi Umum (Generalized Pigeonhole Principle):** Jika ada $N$ objek yang ditempatkan ke dalam $k$ buah wadah, maka setidaknya ada satu wadah yang menampung paling sedikit $\lceil N/k \rceil$ objek.
		- *Catatan:* Simbol $\lceil \dots \rceil$ adalah fungsi *ceiling* (pembulatan ke atas ke bilangan bulat terdekat). Contoh: $\lceil 3.1 \rceil = 4$.
	- **Info Tambahan (Aplikasi di Dunia Komputer):**
		- Prinsip ini sangat esensial dalam menjelaskan fenomena **Hash Collision** pada struktur data *Hash Table* dan Kriptografi.
		- Jika algoritma hashing (seperti MD5/SHA) menghasilkan ukuran *output* 256-bit (berarti ada jumlah kombinasi sarang yang terbatas, meskipun sangat besar), namun *file* yang di-*hash* berukuran *gigabytes* (jumlah merpati jauh lebih banyak), maka secara matematis *pasti* ada dua *file* berbeda yang memiliki kode *hash* yang sama persis (tabrakan data). Ini membuktikan bahwa tidak ada fungsi *hash* pemampatan yang 100% bebas dari kolisi.
	- **Penyelesaian Masalah 1: Tanggal Lahir (Bulan)**
		- *Masalah:* Di dalam sebuah kelas *Discrete Math* terdapat 37 mahasiswa. Buktikan bahwa setidaknya ada 4 orang mahasiswa yang lahir pada bulan yang sama!
		- *Penyelesaian:*
			- Identifikasi Merpati ($N$ objek): Jumlah mahasiswa = 37.
			- Identifikasi Sarang ($k$ wadah): Jumlah bulan dalam setahun = 12.
			- Gunakan Teorema Umum: $\lceil N/k \rceil = \lceil 37/12 \rceil$
			- Hitung: $37 / 12 = 3.0833...$
			- Lakukan fungsi *ceiling* (bulatkan ke atas): $\lceil 3.0833 \rceil = 4$.
			- *Kesimpulan:* Terbukti bahwa dari 37 mahasiswa, pasti ada minimum 4 orang yang berbagi bulan kelahiran yang sama, karena jika setiap bulan hanya diisi maksimal 3 orang, maka $3 \times 12 = 36$ orang (masih sisa 1 orang yang harus masuk ke salah satu dari 12 bulan tersebut).
	- **Penyelesaian Masalah 2: Pengambilan Kaos Kaki Buta**
		- *Masalah:* Dalam sebuah laci kamar yang gelap, terdapat 10 pasang kaos kaki hitam (total 20 sebelah) dan 10 pasang kaos kaki biru (total 20 sebelah). Berapa jumlah kaos kaki minimum yang harus Anda ambil (tanpa melihat) untuk memastikan Anda mendapatkan sepasang kaos kaki dengan warna yang sama?
		- *Penyelesaian:*
			- Identifikasi Sarang ($k$ wadah): Warna yang tersedia (Hitam dan Biru) $\implies k = 2$.
			- Kita ingin memastikan sepasang (2 buah) kaos kaki dari sarang yang sama.
			- Dalam Pigeonhole, jika mengambil $k+1$ objek (jumlah sarang + 1), maka ada minimal 1 sarang yang mendapat 2 objek.
			- Maka, jumlah yang harus diambil adalah $2 + 1 = 3$ sebelah kaos kaki.
			- *Pembuktian Logika Skenario Terburuk:*
				- Pengambilan 1: Hitam.
				- Pengambilan 2 (sial, beda warna): Biru. (Sekarang kita punya 1 Hitam, 1 Biru).
				- Pengambilan 3: Apa pun warnanya (entah Hitam atau Biru), ia pasti akan berjodoh dengan salah satu kaos kaki yang sudah ada di tangan, membentuk satu pasang warna yang sama.