# Week 12-13: Turunan Fungsi Multivariabel dan Aplikasinya
	- ## 1. [[Turunan Parsial]]
		- **Konsep Dasar**: Karena fungsi multivariabel memiliki lebih dari satu variabel bebas (misal $z = f(x,y)$), kita tidak bisa menurunkannya secara serentak terhadap semua variabel. Kita harus menurunkannya "secara parsial" (satu per satu).
		- **Turunan Pertama**:
			- **Terhadap** $x$: Dinotasikan $f_x$ atau $\frac{\partial f}{\partial x}$. Cara menghitungnya: Turunkan fungsi terhadap variabel $x$, anggap variabel $y$ (dan variabel lainnya) sebagai suatu **konstanta/angka biasa**.
			- **Terhadap** $y$: Dinotasikan $f_y$ atau $\frac{\partial f}{\partial y}$. Cara menghitungnya: Turunkan fungsi terhadap variabel $y$, anggap variabel $x$ sebagai **konstanta/angka biasa**.
		- **Turunan Kedua (Tingkat Tinggi)**: Turunan pertama diturunkan lagi. Ada 4 jenis untuk fungsi dua variabel:
		  1. $f_{xx} = \frac{\partial^2 f}{\partial x^2}$ (Turunkan terhadap $x$, lalu terhadap $x$ lagi)
		  2. $f_{yy} = \frac{\partial^2 f}{\partial y^2}$ (Turunkan terhadap $y$, lalu terhadap $y$ lagi)
		  3. $f_{xy} = \frac{\partial^2 f}{\partial y \partial x}$ (Turunkan terhadap $x$, lalu terhadap $y$) $\implies$ *Turunan Campuran*
		  4. $f_{yx} = \frac{\partial^2 f}{\partial x \partial y}$ (Turunkan terhadap $y$, lalu terhadap $x$) $\implies$ *Turunan Campuran*
		- **Teorema Clairaut**: Jika turunan parsial kedua kontinu, maka nilai turunan campurannya selalu sama: $f_{xy} = f_{yx}$.
	- ## 2. [[Diferensial Total]]
		- Mengukur estimasi perubahan total pada fungsi $z$ akibat perubahan kecil serentak pada variabel $x$ dan $y$.
		- **Rumus Diferensial Total** ($dz$):
			- $dz = \frac{\partial z}{\partial x} dx + \frac{\partial z}{\partial y} dy$
			- Jika fungsinya tiga variabel $w = f(x, y, z)$:
			- $dw = \frac{\partial w}{\partial x} dx + \frac{\partial w}{\partial y} dy + \frac{\partial w}{\partial z} dz$
	- ## 3. [[Aturan Rantai (Turunan Fungsi Komposit)]]
		- Jika $z = f(x, y)$, di mana $x$ dan $y$ masing-masing adalah fungsi dari variabel lain, misalnya $t$ (yaitu $x = g(t)$ dan $y = h(t)$), maka turunan total $z$ terhadap $t$ adalah:
			- $\frac{dz}{dt} = \frac{\partial z}{\partial x} \frac{dx}{dt} + \frac{\partial z}{\partial y} \frac{dy}{dt}$
		- Jika $x$ dan $y$ masing-masing adalah fungsi dari *dua* variabel $s$ dan $t$ ($x = g(s,t), y = h(s,t)$), maka:
			- $\frac{\partial z}{\partial s} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial s} + \frac{\partial z}{\partial y} \frac{\partial y}{\partial s}$
			- $\frac{\partial z}{\partial t} = \frac{\partial z}{\partial x} \frac{\partial x}{\partial t} + \frac{\partial z}{\partial y} \frac{\partial y}{\partial t}$
		- *Tips*: Gunakan **diagram pohon** untuk memetakan alur dari variabel tak bebas (paling atas) hingga variabel bebas (paling bawah) agar tidak ada jalur suku yang terlewat.
	- ## 4. Turunan Fungsi Implisit
		- Digunakan jika variabel tidak bisa dipisahkan secara eksplisit ke satu ruas. Anda bisa menggunakan turunan parsial untuk menyelesaikannya dengan lebih cepat.
		- Misalkan suatu persamaan didefinisikan secara implisit oleh $F(x, y) = 0$, maka:
			- $\frac{dy}{dx} = -\frac{F_x}{F_y}$ (Syarat: $F_y \neq 0$)
		- Untuk fungsi ruang $F(x, y, z) = 0$:
			- $\frac{\partial z}{\partial x} = -\frac{F_x}{F_z}$ dan $\frac{\partial z}{\partial y} = -\frac{F_y}{F_z}$