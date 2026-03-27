# Week 10: Integral Parsial dan Integral Tentu
	- ## 1. [[Integral Parsial]]
		- **Konsep Dasar**: Teknik integral parsial digunakan ketika integran (fungsi yang diintegralkan) merupakan perkalian dari dua fungsi yang sulit atau tidak dapat diselesaikan dengan substitusi biasa.
		- Penggunaan teknik ini adalah menyatakan integran dalam dua bagian: satu bagian bertindak sebagai $u$ dan sisanya bersama-sama dengan $dx$ bertindak sebagai $dv$.
		- **Rumus Utama**:
			- $\int u \, dv = u \cdot v - \int v \, du$
		- **Aturan Pemilihan** $u$ dan $dv$:
			- Saat melakukan langkah pemisahan, Anda harus memilih bagian $dv$ yang dapat diintegralkan.
			- Perlu dipertimbangkan bahwa bentuk integral yang baru di sisi kanan rumus, yaitu $\int v \, du$, tidak boleh lebih sulit untuk dihitung dibandingkan dengan integral awal $\int u \, dv$.
			- **Aturan LIPET**: Untuk memilih fungsi mana yang menjadi $u$, gunakan urutan prioritas (dari kiri ke kanan) berikut ini:
			  1. **L**ogs (Fungsi Logaritma, misal: $\ln x$)
			  2. **I**nvers Trig (Fungsi Invers Trigonometri, misal: $\arcsin x$) 
			  3. **P**olinomial (Fungsi Aljabar/Suku Banyak, misal: $x, x^2$) 
			  4. **E**ksponensial (Fungsi Eksponen, misal: $e^x$) 
			  5. **T**rig (Fungsi Trigonometri, misal: $\sin x, \cos x$)
		- **Contoh Soal & Penyelesaian**:
			- Tentukan hasil dari $\int x e^x \, dx$.
			- **Penyelesaian**:
			  1. Berdasarkan aturan LIPET, $x$ adalah Polinomial dan $e^x$ adalah Eksponensial. Karena Polinomial lebih kiri prioritasnya dibanding Eksponensial, maka pilih $u = x$.
			  2. Sisanya menjadi $dv$, yaitu $dv = e^x \, dx$.
			  3. Turunkan $u$: $du = dx$.
			  4. Integralkan $dv$: $v = \int e^x \, dx = e^x$.
			  5. Masukkan ke dalam rumus integral parsial: $\int u \, dv = uv - \int v \, du$.
			  6. $\int x e^x \, dx = x \cdot e^x - \int e^x \, dx$.
			  7. $\int x e^x \, dx = x e^x - e^x + C$.
	- ## 2. [[Integral Tentu (Definite Integral)]]
		- **Konsep Dasar & Jumlahan Riemann**:
			- luas daerah di bawah suatu kurva dapat dihitung secara konseptual dengan cara menjumlahkan segi empat-segi empat yang dibentuk di bawah kurva tersebut, yang hasilnya dikenal sebagai Jumlahan Riemann.
			- Lebar segi empat tersebut disebut dengan *subinterval*, dan keseluruhan interval dari luasan tersebut disebut *partisi*. Perlu dicatat bahwa panjang setiap *subinterval* tidak harus selalu sama.
			- Semakin kecil partisi atau batas *subinterval*, makin mendekati luas kurva yang sebenarnya.
		- **Langkah-langkah Geometris Pendekatan Area**:
		  1. Interval batas kurva dibagi dalam $n$ *sub-interval* dengan lebar yang sama ($\Delta x$).
		  2. Dari setiap *sub-interval* tersebut, dibuat suatu segi empat (pias) yang lebarnya $\Delta x$ dan tingginya sesuai dengan nilai fungsi $f(\xi_i)$.
		  3. Oleh karena itu, luas setiap segi empat pada suatu interval adalah $f(\xi_i)\Delta x$.
		  4. Luas daerah total yang dicari akan mendekati jumlah luas segi empat dari semua *sub-interval* yang ada, yaitu dirumuskan sebagai $\sum f(\xi_i)\Delta x$.
		- **Teorema Dasar Kalkulus**:
			- Dalam perhitungannya, integral tentu untuk mencari luasan memiliki batas bawah ($a$) dan batas atas ($b$): $\int_a^b f(x) \, dx = F(b) - F(a)$ di mana $F(x)$ adalah hasil integral dari $f(x)$.
		- **Contoh Soal & Penyelesaian**:
			- Hitunglah nilai integral tentu berikut: $\int_0^2 (3x^2 + 4x + 1) \, dx$.
			- **Penyelesaian**:
			  1. Pertama, tentukan fungsi anti-turunan (integral tak tentu) dari persamaan tersebut.
			  2. $\int (3x^2 + 4x + 1) \, dx = x^3 + 2x^2 + x$.
			  3. Selanjutnya, substitusikan batas atas ($2$) dan batas bawah ($0$) menggunakan konsep $F(b) - F(a)$.
			  4. Nilai batas atas $F(2) = (2)^3 + 2(2)^2 + (2) = 8 + 8 + 2 = 18$.
			  5. Nilai batas bawah $F(0) = (0)^3 + 2(0)^2 + (0) = 0$.
			  6. Nilai akhir integral tentu $= 18 - 0 = 18$.
	- ## 3. [[Aplikasi Integral Tentu (Luas Bidang Datar)]]
		- **Menghitung Luas Area Antar Kurva**:
			- Jika dihadapkan pada soal cerita untuk menghitung area di antara dua kurva, misalnya Kurva 1 berbentuk parabola terbuka ke bawah dan Kurva 2 berbentuk garis lurus dengan gradien positif.
			- **Langkah Umum Penyelesaian**:
			  1. Cari titik perpotongan antara Kurva 1 dan Kurva 2. Nilai absis (sumbu-x) dari titik potong ini akan menjadi batas bawah ($a$) dan batas atas ($b$) integrasi.
			  2. Gunakan rumus pengurangan kurva: Luas $= \int_a^b (\text{Kurva Atas} - \text{Kurva Bawah}) \, dx$.