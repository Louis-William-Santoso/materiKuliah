# Week 3: Fungsi
	- ## 1. [[Definisi Dasar]]
		- **Fungsi**: Sebuah aturan atau relasi yang memetakan setiap elemen $x$ di himpunan asal (tepat satu) ke sebuah elemen $y$ di himpunan kawan. 
		  
		  [Image of Function Mapping Diagram]
		- Misalkan fungsi dinotasikan dengan $f$, maka $y = f(x)$.
			- $x$ disebut variabel bebas (*independent variable*).
			- $y$ disebut variabel terikat (*dependent variable*).
	- ## 2. [[Domain dan Range]]
		- **Domain (** $D_f$ **atau Daerah Asal)**: Himpunan semua nilai input ($x$) yang mungkin sehingga fungsi tersebut terdefinisi secara riil dan tidak menghasilkan *error* matematika.
		- **Range (** $R_f$ **atau Daerah Hasil)**: Himpunan semua nilai output ($y$) yang mungkin dihasilkan oleh fungsi dari domainnya.
		- ### Aturan Utama Menentukan Domain
			- Dalam kalkulus fungsi riil, kita harus menghindari tiga hal utama agar fungsi tetap terdefinisi:
			  1. **Pembagian dengan nol**: Jika fungsi berbentuk pecahan $\frac{P(x)}{Q(x)}$, maka penyebutnya tidak boleh nol $\implies Q(x) \neq 0$.
			  2. **Akar negatif**: Jika fungsi berbentuk akar genap $\sqrt[n]{P(x)}$ (misal akar kuadrat, akar pangkat 4), maka ekspresi di dalam akar tidak boleh negatif $\implies P(x) \ge 0$.
			  3. **Logaritma dari nol atau negatif**: Jika fungsi berbentuk logaritma $\log_a(P(x))$ atau $\ln(P(x))$, maka argumen (numerus) logaritma harus positif $\implies P(x) > 0$.
		- ### Contoh Soal Penentuan Domain
			- **Contoh 1**: $f(x) = \frac{1}{x+1}$
				- Syarat penyebut: $x + 1 \neq 0 \implies x \neq -1$
				- **Domain**: $(-\infty, -1) \cup (-1, \infty)$
			- **Contoh 2**: $f(x) = \sqrt{x+3}$
				- Syarat dalam akar: $x + 3 \ge 0 \implies x \ge -3$
				- **Domain**: $[-3, \infty)$
			- **Contoh 3**: $f(x) = \ln(x-2)$
				- Syarat logaritma: $x - 2 > 0 \implies x > 2$
				- **Domain**: $(2, \infty)$
	- ## 3. [[Sifat-Sifat Fungsi]]
		- ### Fungsi Genap dan Gasal (Ganjil)
			- **Fungsi Genap**: Memenuhi persamaan $f(-x) = f(x)$.
				- Secara geometris, grafiknya **simetris terhadap sumbu-Y**.
				- Contoh: $y = x^2, y = \cos x, y = |x|$.
			- **Fungsi Gasal**: Memenuhi persamaan $f(-x) = -f(x)$.
				- Secara geometris, grafiknya **simetris terhadap titik asal** $(0,0)$ (bisa diputar 180 derajat dan bentuknya sama).
				- Contoh: $y = x^3, y = \sin x$.
		- ### Fungsi Periodik
			- Fungsi yang nilainya berulang pada interval tertentu.
			- Memenuhi persamaan $f(x+p) = f(x)$ untuk suatu konstanta riil positif $p$. Konstanta $p$ terkecil disebut **periode**.
			- Contoh utama: Fungsi trigonometri seperti $y = \sin x$ (periode $2\pi$).
	- ## 4. [[Jenis-Jenis Fungsi]]
		- **Fungsi Polinomial (Suku Banyak)**: $f(x) = a_nx^n + a_{n-1}x^{n-1} + \dots + a_1x + a_0$. Domainnya adalah seluruh bilangan riil $(-\infty, \infty)$.
			- Jika $n=1 \implies$ **Fungsi Linier** (berbentuk garis lurus $y = mx + c$).
			- Jika $n=2 \implies$ **Fungsi Kuadrat** (berbentuk parabola $y = ax^2+bx+c$).
		- **Fungsi Rasional**: Rasio dari dua polinomial $f(x) = \frac{P(x)}{Q(x)}$. Domainnya adalah himpunan semua bilangan riil kecuali pembuat nol dari $Q(x)$.
		- **Fungsi Eksponensial**: $f(x) = a^x$ (dengan $a > 0$ dan $a \neq 1$) atau $f(x) = e^x$.
			- Ciri khas: Variabel berada di pangkat.
			- Domain: $(-\infty, \infty)$. Range: $(0, \infty)$ (kurva selalu di atas sumbu-x).
		- **Fungsi Logaritma**: $f(x) = ^a\log x$ atau $f(x) = \ln x$. Merupakan kebalikan (invers) dari fungsi eksponensial.
			- Domain: $(0, \infty)$ (hanya menerima nilai positif). Range: $(-\infty, \infty)$.
		- **Fungsi Sepotong-sepotong (Piecewise)**: Fungsi yang definisinya berbeda-beda tergantung pada interval nilai $x$-nya.
			- **Fungsi Nilai Mutlak**: $f(x) = |x|$. Definisinya: $f(x) = x$ jika $x \ge 0$, dan $f(x) = -x$ jika $x < 0$. Bentuk grafiknya menyerupai huruf 'V'.
			- **Fungsi Heaviside (Step function)**: Bernilai $0$ untuk $x < 0$ dan bernilai $1$ untuk $x \ge 0$.
		- **Fungsi Trigonometri**: Melibatkan relasi sudut segitiga ($\sin x, \cos x, \tan x, \sec x, \csc x, \cot x$). Ingat bahwa di dalam kalkulus, argumen dari fungsi trigonometri selalu diasumsikan dalam **Radian**, bukan derajat.