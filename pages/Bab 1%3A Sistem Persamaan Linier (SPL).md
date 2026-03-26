## 1. Definisi Dasar
	- **Persamaan Linier**: Persamaan yang melibatkan $n$ peubah (variabel) $x_1, x_2, \dots, x_n$ dan dapat dinyatakan dalam bentuk matematis:
		- $a_1x_1 + a_2x_2 + \dots + a_nx_n = b$
		- *Keterangan*: $a_1, a_2, \dots, a_n$ dan $b$ adalah konstanta bilangan real.
	- **Sistem Persamaan Linier (SPL)**: Kumpulan dari beberapa persamaan linier. Solusi dari persamaan linier adalah urutan $n$ bilangan $s_1, s_2, \dots, s_n$ sehingga persamaan dipenuhi jika disubstitusikan terhadap $x_1 = s_1, x_2 = s_2, \dots, x_n = s_n$.
- ## 2. Klasifikasi Solusi SPL
	- Sebuah SPL tidak selalu memiliki satu jawaban tunggal. Terdapat 3 kemungkinan solusi untuk sebuah SPL:
	  1. **Ada Satu Penyelesaian (Tunggal)**: Kondisi ini disebut sebagai **SPL Konsisten**.
	  2. **Tak Hingga Banyaknya Penyelesaian**: Terdapat banyak solusi yang memungkinkan. Ini juga masuk kategori **SPL Konsisten**.
	  3. **Tidak Ada Penyelesaian**: Kondisi di mana sistem saling berlawanan atau sejajar. Disebut sebagai **SPL Tak Konsisten**
- ## 3. Representasi dan Penulisan SPL
	- Ada tiga cara umum untuk merepresentasikan atau menuliskan Sistem Persamaan Linier:
	- **a. Bentuk Persamaan**
		- Merupakan bentuk aljabar seperti pada umumnya. Contoh penulisan:
			- $x + y + 2z = 9$
			- $2x + 4y - 3z = 1$
			- $3x + 6y - 5z = 0$
	- **b. Bentuk Matriks** ($A \vec{x} = b$)
		- Memisahkan koefisien, variabel, dan hasil ke dalam matriks berbeda.
		- Matriks koefisien $A$ dikalikan dengan vektor variabel $x$, menghasilkan vektor konstanta $b$.
	- **c. Matriks Augmented (Matriks Diperluas)**
		- [cite_start]Menggabungkan matriks koefisien $A$ dan vektor konstanta $b$ ke dalam satu kesatuan matriks. Bentuk ini sangat memudahkan penyelesaian komputasi menggunakan metode eliminasi.
- ## 4. Operasi Baris Elementer (OBE) & Ekivalensi Matriks
	- **Operasi Baris Elementer (OBE)**: Dengan suatu aturan tertentu, elemen-elemen suatu baris dari suatu matriks dapat berubah. Aturan ini digunakan sebagai teknik untuk mencari solusi SPL.
	- **Ekivalensi Dua Matriks**: Dua matriks $A$ dan $B$ di sebut ekivalen (ditulis $A \sim B$) jika matriks $B$ diperoleh dari matriks $A$ dengan cara operasi elementer[cite: 5, 12, 50].
- ## 5. Sistem Persamaan Linier (SPL) Homogen [cite: 6, 13, 51]
	- **Definisi**: SPL disebut homogen jika seluruh persamaan menghasilkan nilai nol (ruas kanan bernilai $0$).
		- [cite_start]Bentuk matematis: $a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = 0$.
	- **Karakteristik Penyelesaian SPL Homogen**:
		- **Penyelesaian Trivial**: Jika penyelesaian untuk semua variabel adalah nol ($x_1 = 0, x_2 = 0, \dots, x_n = 0$), maka penyelesaian SPL homogen ini disebut penyelesaian trivial.
		- **Penyelesaian Nontrivial**: Jika tidak semua variabel bernilai nol ($x_i \neq 0$), maka penyelesaiannya disebut penyelesaian nontrivial.