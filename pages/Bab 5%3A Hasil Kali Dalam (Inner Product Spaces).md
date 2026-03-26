## 1. Konsep Dasar Hasil Kali Dalam
	- **Definisi**: Hasil kali dalam (Inner Product) adalah sebuah fungsi yang mengaitkan setiap pasang elemen di dalam suatu ruang vektor (misalnya vektor $\mathbf{u}$ dan $\mathbf{v}$) dengan sebuah bilangan real skalar. Notasi umumnya ditulis sebagai $\langle \mathbf{u}, \mathbf{v} \rangle$.
	- Konsep ini merupakan **perluasan (generalisasi)** dari konsep *dot product* (hasil kali titik) pada vektor ruang Euclidian ($R^2$ atau $R^3$), sehingga dapat diaplikasikan pada ruang vektor yang lebih abstrak seperti ruang matriks atau ruang fungsi.
	- **Empat Aksioma Utama**: Agar suatu fungsi bisa disebut "hasil kali dalam", ia harus memenuhi:
	  1. **Simetri**: $\langle \mathbf{u}, \mathbf{v} \rangle = \langle \mathbf{v}, \mathbf{u} \rangle$
	  2. **Penambahan (Aditivitas)**: $\langle \mathbf{u} + \mathbf{w}, \mathbf{v} \rangle = \langle \mathbf{u}, \mathbf{v} \rangle + \langle \mathbf{w}, \mathbf{v} \rangle$
	  3. **Homogenitas Skalar**: $\langle k\mathbf{u}, \mathbf{v} \rangle = k \langle \mathbf{u}, \mathbf{v} \rangle$ (di mana $k$ adalah skalar)
	  4. **Kepositifan**: $\langle \mathbf{u}, \mathbf{u} \rangle \ge 0$, dan $\langle \mathbf{u}, \mathbf{u} \rangle = 0$ jika dan hanya jika $\mathbf{u} = \mathbf{0}$.
- ## 2. Hasil Kali Dalam pada Ruang Matriks
	- Hasil kali dalam tidak hanya eksklusif untuk vektor berjejer. Pada ruang matriks bujur sangkar (contoh $M_{22}$), kita dapat mendefinisikan aturan hasil kali dalam.
	- **Formula Hasil Kali Dalam $M_{22}$**:
		- Jika diketahui matriks $U = \begin{pmatrix} u_1 & u_2 \\ u_3 & u_4 \end{pmatrix}$ dan $V = \begin{pmatrix} v_1 & v_2 \\ v_3 & v_4 \end{pmatrix}$
		- Maka hasil kali dalamnya didefinisikan dengan mengalikan elemen-elemen yang seletak lalu menjumlahkannya:
		- $$\langle U, V \rangle = u_1v_1 + u_2v_2 + u_3v_3 + u_4v_4$$
- ## 3. Panjang (Norm), Jarak, dan Sudut
	- Berbekal formula $\langle \mathbf{u}, \mathbf{v} \rangle$, kita bisa mendefinisikan aspek geometris pada ruang abstrak.
	- **Norm (Panjang/Magnitudo)**: Diukur dengan mengakar-kuadratkan hasil kali dalam elemen dengan dirinya sendiri.
		- $$||\mathbf{u}|| = \sqrt{\langle \mathbf{u}, \mathbf{u} \rangle}$$
	- **Jarak Dua Elemen**: Jarak antara elemen $U$ dan $V$ disimbolkan dengan $d(U, V)$.
		- $$d(U, V) = ||U - V|| = \sqrt{\langle U - V, U - V \rangle}$$
	- **Sudut Antara Dua Elemen**:
		- Menggunakan modifikasi rumus kosinus:
		- $$\cos \theta = \frac{\langle U, V \rangle}{||U|| \cdot ||V||}$$
- ## 4. Ortogonalitas (Tegak Lurus)
	- **Definisi Ortogonal**: Dua elemen dalam sebuah ruang hasil kali dalam dikatakan **ortogonal** (tegak lurus secara geometris) jika hasil kali dalam dari keduanya bernilai **Nol**.
		- $$\langle U, V \rangle = 0$$
	- Hal ini masuk akal secara rumus sudut, karena jika $\cos \theta = 0$, maka $\theta = 90^\circ$ (tegak lurus).
- ## 5. Bedah Contoh Kasus & Penyelesaian Masalah
	- ### Kasus 1: Menghitung Hasil Kali Dalam Matriks
		- *Soal*: Diketahui $U = \begin{pmatrix} -1 & 0 \\ 3 & 2 \end{pmatrix}$ dan $V = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}$. Tentukan nilai $\langle U, V \rangle$!
		- *Penyelesaian*: Kalikan elemen yang seletak.
			- $\langle U, V \rangle = (-1)(1) + (0)(2) + (3)(3) + (2)(4)$
			- $\langle U, V \rangle = -1 + 0 + 9 + 8 = 16$.
	- ### Kasus 2: Ortogonalitas Vektor Mengandung Variabel
		- *Soal*: Untuk nilai $m$ berapakah vektor $\mathbf{u} = (m, m, 1)$ dan $\mathbf{v} = (m, 5, 6)$ ortogonal di $R^3$?
		- *Penyelesaian*: Syarat ortogonal adalah $\langle \mathbf{u}, \mathbf{v} \rangle = 0$.
			- $(m \cdot m) + (m \cdot 5) + (1 \cdot 6) = 0$
			- $m^2 + 5m + 6 = 0$
			- Cari akar-akar persamaan kuadratnya: $(m + 2)(m + 3) = 0$.
			- Jawabannya, kedua vektor akan ortogonal jika nilai $m = -2$ atau $m = -3$.
- ## 🧠 6. Mini Quiz: Uji Pemahaman Bab 5
	- **Soal 1**: Jika sebuah ruang hasil kali dalam memberikan hasil $\langle A, A \rangle = -4$, aksioma apa yang telah dilanggar?
		- *Jawaban*: Melanggar Aksioma 4 (Kepositifan). Hasil kali dalam sebuah elemen dengan dirinya sendiri $\langle A, A \rangle$ harus selalu lebih besar atau sama dengan nol ($\ge 0$). Nilai panjang/norm sebuah objek tidak mungkin negatif.
	- **Soal 2**: Apa yang terjadi pada nilai $\cos \theta$ jika kita menghitung sudut antara vektor $\mathbf{u}$ dengan dirinya sendiri ($\mathbf{u}$)?
		- *Jawaban*: Nilai $\cos \theta$ akan sama dengan 1. Karena $\cos \theta = \frac{\langle \mathbf{u}, \mathbf{u} \rangle}{||\mathbf{u}|| \cdot ||\mathbf{u}||} = \frac{||\mathbf{u}||^2}{||\mathbf{u}||^2} = 1$. Ini menandakan sudutnya adalah $0^\circ$ (berimpit).
	- **Soal 3**: Diberikan polinomial $P_1 = 2x + 1$ dan $P_2 = x - 2$. Jika aturan hasil kali dalamnya adalah $\langle P_1, P_2 \rangle = (kof. x P_1 \cdot kof. x P_2) + (konstanta P_1 \cdot konstanta P_2)$, apakah kedua polinomial tersebut ortogonal?
		- *Jawaban*: Mari kita hitung. $\langle P_1, P_2 \rangle = (2 \cdot 1) + (1 \cdot -2) = 2 - 2 = 0$. Karena hasil kali dalamnya adalah 0, maka secara matematis kedua polinomial tersebut **ortogonal** di ruang fungsi yang dideskripsikan.