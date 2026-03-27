# Week 8-10: Integral dan Aplikasi Integral
	- ## 1. [[Konsep Dasar Integral (Anti-Turunan)]]
		- **Definisi**: Integral adalah operasi matematika yang merupakan kebalikan (invers) dari turunan. Jika turunan mencari "kecepatan perubahan" dari sebuah fungsi, integral mencari "akumulasi" atau fungsi asalnya.
		- Jika $F(x)$ adalah fungsi yang turunannya adalah $f(x)$ (yaitu $F'(x) = f(x)$), maka integral tak tentu dari $f(x)$ ditulis sebagai:
			- $\int f(x) dx = F(x) + C$
			- $\int$ melambangkan operasi integral.
			- $f(x)$ disebut **integran** (fungsi yang diintegralkan).
			- $dx$ menunjukkan variabel integrasi (diintegralkan terhadap $x$).
			- $C$ adalah **konstanta integrasi** (karena turunan dari konstanta adalah 0, kita harus selalu menambahkan $C$ pada integral tak tentu).
	- ## 2. [[Sifat dan Rumus Dasar Integrasi]]
		- **Sifat Linieritas**:
			- $\int k \cdot f(x) dx = k \int f(x) dx$ (di mana $k$ adalah konstanta).
			- $\int [f(x) \pm g(x)] dx = \int f(x) dx \pm \int g(x) dx$
		- **Rumus Dasar**:
			- **Aturan Pangkat**: $\int x^n dx = \frac{1}{n+1}x^{n+1} + C$ (Syarat: $n \neq -1$)
			- **Fungsi Logaritma Natural**: $\int \frac{1}{x} dx = \ln|x| + C$
			- **Fungsi Eksponensial**:
				- $\int e^x dx = e^x + C$
				- $\int a^x dx = \frac{a^x}{\ln a} + C$ (untuk $a > 0, a \neq 1$)
			- **Fungsi Trigonometri**:
				- $\int \sin x dx = -\cos x + C$
				- $\int \cos x dx = \sin x + C$
				- $\int \sec^2 x dx = \tan x + C$
				- $\int \csc^2 x dx = -\cot x + C$
				- $\int \sec x \tan x dx = \sec x + C$
				- $\int \csc x \cot x dx = -\csc x + C$
	- ## 3. [[Teknik Integrasi]]
		- Tidak semua fungsi bisa diintegralkan langsung dengan rumus dasar. Berikut adalah teknik-teknik untuk memanipulasi integran:
		- ### A. Teknik Substitusi
			- Digunakan jika integran merupakan fungsi komposisi yang dikalikan dengan turunan dari "fungsi di dalamnya" (berkaitan dengan Aturan Rantai pada turunan).
			- **Langkah penyelesaian**:
			  1. Pilih bagian dari integran untuk disubstitusi, misal $u = g(x)$.
			  2. Turunkan $u$ terhadap $x$ untuk mendapatkan $du = g'(x) dx \implies dx = \frac{du}{g'(x)}$.
			  3. Substitusikan $u$ dan $dx$ ke dalam integral awal, sehingga semua variabel berubah menjadi $u$.
			  4. Integralkan terhadap $u$.
			  5. Kembalikan variabel $u$ menjadi $x$.
		- ### B. Integral Parsial (Integration by Parts)
			- Berasal dari aturan perkalian turunan ($(uv)' = u'v + uv'$). Digunakan saat mengintegralkan perkalian dua fungsi yang tidak saling berkaitan erat (tidak bisa disubstitusi biasa).
			- **Rumus**: $\int u dv = u \cdot v - \int v du$
			- **Aturan Pemilihan $u$ (Aturan LIPET)**: Pilih fungsi $u$ berdasarkan urutan prioritas yang paling mudah diturunkan (dari kiri ke kanan):
			  1. **L**ogaritma (misal: $\ln x$)
			  2. **I**nvers Trigonometri (misal: $\arctan x$)
			  3. **P**olinomial / Aljabar (misal: $x, x^2$)
			  4. **E**ksponensial (misal: $e^x$)
			  5. **T**rigonometri (misal: $\sin x, \cos x$)
			- Sisa dari integran, beserta $dx$, menjadi $dv$ yang kemudian diintegralkan untuk mendapatkan $v$.
		- ### C. Mengubah Integran Menjadi Pecahan Parsial (Partial Fractions)
			- Digunakan untuk mengintegralkan fungsi rasional $\frac{P(x)}{Q(x)}$ di mana polinomial penyebut $Q(x)$ dapat difaktorkan.
			- **Langkah penyelesaian**:
			  1. Pastikan derajat pembilang $P(x)$ lebih kecil dari derajat penyebut $Q(x)$. Jika tidak, lakukan pembagian polinomial (porogapit) terlebih dahulu.
			  2. Faktorkan penyebut $Q(x)$ menjadi faktor-faktor linier (misal $(x-a)$) atau kuadrat yang tidak bisa difaktorkan lagi.
			  3. Pecah menjadi jumlahan pecahan parsial:
				- Faktor linier tak berulang: $\frac{A}{x-a} + \frac{B}{x-b}$
				- Faktor linier berulang: $\frac{A}{x-a} + \frac{B}{(x-a)^2}$
				  4. Cari nilai konstanta $A, B$, dst., dengan menyamakan penyebut ruas kiri dan kanan.
				  5. Integralkan masing-masing pecahan parsial yang sudah disederhanakan (biasanya menghasilkan fungsi $\ln$).
		- ### D. Substitusi Trigonometri dan Fungsi Irasional
			- Digunakan jika integran memuat bentuk akar khusus, seperti $\sqrt{a^2 - x^2}, \sqrt{a^2 + x^2}$, atau $\sqrt{x^2 - a^2}$.
			- Idenya adalah memisalkan $x$ dengan fungsi trigonometri ($x = a \sin \theta, x = a \tan \theta$, atau $x = a \sec \theta$) agar bentuk akarnya hilang menggunakan identitas Pythagoras.
	- ## 4. [[Integral Tentu (Definite Integral)]]
		- Integral tentu memiliki batas bawah dan batas atas. Hasilnya adalah sebuah **angka/nilai**, bukan fungsi berkonstanta $C$.
		- **Jumlahan Riemann**: Secara konsep, integral tentu mencari luas daerah di bawah kurva dengan membaginya menjadi banyak segi empat (sub-interval / pias) selebar $\Delta x$. Makin kecil $\Delta x$ (makin banyak partisi), hasilnya makin mendekati luas aslinya. 
		  
		  [Image of Riemann sum]
		- **Teorema Dasar Kalkulus**:
			- $\int_{a}^{b} f(x) dx = F(b) - F(a)$
			- Di mana $a$ adalah batas bawah, $b$ adalah batas atas, dan $F(x)$ adalah anti-turunan dari $f(x)$.
	- ## 5. [[Aplikasi Integral]]
		- ### Luas Bidang Datar
			- Integral tentu digunakan untuk menghitung luas area di antara kurva dan sumbu koordinat, atau di antara dua kurva. 
			  
			  [Image of Area between two curves]
			- **Luas area antara kurva dan Sumbu-X**:
				- $L = \int_{a}^{b} f(x) dx$ (jika kurva di atas sumbu-x)
				- $L = -\int_{a}^{b} f(x) dx$ atau $\int_{a}^{b} |f(x)| dx$ (jika kurva di bawah sumbu-x)
			- **Luas area di antara dua kurva** ($y_1 = f(x)$ dan $y_2 = g(x)$):
				- Jika kurva $f(x)$ berada di *atas* $g(x)$ pada interval $[a, b]$, maka:
				- $L = \int_{a}^{b} (\text{Kurva Atas} - \text{Kurva Bawah}) dx = \int_{a}^{b} (f(x) - g(x)) dx$
				- Titik potong antar kurva sering kali digunakan untuk menentukan batas integrasi $a$ dan $b$.