# Week 1: Sistem Bilangan Riil & Pertidaksamaan
	- ## 1. [[Sistem Bilangan Riil]]
		- ### A. Hierarki Himpunan Bilangan
			- Pemahaman dasar kalkulus dimulai dari pengenalan sistem bilangan. Bilangan riil adalah gabungan dari beberapa himpunan bilangan yang lebih kecil.       - **Bilangan Asli ($\mathbb{N}$)**: Himpunan bilangan bulat positif yang dimulai dari 1. Contoh: $1, 2, 3, 4, \dots$
			- **Bilangan Cacah ($\mathbb{W}$)**: Bilangan asli ditambah nol. Contoh: $0, 1, 2, 3, \dots$
			- **Bilangan Bulat ($\mathbb{Z}$)**: Gabungan bilangan cacah dan bilangan negatifnya. Contoh: $\dots, -2, -1, 0, 1, 2, \dots$
			- **Bilangan Rasional ($\mathbb{Q}$)**: Bilangan yang dapat dinyatakan dalam bentuk pecahan $\frac{p}{q}$, di mana $p$ dan $q$ adalah bilangan bulat dan $q \neq 0$. Desimalnya berhenti atau berulang teratur. Contoh: $\frac{1}{2}, -\frac{3}{4}, 0.75, 0.333\dots$
			- **Bilangan Irasional**: Bilangan yang tidak dapat dinyatakan dalam bentuk pecahan $\frac{p}{q}$. Desimalnya tidak pernah berhenti dan tidak berulang. Contoh: $\sqrt{2}, \pi, e$.
			- **Bilangan Riil ($\mathbb{R}$)**: Gabungan dari semua bilangan rasional dan irasional. Semua bilangan ini dapat diletakkan pada sebuah garis bilangan tak hingga.
		- ### B. Sifat-Sifat Operasi Bilangan Riil
			- Jika $a, b,$ dan $c$ adalah elemen dari himpunan bilangan riil ($\mathbb{R}$), maka berlaku sifat-sifat berikut:
			- **Komutatif**: Berlaku untuk penjumlahan ($a+b = b+a$) dan perkalian ($a \cdot b = b \cdot a$).
			- **Asosiatif**: Berlaku untuk pengelompokan penjumlahan ($(a+b)+c = a+(b+c)$) dan perkalian ($(a \cdot b) \cdot c = a \cdot (b \cdot c)$).
			- **Distributif**: Penyebaran perkalian terhadap penjumlahan ($a \cdot (b+c) = a \cdot b + a \cdot c$).
			- **Elemen Identitas**: Angka $0$ untuk penjumlahan ($a+0 = a$) dan angka $1$ untuk perkalian ($a \cdot 1 = a$).
			- **Invers**: Invers aditif/penjumlahan ($-a$) sehingga $a + (-a) = 0$. Invers perkalian ($\frac{1}{a}$ untuk $a \neq 0$) sehingga $a \cdot \frac{1}{a} = 1$.
	- ## 2. [[Notasi Interval]]
		- Dalam pertidaksamaan, himpunan penyelesaian sering ditulis menggunakan notasi interval.     - **Interval Terbuka** $(a, b)$: Titik ujung tidak termasuk. Ekuivalen dengan $a < x < b$. Pada garis bilangan digambar dengan "bulatan kosong".
		- **Interval Tertutup** $[a, b]$: Titik ujung termasuk. Ekuivalen dengan $a \le x \le b$. Pada garis bilangan digambar dengan "bulatan penuh".
		- **Interval Setengah Terbuka** $[a, b)$: $a$ termasuk, $b$ tidak. Ekuivalen dengan $a \le x < b$.
		- **Tak Hingga** ($\infty$): Selalu menggunakan kurung buka/tutup biasa, bukan kurung siku. Contoh: $(-\infty, a]$ berarti $x \le a$.
	- ## 3. [[Pertidaksamaan dan Penyelesaian Masalah]]
		- Menyelesaikan pertidaksamaan berarti mencari semua himpunan nilai variabel (misalnya $x$) yang membuat pernyataan matematika tersebut bernilai benar.
		- Aturan Emas: **Jika Anda mengalikan atau membagi kedua ruas pertidaksamaan dengan bilangan negatif, tanda pertidaksamaan HARUS dibalik.** (misal: $<$ menjadi $>$).
		- ### A. Pertidaksamaan Linier
			- Variabel hanya berpangkat satu. Diselesaikan dengan memindahkan variabel ke satu sisi dan konstanta ke sisi lain.
			- **Contoh Soal**: Tentukan penyelesaian dari $3x - 5 < 5x + 7$
				- **Penyelesaian**:
					- Kurangi kedua ruas dengan $5x$: $-2x - 5 < 7$
					- Tambahkan kedua ruas dengan $5$: $-2x < 12$
					- Bagi kedua ruas dengan $-2$ (ingat, tanda dibalik!): $x > -6$
					- **Himpunan Penyelesaian (HP)**: $(-6, \infty)$
		- ### B. Pertidaksamaan Kuadrat
			- Variabel memiliki pangkat tertinggi dua.       - **Langkah penyelesaian**:
			  1. Jadikan salah satu ruas sama dengan nol (0).
			  2. Faktorkan persamaan kuadrat tersebut untuk mencari akar-akarnya (pembuat nol).
			  3. Buat garis bilangan dan letakkan akar-akar tersebut.
			  4. Uji titik pada setiap interval untuk menentukan tanda positif ($+$) atau negatif ($-$).
			  5. Pilih interval yang sesuai dengan tanda pertidaksamaan.
			- **Contoh Soal**: Selesaikan $x^2 - x - 6 \ge 0$
				- **Penyelesaian**:
					- Faktorkan: $(x - 3)(x + 2) \ge 0$
					- Pembuat nol: $x = 3$ dan $x = -2$.
					- Uji garis bilangan:
						- Untuk $x < -2$ (misal $x=-3$): $(-)(-)$ = Positif ($+$)
						- Untuk $-2 < x < 3$ (misal $x=0$): $(-)(+)$ = Negatif ($-$)
						- Untuk $x > 3$ (misal $x=4$): $(+)(+)$ = Positif ($+$)
					- Karena diminta $\ge 0$ (positif atau nol), maka kita ambil area ($+$).
					- **HP**: $(-\infty, -2] \cup [3, \infty)$
		- ### C. Pertidaksamaan Rasional (Pecahan)
			- Berbentuk pecahan $\frac{P(x)}{Q(x)}$. Perlakuan mirip dengan kuadrat, tetapi ada syarat tambahan: **penyebut tidak boleh nol**.
			- **Langkah penyelesaian**:
			  1. Buat ruas kanan menjadi nol (pindahkan semua ke ruas kiri).
			  2. Samakan penyebut menjadi satu pecahan tunggal.
			  3. Cari pembuat nol dari pembilang dan pembuat nol dari penyebut.
			  4. Uji pada garis bilangan. Pastikan pembuat nol dari **penyebut selalu menggunakan bulatan kosong** (kurung biasa).
			- **Contoh Soal**: Selesaikan $\frac{2x+4}{x-1} \le 0$
				- **Penyelesaian**:
					- Ruas kanan sudah nol.
					- Pembuat nol pembilang: $2x+4 = 0 \implies x = -2$ (Bulatan penuh, karena tanda $\le$).
					- Pembuat nol penyebut: $x-1 = 0 \implies x = 1$ (Bulatan kosong, karena penyebut tidak boleh nol).
					- Uji garis bilangan dengan titik kritis $-2$ dan $1$:
						- Area $x < -2$: Positif ($+$)
						- Area $-2 < x < 1$: Negatif ($-$)
						- Area $x > 1$: Positif ($+$)
					- Karena tanda $\le 0$, kita cari area negatif ($-$).
					- **HP**: $[-2, 1)$
		- ### D. Pertidaksamaan Nilai Mutlak
			- Nilai mutlak $|x|$ melambangkan jarak suatu bilangan dari $0$ pada garis bilangan.
			- **Sifat penting**:
				- Jika $|X| < a$, maka $-a < X < a$
				- Jika $|X| > a$, maka $X < -a$ atau $X > a$
			- **Contoh Soal**: Selesaikan $|3x - 2| \le 7$
				- **Penyelesaian**:
					- Gunakan sifat pertama: $-7 \le 3x - 2 \le 7$
					- Tambahkan $2$ ke ketiga ruas: $-5 \le 3x \le 9$
					- Bagi semua ruas dengan $3$: $-\frac{5}{3} \le x \le 3$
					- **HP**: $[-\frac{5}{3}, 3]$