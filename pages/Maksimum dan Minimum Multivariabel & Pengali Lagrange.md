## 1. Maksimum dan Minimum Fungsi Multivariabel (Tanpa Kendala)
	- Konsepnya mirip dengan fungsi satu variabel, namun kita mencari titik puncak (bukit), lembah, atau titik pelana pada suatu permukaan 3D.
	- **Langkah 1: Cari Titik Kritis $(a, b)$**
		- Syarat titik stasioner: $f_x = 0$ **dan** $f_y = 0$. (Selesaikan sistem persamaan ini untuk mendapatkan nilai $x$ dan $y$).
	- **Langkah 2: Uji Turunan Parsial Kedua (Hessian / Uji D)**
		- Hitung diskriminan $D$ di titik kritis $(a, b)$:
		- $D = f_{xx}(a,b) \cdot f_{yy}(a,b) - [f_{xy}(a,b)]^2$
	- **Langkah 3: Ambil Kesimpulan**
		- Jika $D > 0$ dan $f_{xx} > 0 \implies$ Titik $(a,b)$ adalah **Minimum Lokal** (Lembah).
		- Jika $D > 0$ dan $f_{xx} < 0 \implies$ Titik $(a,b)$ adalah **Maksimum Lokal** (Puncak).
		- Jika $D < 0 \implies$ Titik $(a,b)$ adalah **Titik Pelana** (*Saddle Point*).
		- Jika $D = 0 \implies$ Uji gagal (tidak ada kesimpulan).
- ## 2. Masalah Maksimum-Minimum dengan Kendala (Pengali Lagrange)
	- Digunakan ketika kita harus mengoptimalkan suatu fungsi $f(x, y, z)$ (misal: mencari volume maksimum), namun dibatasi oleh suatu syarat atau kendala $g(x, y, z) = 0$ (misal: luas permukaan bahan terbatas).
	- **Metode Pengali Lagrange ($\lambda$)**:
	  1. Tentukan **Fungsi Utama** $f(x, y, z)$ yang ingin dimaksimalkan/diminimalkan.
	  2. Tentukan **Fungsi Kendala** $g(x, y, z) = 0$.
	  3. Buat fungsi bantuan (Fungsi Lagrange):
		- $G(x, y, z, \lambda) = f(x, y, z) + \lambda \cdot g(x, y, z)$
		  4. Cari titik kritis dengan men-nol-kan semua turunan parsial pertama dari $G$:
		- $G_x = 0 \implies f_x + \lambda g_x = 0$
		- $G_y = 0 \implies f_y + \lambda g_y = 0$
		- $G_z = 0 \implies f_z + \lambda g_z = 0$
		- $G_\lambda = 0 \implies g(x, y, z) = 0$ (Ini akan mengembalikan persamaan kendala itu sendiri).
		  5. Selesaikan sistem persamaan di atas untuk menemukan nilai $x, y, z$.
		  6. Substitusikan titik-titik $(x, y, z)$ yang didapat ke dalam Fungsi Utama $f(x, y, z)$ untuk melihat nilai mana yang paling besar (Maksimum) dan paling kecil (Minimum).