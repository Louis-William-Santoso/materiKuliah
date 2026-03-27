# Week 11: Geometri Ruang dan Fungsi Multivariabel
	- ## 1. [[Sistem Koordinat dan Geometri Ruang]] ($\mathbb{R}^3$)
		- **Sistem Koordinat Kartesius 3D**: Untuk menentukan posisi titik di dalam ruang, kita menggunakan tiga sumbu yang saling tegak lurus: sumbu-$x$, sumbu-$y$, dan sumbu-$z$. Titik direpresentasikan sebagai tripel berurutan $(x, y, z)$. 
		  
		  [Image of 3D Cartesian coordinate system]
		- **Jarak Antara Dua Titik**:
			- Jarak $d$ antara titik $P_1(x_1, y_1, z_1)$ dan $P_2(x_2, y_2, z_2)$ dihitung menggunakan perluasan Teorema Pythagoras:
			- $d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2 + (z_2 - z_1)^2}$
		- **Persamaan Permukaan Dasar di** $\mathbb{R}^3$:
			- **Bola (Sphere)**: Himpunan titik yang berjarak $r$ dari titik pusat $(a, b, c)$.
				- Persamaan: $(x - a)^2 + (y - b)^2 + (z - c)^2 = r^2$
			- **Bidang Datar (Plane)**: Permukaan datar tak terhingga di ruang 3D.
				- Persamaan umum: $Ax + By + Cz + D = 0$
			- **Permukaan Kuadratik (Quadric Surfaces)**:  Bentuk ruang yang persamaannya mengandung variabel berpangkat dua (misalnya Elipsoida, Paraboloida, Hiperboloida, dan Kerucut).
	- ## 2. [[Konsep Dasar Fungsi Multivariabel]]
		- **Definisi Fungsi Dua Variabel**: Jika $f$ adalah sebuah fungsi dengan dua variabel bebas $x$ dan $y$, maka $z = f(x, y)$ memetakan setiap pasangan berurutan $(x, y)$ di daerah asal (domain) ke tepat satu bilangan riil $z$.
			- **Domain ($D$)**: Himpunan semua pasangan $(x, y)$ di bidang-$xy$ yang membuat fungsi terdefinisi (aturan akar, pembagian, dan logaritma tetap berlaku seperti fungsi satu variabel).
			- **Range**: Himpunan nilai output $z$ di sumbu vertikal.
		- **Grafik Permukaan**: Grafik dari fungsi $z = f(x, y)$ adalah sebuah permukaan di ruang tiga dimensi.
		- **Kurva Ketinggian (Level Curves) dan Peta Kontur**:
			- Sangat sulit menggambar permukaan 3D di atas kertas 2D. Oleh karena itu, kita menggunakan kurva ketinggian.
			- Definisi: Proyeksi dari irisan antara permukaan $z = f(x, y)$ dengan bidang datar mendatar $z = c$ ke bidang-$xy$.
			- Persamaan kurva ketinggian: $f(x, y) = c$ (di mana $c$ adalah konstanta).
			- *Contoh di dunia nyata*: Peta topografi yang menunjukkan garis-garis elevasi gunung.
	- ## 3. [[Turunan Parsial (Partial Derivatives)]]
		- Karena ada lebih dari satu variabel bebas, turunan tidak lagi dilakukan pada satu arah saja, melainkan "secara parsial" atau pada arah sumbu tertentu.
		- **Turunan Parsial terhadap** $x$:
			- Notasi: $f_x, \frac{\partial f}{\partial x}, \frac{\partial z}{\partial x}$
			- **Aturan Praktis**: Turunkan fungsi terhadap variabel $x$, sementara variabel $y$ diperlakukan seperti angka konstan biasa.
		- **Turunan Parsial terhadap** $y$:
			- Notasi: $f_y, \frac{\partial f}{\partial y}, \frac{\partial z}{\partial y}$
			- **Aturan Praktis**: Turunkan fungsi terhadap variabel $y$, sementara variabel $x$ diperlakukan seperti angka konstan biasa.
		- **Contoh Perhitungan**:
			- Jika $f(x, y) = 3x^2y + \sin(xy)$
			- Maka turunan parsial terhadap $x$: $\frac{\partial f}{\partial x} = 6xy + y\cos(xy)$
			- Dan turunan parsial terhadap $y$: $\frac{\partial f}{\partial y} = 3x^2 + x\cos(xy)$
	- ## 4. [[Turunan Parsial Tingkat Tinggi]]
		- Sama seperti turunan biasa, kita bisa menurunkan lagi hasil turunan parsial pertama. Ada 4 macam turunan parsial kedua untuk fungsi $z = f(x, y)$:
		  1. $f_{xx} = \frac{\partial^2 f}{\partial x^2}$ (Turunkan terhadap $x$, lalu terhadap $x$ lagi)
		  2. $f_{yy} = \frac{\partial^2 f}{\partial y^2}$ (Turunkan terhadap $y$, lalu terhadap $y$ lagi)
		  3. $f_{xy} = \frac{\partial^2 f}{\partial y \partial x}$ (Turunkan terhadap $x$, lalu hasilnya diturunkan terhadap $y$)
		  4. $f_{yx} = \frac{\partial^2 f}{\partial x \partial y}$ (Turunkan terhadap $y$, lalu hasilnya diturunkan terhadap $x$)
		- **Teorema Clairaut**: Jika fungsi dan turunan parsial campurannya kontinu, maka nilai turunan campurannya akan sama $\implies f_{xy} = f_{yx}$.
	- ## 5. [[Vektor Gradien]] ($\nabla$)
		- **Definisi**: Gradien dari suatu fungsi $f(x, y)$ adalah sebuah fungsi vektor yang menggabungkan turunan parsial pertama menjadi komponen-komponen vektor.
		- **Notasi dan Rumus**: $\nabla f(x, y) = \langle f_x(x, y), f_y(x, y) \rangle = \frac{\partial f}{\partial x}\mathbf{i} + \frac{\partial f}{\partial y}\mathbf{j}$
		- **Makna Geometris yang Sangat Penting**:
			- Jika Anda berdiri di suatu titik pada suatu permukaan, vektor gradien di titik tersebut akan selalu menunjuk ke arah "tanjakan paling curam" (arah di mana fungsi $f$ bertambah paling cepat).
			- Panjang (modulus) dari vektor gradien mewakili laju perubahan maksimum dari fungsi tersebut.
			- Vektor gradien selalu tegak lurus (ortogonal) terhadap kurva ketinggian $f(x,y) = c$.