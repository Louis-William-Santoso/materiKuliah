- Konsep *Tree* adalah bentuk khusus dari graf yang sangat krusial dalam ilmu komputer. Struktur data hierarkis seperti sistem file pada OS (Windows Explorer / macOS Finder), pengurutan data, struktur HTML/XML (DOM), hingga algoritma kecerdasan buatan, semuanya dibangun di atas pondasi teori pohon.
- ## 1. [[Definisi dan Sifat Dasar Tree]]
	-
	- **Definisi:** *Tree* (Pohon) adalah sebuah graf tak berarah yang **terhubung (connected)** dan sama sekali **tidak mengandung sirkuit/siklus (acyclic)**.
	- **Sifat Mutlak:** - Jika sebuah tree memiliki $n$ buah simpul (*vertex/node*), maka tree tersebut WAJIB memiliki tepat $n - 1$ buah sisi (*edge*).
		- Hanya ada tepat satu lintasan (*path*) unik yang menghubungkan sembarang dua simpul di dalam tree. Jika Anda menambahkan satu sisi baru di antara dua simpul mana pun, sebuah sirkuit pasti akan terbentuk.
	- **Hutan (Forest):** Kumpulan pohon yang saling lepas (graf tidak terhubung yang tidak mengandung sirkuit). Jika hutan memiliki $n$ simpul dan $k$ komponen terhubung (pohon), maka jumlah sisinya adalah $n - k$.
- ## 2. [[Terminologi pada Rooted Tree (Pohon Berakar)]]
	- Pada *rooted tree*, salah satu simpul ditetapkan sebagai akar (*root*), dan semua sisi diarahkan menjauhi akar tersebut (membentuk hierarki dari atas ke bawah).
	- **Root (Akar):** Simpul paling atas yang tidak memiliki orang tua (*parent*). Level/kedalamannya adalah 0.
	- **Leaf (Daun / Simpul Terminal):** Simpul paling ujung bawah yang tidak memiliki anak (*child*). Berderajat keluar 0.
	- **Internal Node (Simpul Dalam):** Simpul yang memiliki minimal satu anak (bukan root dan bukan leaf).
	- **Parent & Child (Orang Tua & Anak):** Jika ada sisi terarah dari simpul $u$ ke simpul $v$, maka $u$ adalah *parent* dari $v$, dan $v$ adalah *child* dari $u$.
	- **Siblings (Saudara Kandung):** Simpul-simpul yang memiliki *parent* yang sama.
	- **Subtree (Upapohon):** Sebuah simpul beserta seluruh keturunannya (anak, cucu, dst.) yang membentuk pohon tersendiri.
	- **Level / Depth (Kedalaman):** Jarak (jumlah sisi) dari *root* menuju suatu simpul.
	- **Height / Panjang (Ketinggian):** Level maksimum (kedalaman terdalam) yang ada di dalam tree tersebut.
- ## 3. [[Jenis-Jenis Tree Khusus]]
	- **m-ary Tree:** Pohon berakar di mana setiap simpul internal memiliki *maksimal* $m$ buah anak. Jika setiap simpul internal memiliki *tepat* $m$ anak, disebut *full m-ary tree*.
	- **Binary Tree (Pohon Biner):** Kasus khusus dari *m-ary tree* di mana $m = 2$. Setiap simpul maksimal hanya boleh punya 2 anak (anak kiri dan anak kanan). Ini adalah struktur data paling populer di ilmu komputer.
	- **Binary Search Tree (BST):** Pohon biner yang elemennya terurut. Aturannya: Semua nilai simpul di cabang kiri *harus lebih kecil* dari *parent*-nya, dan semua nilai di cabang kanan *harus lebih besar* dari *parent*-nya. Sangat efisien untuk pencarian data.
- ## 4. [[Aplikasi 1: Prefix Code (Kode Awalan)]]
	- **Konteks:** Dalam komunikasi digital, data teks diubah menjadi barisan biner (0 dan 1). Jika panjang kode tiap karakter berbeda (variabel), komputer butuh cara untuk tahu di mana batas pembacaan karakter berakhir tanpa menggunakan spasi.
	- **Definisi:** *Prefix code* adalah himpunan barisan biner di mana **tidak ada satu pun kode yang menjadi awalan (prefix) dari kode lainnya**.
	- **Contoh dari Materi:**
		- Himpunan $A = \{000, 001, 01, 10, 11\}$ **Adalah Prefix Code**. Tidak ada anggota yang menjadi awalan anggota lain. Komputer bisa membacanya tanpa ambigu.
		- Himpunan $B = \{1, 00, 01, 000, 0001\}$ **BUKAN Prefix Code**. Alasannya, `00` adalah prefix/awalan dari `000` dan `0001`. Jika komputer membaca "0001", ia akan bingung apakah itu "00" lalu "01", atau "000" lalu "1".
- ## 5. [[Aplikasi 2: Huffman Coding (Kompresi Data teks)]]
	-
	- **Konteks:** Algoritma kompresi data yang sangat efisien (digunakan pada format `.zip` atau MP3). Ia menggunakan pohon biner untuk merepresentasikan karakter berdasarkan frekuensi kemunculannya.
	- **Prinsip Kerja:** Karakter yang *sering* muncul diberi kode biner yang *sangat pendek*, sedangkan karakter yang *jarang* muncul diberi kode biner yang *panjang*.
	- **Langkah Membuat Huffman Tree:**
	  1. Hitung frekuensi kemunculan setiap karakter dari teks.
	  2. Buat setiap karakter menjadi simpul daun (leaf).
	  3. Ambil dua simpul dengan frekuensi **terkecil**. Gabungkan keduanya dengan sebuah simpul *parent* baru. Nilai frekuensi *parent* ini adalah penjumlahan frekuensi kedua anaknya.
	  4. Ulangi langkah 3 secara iteratif (terus gabungkan dua simpul/subtree terkecil) sampai hanya tersisa satu simpul puncak, yaitu *Root*.
	  5. Berikan label `0` pada setiap cabang yang ke arah kiri, dan label `1` pada setiap cabang ke arah kanan.
	  6. **Mendapatkan Kode:** Untuk mencari biner suatu karakter, telusuri lintasan dari *Root* turun menuju *Leaf* karakter tersebut, lalu catat angka `0` dan `1` yang dilewati. Pohon ini secara otomatis akan memenuhi syarat *Prefix Code*.
- ## 6. [[Aplikasi 3: Minimum Spanning Tree (MST)]]
	- **Konteks:** Misalkan ada banyak kota yang terhubung oleh jalan dengan jarak/biaya berbeda (graf berbobot). Bagaimana cara mengaspal jalan raya/menarik kabel fiber optik agar **semua kota terhubung**, namun dengan **total biaya seminimal mungkin**? Jawabannya adalah *Spanning Tree* (pohon yang merentang menyentuh semua simpul graf tanpa membuat sirkuit tertutup).
	- **Algoritma Populer:**
		- **Algoritma Kruskal:** Urutkan semua sisi dari bobot terkecil ke terbesar. Masukkan sisi satu per satu ke dalam graf asalkan tidak membentuk sirkuit.
		- **Algoritma Prim:** Mulai dari satu simpul sembarang, lalu selalu tambahkan sisi dengan bobot terkecil yang terhubung dengan simpul yang sudah masuk jaringan, asalkan tidak membentuk sirkuit.