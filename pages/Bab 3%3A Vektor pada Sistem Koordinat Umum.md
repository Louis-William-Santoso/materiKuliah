# Catatan Mendalam: Bab 3 - Vektor pada Sistem Koordinat Umum
	- ## 1. Konsep Dasar Vektor
		- **Definisi Vektor**: Besaran yang memiliki nilai (panjang/magnitudo) dan arah. Berbeda dengan *skalar* yang hanya memiliki nilai saja.
		- **Notasi Vektor**: Biasanya dituliskan dengan huruf kecil yang dicetak tebal ($\mathbf{u}, \mathbf{v}$) atau dengan tanda panah di atasnya ($\vec{u}, \vec{v}$).
		- **Komponen Vektor**: Vektor dapat direpresentasikan dalam ruang berdimensi $n$ (ditulis $R^n$).
			- Di $R^2$ (2 Dimensi): $\mathbf{u} = (u_1, u_2)$
			- Di $R^3$ (3 Dimensi): $\mathbf{u} = (u_1, u_2, u_3)$
			- Di $R^n$ ($n$ Dimensi): $\mathbf{u} = (u_1, u_2, \dots, u_n)$
	- ## 2. Operasi Aritmatika Vektor
		- ### Penjumlahan dan Pengurangan Vektor
			- Dilakukan dengan menjumlahkan atau mengurangkan komponen-komponen yang seletak posisinya.
			- Jika $\mathbf{u} = (u_1, u_2, u_3)$ dan $\mathbf{v} = (v_1, v_2, v_3)$, maka:
				- $\mathbf{u} + \mathbf{v} = (u_1+v_1, u_2+v_2, u_3+v_3)$
				- $\mathbf{u} - \mathbf{v} = (u_1-v_1, u_2-v_2, u_3-v_3)$
			- *Interpretasi Geometris*: Penjumlahan dapat divisualisasikan menggunakan "Aturan Segitiga" (menyambung pangkal ke ujung) atau "Aturan Jajar Genjang".
		- ### Perkalian Vektor dengan Skalar
			- Jika $k$ adalah bilangan skalar (bilangan real) dan $\mathbf{u}$ adalah vektor, maka $k\mathbf{u}$ dilakukan dengan mengalikan setiap komponen vektor dengan $k$.
			- $k\mathbf{u} = (ku_1, ku_2, ku_3)$
			- *Sifat Arah*:
				- Jika $k > 0$, arah vektor tetap (hanya panjangnya yang berubah).
				- Jika $k < 0$, arah vektor menjadi berlawanan 180 derajat.
	- ## 3. Membentuk Vektor dari Dua Titik Koordinat
		- Sebuah vektor seringkali direpresentasikan dari titik pangkal $P_1$ menuju titik ujung $P_2$. Vektor ini dilambangkan dengan $\vec{P_1P_2}$.
		- **Cara Menghitung**: Komponen vektor didapat dengan mengurangi koordinat titik ujung dengan koordinat titik pangkal (*Ujung kurangi Pangkal*).
		- **Contoh Rumus di $R^3$**:
			- Diketahui titik $P_1(x_1, y_1, z_1)$ dan $P_2(x_2, y_2, z_2)$.
			- $\vec{P_1P_2} = (x_2 - x_1, y_2 - y_1, z_2 - z_1)$.
	- ## 4. Norm (Panjang Vektor)
		- **Definisi**: Norm atau panjang dari sebuah vektor $\mathbf{u}$ dinotasikan dengan $||\mathbf{u}||$. Rumus ini didasarkan pada Teorema Pythagoras.
		- **Rumus Norm di $R^2$**:
			- Jika $\mathbf{u} = (u_1, u_2)$, maka $||\mathbf{u}|| = \sqrt{u_1^2 + u_2^2}$
		- **Rumus Norm di $R^3$**:
			- Jika $\mathbf{u} = (u_1, u_2, u_3)$, maka $||\mathbf{u}|| = \sqrt{u_1^2 + u_2^2 + u_3^2}$
		- **Vektor Satuan (Unit Vector)**: Vektor yang panjangnya (norm-nya) tepat sama dengan 1. Jika kita memiliki vektor $\mathbf{v}$ sembarang yang bukan nol, kita bisa mencari vektor satuan yang searah dengannya menggunakan rumus: $\hat{v} = \frac{\mathbf{v}}{||\mathbf{v}||}$.
	- ## 5. Sifat-sifat (Aksioma) Operasi Vektor
		- Jika $\mathbf{u}, \mathbf{v}, \mathbf{w}$ adalah vektor dan $k, l$ adalah skalar, maka berlaku sifat berikut yang mengizinkan kita melakukan manipulasi aljabar pada vektor:
		  1. Komutatif Penjumlahan: $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$
		  2. Asosiatif Penjumlahan: $(\mathbf{u} + \mathbf{v}) + \mathbf{w} = \mathbf{u} + (\mathbf{v} + \mathbf{w})$
		  3. Identitas Penjumlahan: Terdapat vektor nol ($\mathbf{0}$) sehingga $\mathbf{u} + \mathbf{0} = \mathbf{u}$
		  4. Invers Penjumlahan: $\mathbf{u} + (-\mathbf{u}) = \mathbf{0}$
		  5. Distributif Skalar 1: $k(\mathbf{u} + \mathbf{v}) = k\mathbf{u} + k\mathbf{v}$
		  6. Distributif Skalar 2: $(k + l)\mathbf{u} = k\mathbf{u} + l\mathbf{u}$
		  7. Asosiatif Skalar: $k(l\mathbf{u}) = (kl)\mathbf{u}$
		  8. Identitas Skalar: $1\mathbf{u} = \mathbf{u}$
	- ## 🧠 6. Mini Quiz: Uji Pemahaman Bab 3
		- **Soal 1**: Diketahui titik pangkal $P_1(3, -8)$ dan titik ujung $P_2(-4, 6)$. Tentukan komponen vektor $\vec{P_1P_2}$!
			- *Jawaban*: Menggunakan rumus *Ujung - Pangkal*.
			- $\vec{P_1P_2} = (-4 - 3, 6 - (-8)) = (-7, 14)$.
		- **Soal 2**: Jika $\mathbf{u} = (-3, 1, 2)$ dan $\mathbf{v} = (4, 0, -8)$, hitunglah nilai dari $3\mathbf{v} - \mathbf{u}$!
			- *Jawaban*:
			- $3\mathbf{v} = 3(4, 0, -8) = (12, 0, -24)$.
			- $3\mathbf{v} - \mathbf{u} = (12, 0, -24) - (-3, 1, 2) = (12 - (-3), 0 - 1, -24 - 2)$.
			- Hasil akhir: $(15, -1, -26)$.
		- **Soal 3**: Apa yang terjadi secara geometris jika sebuah vektor dikalikan dengan skalar bernilai $-2$?
			- *Jawaban*: Panjang (magnitudo) vektor tersebut akan menjadi dua kali lipat dari panjang semula, namun arah panahnya berbalik $180^\circ$ (berlawanan arah).
		- **Soal 4**: Bagaimana cara mencari nilai norm (panjang) dari vektor $\mathbf{w} = (0, 3, 4)$?
			- *Jawaban*: $||\mathbf{w}|| = \sqrt{0^2 + 3^2 + 4^2} = \sqrt{0 + 9 + 16} = \sqrt{25} = 5$. Panjang vektor tersebut adalah 5.