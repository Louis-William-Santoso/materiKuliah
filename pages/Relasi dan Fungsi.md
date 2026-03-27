- Materi ini membahas bagaimana elemen-elemen dari satu atau lebih himpunan saling berhubungan, serta aturan ketat yang mendasari pemetaan elemen tersebut dalam bentuk fungsi. Konsep ini adalah tulang punggung dari basis data relasional dan pemrograman fungsional.
- ## 1. [[Konsep Dasar: Cartesian Product (Hasil Kali Kartesian)]]
	- **Definisi:** Misalkan $A$ dan $B$ adalah himpunan. Hasil kali kartesian antara $A$ dan $B$, dinotasikan sebagai $A \times B$, adalah himpunan **semua kemungkinan pasangan terurut** $(a, b)$ di mana elemen $a$ berasal dari $A$ dan elemen $b$ berasal dari $B$.
	- **Notasi Logika:** $A \times B = \{(a, b) \mid a \in A \text{ dan } b \in B\}$
	- **Kardinalitas (Jumlah Elemen):** Jika himpunan $A$ memiliki $m$ elemen dan himpunan $B$ memiliki $n$ elemen, maka jumlah elemen dari $A \times B$ adalah $m \times n$. Dinotasikan: $|A \times B| = |A| \cdot |B|$.
	- **Contoh:** Jika $A = \{1, 2\}$ dan $B = \{a, b\}$, maka $A \times B = \{(1, a), (1, b), (2, a), (2, b)\}$.
	- *Info Tambahan:* Ingat bahwa pasangan terurut $(a, b)$ **tidak sama** dengan $(b, a)$. Oleh karena itu, $A \times B \neq B \times A$ (kecuali $A = B$ atau salah satunya adalah himpunan kosong).
- ## 2. [[Relasi Biner]]
	- **Definisi:** Relasi biner $R$ dari himpunan $A$ ke himpunan $B$ adalah himpunan bagian (subset) dari Cartesian Product $A \times B$.
	- **Notasi:** Jika $(a, b) \in R$, kita dapat menuliskannya sebagai $aRb$ (dibaca: $a$ berelasi dengan $b$). Jika tidak berelasi, ditulis $a \not R b$.
	- **Relasi pada Sebuah Himpunan:** Seringkali kita melihat relasi dari himpunan $A$ ke himpunan $A$ itu sendiri. Ini adalah himpunan bagian dari $A \times A$ (atau $A^2$).
- ## 3. [[Sifat-Sifat Relasi (pada Himpunan A)]]
	- **Refleksif (Reflexive):**
		- Suatu relasi $R$ bersifat refleksif jika setiap elemen di $A$ berelasi dengan dirinya sendiri.
		- Syarat: $\forall a \in A, (a, a) \in R$.
	- **Simetris (Symmetric):**
		- Suatu relasi $R$ bersifat simetris jika $a$ berelasi dengan $b$, maka $b$ juga pasti berelasi dengan $a$.
		- Syarat: Jika $(a, b) \in R$, maka $(b, a) \in R$.
	- **Transitif (Transitive):**
		- Suatu relasi $R$ bersifat transitif jika $a$ berelasi dengan $b$ dan $b$ berelasi dengan $c$, maka $a$ pasti berelasi dengan $c$. (Hukum domino/perantara).
		- Syarat: Jika $(a, b) \in R$ dan $(b, c) \in R$, maka $(a, c) \in R$.
- ## 4. [[Relasi Ekivalen]]
	- **Definisi:** Sebuah relasi disebut **Relasi Ekivalen** jika dan hanya jika relasi tersebut memenuhi KETIGA sifat di atas sekaligus: **Refleksif, Simetris, dan Transitif**.
	- **Penyelesaian Masalah (Membuktikan Relasi Ekivalen):**
		- *Masalah:* Misalkan $m > 1$ adalah bilangan bulat positif. Dua bilangan bulat $a$ dan $b$ disebut kongruen modulo $m$ ($a \equiv b \pmod m$) jika $m$ membagi habis $(a - b)$. Buktikan bahwa relasi $R = \{(a, b) \mid a \equiv b \pmod m\}$ adalah relasi ekivalen pada himpunan bilangan bulat!
		- *Penyelesaian:*
		  1.  **Cek Refleksif:** Ambil sembarang bilangan $a$. Apakah $a \equiv a \pmod m$? Ya, karena $(a - a) = 0$, dan $m$ membagi habis $0$. (Terbukti Refleksif).
		  2.  **Cek Simetris:** Jika $a \equiv b \pmod m$, maka $m$ membagi $(a - b)$. Artinya $(a - b) = km$ untuk suatu bilangan bulat $k$. Kalikan dengan $-1$ menjadi $(b - a) = (-k)m$. Karena $-k$ juga bilangan bulat, maka $m$ membagi $(b - a)$, sehingga $b \equiv a \pmod m$. (Terbukti Simetris).
		  3.  **Cek Transitif:** Jika $a \equiv b \pmod m$ (berarti $a - b = k_1m$) dan $b \equiv c \pmod m$ (berarti $b - c = k_2m$). Jumlahkan keduanya: $(a - b) + (b - c) = k_1m + k_2m$. Hasilnya $(a - c) = (k_1 + k_2)m$. Karena $(k_1 + k_2)$ adalah bilangan bulat, maka $m$ membagi $(a - c)$, sehingga $a \equiv c \pmod m$. (Terbukti Transitif).
		- *Kesimpulan:* Karena memenuhi ketiga syarat, relasi kongruen modulo $m$ terbukti adalah Relasi Ekivalen.
- ## 5. [[Fungsi (Pemetaan)]]
	- **Definisi Ketat:** Misalkan $A$ dan $B$ adalah himpunan. Suatu fungsi $f$ dari $A$ ke $B$ ($f: A \rightarrow B$) adalah relasi biner yang mengaitkan **setiap** elemen di $A$ dengan **tepat satu** elemen di $B$.
	- **Terminologi Penting:**
		- **Domain (Daerah Asal):** Himpunan $A$. (Semua elemen di sini WAJIB dipetakan dan tidak boleh bercabang/selingkuh).
		- **Kodomain (Daerah Kawan/Hasil):** Himpunan $B$.
		- **Range (Daerah Hasil Aktual):** Himpunan semua nilai $f(a)$ di dalam kodomain yang benar-benar memiliki pasangan dari domain. Range adalah subset dari Kodomain.
	- **Penyelesaian Masalah (Identifikasi Fungsi):**
		- *Masalah:* Jika $A = \{1, 2, 3\}$ dan $B = \{a, b, c\}$. Manakah dari relasi berikut yang merupakan fungsi?
		  1. $f_1 = \{(1, a), (2, b), (3, c), (1, b)\}$
		  2. $f_2 = \{(1, a), (2, b)\}$
		  3. $f_3 = \{(1, a), (2, a), (3, b)\}$
		- *Penyelesaian:*
			- $f_1$ **Bukan Fungsi**, karena elemen domain `1` memiliki dua pasangan (bercabang ke `a` dan `b`).
			- $f_2$ **Bukan Fungsi**, karena elemen domain `3` tidak dipetakan ke manapun. (Semua elemen domain wajib punya pasangan).
			- $f_3$ **Adalah Fungsi**, karena setiap elemen domain (`1`, `2`, `3`) memiliki tepat satu pasangan di kodomain. (Boleh saja dua elemen domain menunjuk ke elemen kodomain yang sama, seperti `a`).
- ## 6. [[Jenis-Jenis Fungsi Khusus]]
	- **Fungsi Injektif (One-to-One / Satu-Satu):**
		- Tidak ada dua elemen berbeda di domain yang dipetakan ke elemen yang sama di kodomain. (Elemen kodomain tidak boleh "dipilih" dua kali).
		- Syarat: Jika $f(a) = f(b)$, maka wajib $a = b$.
	- **Fungsi Surjektif (Onto / Pada):**
		- Setiap elemen di kodomain pasti memiliki minimal satu pasangan dari domain. Tidak ada elemen kodomain yang "jomblo".
		- Syarat: Range = Kodomain.
	- **Fungsi Bijektif (Korespondensi Satu-Satu):**
		- Sebuah fungsi yang sekaligus bersifat **Injektif** DAN **Surjektif**. Setiap elemen $A$ berpasangan tepat satu dengan elemen $B$, dan tidak ada yang tersisa di kedua himpunan. Syarat utamanya adalah kardinalitas $|A| = |B|$.
- ## 7. [[Komposisi Fungsi]]
	- **Definisi:** Menggabungkan dua fungsi menjadi satu proses berantai. Jika ada fungsi $g: A \rightarrow B$ dan fungsi $f: B \rightarrow C$, maka komposisi fungsi $f \circ g$ (dibaca: $f$ bundaran $g$) adalah fungsi dari $A$ ke $C$.
	- **Cara Kerja:** Elemen dievaluasi dari kanan ke kiri. Rumusnya adalah $(f \circ g)(x) = f(g(x))$. Artinya, masukkan nilai $x$ ke fungsi $g$ dulu, lalu hasilnya dimasukkan ke fungsi $f$.
	- *Contoh:* Jika $g = \{(1, a), (2, a), (3, c)\}$ dan $f = \{(a, y), (b, x), (c, z)\}$, maka $f \circ g = \{(1, y), (2, y), (3, z)\}$. (Angka 1 masuk ke $g$ jadi $a$, lalu $a$ masuk ke $f$ jadi $y$).