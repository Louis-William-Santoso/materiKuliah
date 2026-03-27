## 1. [[Definisi dan Konsep Dasar]]
	- **Definisi:** Himpunan adalah kumpulan objek atau benda yang berbeda dan terdefinisi dengan jelas (*well-defined*). Terdefinisi dengan jelas artinya kita dapat memastikan dengan mutlak apakah suatu objek termasuk dalam himpunan tersebut atau tidak.
	- **Manfaat Mempelajari Himpunan:**
		- Melatih cara pandang berbasis sistem (*See things in terms of systems*).
		- Mengorganisasikan data/objek ke dalam kelompok yang logis.
		- Menjadi fondasi dasar untuk memahami logika matematika dan basis data (relational database).
	- **Notasi Dasar:**
		- Nama himpunan selalu ditulis dengan huruf **KAPITAL** (Contoh: $A, B, C$).
		- Anggota/elemen himpunan ditulis di dalam kurung kurawal $\{\}$.
		- Elemen tunggal dari himpunan dinotasikan dengan huruf kecil. Jika $x$ adalah anggota himpunan $A$, maka ditulis $x \in A$. Jika bukan anggota, ditulis $x \notin A$.
	- **Aturan Penting Elemen:**
		- Penulisan anggota di dalam himpunan tidak mempedulikan urutan.
		- Penulisan anggota **hanya boleh satu kali** (tidak boleh ada duplikasi). Contoh: $A = \{1, a, b, 8, b\}$ adalah penulisan yang salah, seharusnya $A = \{1, a, b, 8\}$.
	- **Kardinalitas ($n(A)$ atau $|A|$):** Merupakan jumlah elemen/anggota yang *berbeda* di dalam suatu himpunan.
		- *Contoh:* Jika $B = \{1, \{2, 3\}, \{4\}, 5\}$, maka kardinalitasnya adalah $|B| = 4$. Perhatikan bahwa himpunan di dalam himpunan dihitung sebagai satu elemen kesatuan.
- ## 2. [[Jenis-jenis Himpunan dan Hubungannya]]
	- **Himpunan Semesta ($S$ atau $U$):** Himpunan yang memuat semua elemen atau objek yang sedang dibicarakan.
	- **Himpunan Kosong** ($\emptyset$ atau $\{\}$): Himpunan yang tidak memiliki anggota sama sekali. Kardinalitasnya adalah 0. *Catatan:* $\{\emptyset\}$ bukanlah himpunan kosong, melainkan himpunan yang berisi satu elemen (yaitu simbol kosong).
	- **Himpunan Bagian** (Subset / $\subseteq$): $A \subseteq B$ berarti *setiap* anggota himpunan $A$ juga merupakan anggota himpunan $B$. (Boleh jadi $A$ persis sama dengan $B$).
	- **Himpunan Bagian Sejati** (Proper Subset / $\subset$): $A \subset B$ berarti seluruh anggota $A$ ada di $B$, tetapi $A$ **tidak sama dengan** $B$ (minimal ada satu elemen di $B$ yang tidak ada di $A$).
	- **Himpunan Ekivalen** ($\sim$): Dua himpunan dikatakan ekivalen jika jumlah anggotanya sama ($|A| = |B|$), meskipun isi elemennya berbeda sama sekali.
	- **Himpunan Sama** ($=$): Dua himpunan dikatakan sama jika keduanya memiliki elemen yang sama persis, tanpa mempedulikan urutan.
- ## 3. [[Operasi pada Himpunan]]
	- Operasi himpunan digunakan untuk memanipulasi dan menggabungkan data. Hal ini sering direpresentasikan secara visual menggunakan Diagram Venn. 
	  
	  [Image of Venn diagram set theory operations]
	- **Gabungan** (Union / $\cup$):
		- Himpunan yang berisi seluruh elemen yang ada di $A$, ada di $B$, atau ada di keduanya.
		- Notasi Logika: $A \cup B = \{x \mid x \in A \text{ atau } x \in B\}$
	- **Irisan** (Intersection / $\cap$):
		- Himpunan yang berisi elemen-elemen yang **hanya** muncul secara bersamaan di $A$ dan $B$.
		- Notasi Logika: $A \cap B = \{x \mid x \in A \text{ dan } x \in B\}$
		- *Info Tambahan:* Jika $A \cap B = \emptyset$, maka kedua himpunan tersebut disebut *saling lepas* (disjoint).
	- **Selisih** (Difference / $-$):
		- $A - B$ adalah himpunan elemen yang mutlak milik $A$, tetapi tidak boleh ada di $B$.
		- *Contoh:* $\{a, b, c\} - \{a, d\} = \{b, c\}$.
	- **Komplemen** ($A^c$ atau $A'$):
		- Semua elemen di himpunan Semesta ($S$) yang **bukan** merupakan elemen dari $A$.
	- **Beda Setangkup** (Symmetric Difference / $\oplus$):
		- Himpunan elemen yang ada di $A$ atau di $B$, **tetapi tidak di keduanya** (membuang irisannya).
		- Mirip dengan logika XOR pada ilmu komputer.
		- *Contoh:* $\{a, b\} \oplus \{a, c\} = \{b, c\}$.
	- **Himpunan Kuasa** (Power Set / $P(A)$):
		- Himpunan yang elemennya adalah *seluruh kemungkinan himpunan bagian* dari $A$.
		- Jika $A$ memiliki $n$ elemen, maka jumlah elemen pada Himpunan Kuasa adalah $2^n$.
		- *Contoh:* Jika $A = \{1, 2\}$, maka $P(A) = \{\emptyset, \{1\}, \{2\}, \{1, 2\}\}$.
- ## 4. [[Hukum-Hukum Aljabar Himpunan]]
	- Memahami hukum ini penting untuk menyederhanakan ekspresi himpunan yang kompleks tanpa harus menggambar Diagram Venn.
	- **Hukum Identitas:** $A \cup \emptyset = A$ dan $A \cap S = A$
	- **Hukum Ikatan / Dominasi:** $A \cup S = S$ dan $A \cap \emptyset = \emptyset$
	- **Hukum Komplemen:** $A \cup A^c = S$ dan $A \cap A^c = \emptyset$
	- **Hukum Idempoten:** $A \cup A = A$ dan $A \cap A = A$
	- **Hukum Involusi:** $(A^c)^c = A$ (Komplemen yang dikomplemenkan kembali ke awal).
- ## 5. [[Penyelesaian Masalah: Prinsip Inklusi-Eksklusi]]
	- **Konsep Dasar:** Saat menghitung total gabungan elemen dari beberapa himpunan, kita tidak bisa sekadar menjumlahkan kardinalitasnya karena elemen yang beririsan akan dihitung lebih dari sekali (double counting).
	- **Rumus 2 Himpunan:** $|A \cup B| = |A| + |B| - |A \cap B|$
	- **Rumus 3 Himpunan:** $|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$
	- **Contoh Soal & Penjelasan (Habis Dibagi):**
		- *Masalah:* Berapa banyaknya bilangan bulat antara 1 dan 100 yang habis dibagi 3 atau 5?
		- *Penyelesaian:*
		  1. Tetapkan: Himpunan $A$ (habis dibagi 3) dan Himpunan $B$ (habis dibagi 5).
		  2. Hitung jumlah elemen $A$: $|A| = \lfloor 100/3 \rfloor = 33$. (Fungsi floor $\lfloor \dots \rfloor$ membulatkan ke bawah).
		  3. Hitung jumlah elemen $B$: $|B| = \lfloor 100/5 \rfloor = 20$.
		  4. Hitung irisan (bilangan yang habis dibagi 3 DAN 5, yaitu Kelipatan Persekutuan Terkecil / KPK-nya = 15): $|A \cap B| = \lfloor 100/15 \rfloor = 6$.
		  5. Substitusi ke rumus: $|A \cup B| = 33 + 20 - 6 = 47$.
		  6. *Kesimpulan:* Terdapat 47 bilangan.
	- **Contoh Soal & Penjelasan (Survei 3 Himpunan):**
		- *Masalah:* Dari survei 270 orang: 64 suka apel, 94 suka brokoli, 58 suka kembang kol. Irisan: 26 suka apel & brokoli, 28 apel & kembang kol, 22 brokoli & kembang kol. 14 orang suka ketiganya. Berapa yang tidak suka satupun?
		- *Penyelesaian:*
		  1. Cari dulu total orang yang suka minimal satu sayur/buah (Gabungan ketiganya).
		  2. $|A \cup B \cup C| = 64 + 94 + 58 - 26 - 28 - 22 + 14$
		  3. $|A \cup B \cup C| = 154$ orang.
		  4. Untuk mencari yang *tidak suka satupun*, kurangi himpunan semesta (total peserta) dengan total gabungan himpunan: $270 - 154 = 116$.
		  5. *Kesimpulan:* 116 orang tidak menyukai satupun dari ketiga jenis makanan tersebut.