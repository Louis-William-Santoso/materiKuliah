## 1. [[Sistem Memori (Memory System)]]
	- **Konsep Inti:**
		- Sistem memori adalah tempat di mana komputer menyimpan program dan data.
		- **Sel Memori Dasar:** 1 sel memori menyimpan 1-bit data, yang direpresentasikan dalam biner `1` atau `0` (hidup atau mati).
		- **Sifat Memori:**
			- Setiap sel memiliki 2 status/kondisi (1 dan 0).
			- Sel memori dapat ditulis (*write/store*) dan datanya dapat dibaca (*read/fetch*).
	- **Memory Hierarchy (Hierarki Memori):** 
	  
	  [Image of computer memory hierarchy diagram]
		- Sistem memori diatur dalam sebuah hierarki berdasarkan kecepatan, kapasitas, dan harga.
		- *Urutan dari atas (Paling dekat dengan Prosesor) ke bawah:*
		  1. **Registers:** Berada di dalam CPU. Paling cepat, ukuran paling kecil (byte/word), paling mahal.
		  2. **Cache Memory:** SRAM cepat yang menjembatani kecepatan CPU dan RAM.
		  3. **Main/Internal Memory (RAM):** Memori utama (DRAM), kapasitas ukuran Gigabyte.
		  4. **Secondary/External Memory:** Magnetic Disk (HDD), SSD, Optical Drive. Menyimpan data secara permanen. Kapasitas sangat besar (Terabyte), lambat, murah per byte-nya.
		  5. **Tertiary Memory:** Magnetic tape, Cloud storage (arsip data masif).
		- *Hukum Hierarki:* Semakin turun ke bawah hierarki, **Kapasitas** membesar, **Kecepatan Akses** melambat, dan **Harga per-byte** makin murah.
	- ## 2. [[RAM (Random Access Memory)]]
	- **Konsep Inti:**
		- RAM adalah memori utama (*main memory*) dalam sistem komputer yang digunakan untuk menyimpan data dan instruksi sementara **saat komputer sedang digunakan/berjalan**.
		- Disebut **"Random Access" (Akses Acak)** karena CPU dapat mengakses lokasi memori (alamat memori) mana pun secara langsung dan instan, tanpa harus membaca data secara berurutan (*sequential*) dari awal seperti pada pita kaset (magnetic tape).
	- **Karakteristik Utama RAM:**
		- **Volatile:** Data akan hilang secara permanen jika komputer dimatikan atau kehilangan aliran listrik.
		- **High-speed:** Kecepatan akses jauh lebih cepat dibanding penyimpanan eksternal (HDD/SSD).
		- **Limited Capacity:** Kapasitas lebih kecil dibandingkan memori sekunder karena harganya yang lebih mahal.
	- **Fungsi RAM:**
		- **Menyimpan Data Sementara:** Aplikasi yang sedang dibuka (seperti tab browser) datanya diletakkan di RAM.
		- **Akselerasi Data:** Menghindari CPU mengambil data dari HDD/SSD yang sangat lambat setiap kali butuh data.
		- **Menjalankan OS:** Sebagian instruksi inti sistem operasi di-*load* ke RAM saat komputer *booting*.
		- **Buffer Rendering:** Menyediakan ruang tunggu (*buffer*) cepat untuk memproses grafis dan video.
	- ## 3. [[SRAM vs DRAM]]
	- **SRAM (Static RAM):**
		- **Cara Kerja:** Menyimpan nilai data (1 dan 0) menggunakan rangkaian sirkuit gerbang logika (*flip-flop*).
		- **Sifat:** Selama ada aliran listrik, data akan tetap bertahan. Tidak butuh di- *refresh*.
		- **Kecepatan & Harga:** Sangat cepat, namun desainnya butuh banyak transistor per bit, sehingga ukurannya besar, kepadatannya (*density*) rendah, dan harganya sangat mahal.
		- **Penggunaan:** Umumnya digunakan untuk **Cache Memory** (L1, L2, L3) di dalam atau dekat CPU.
	- **DRAM (Dynamic RAM):**
		- **Cara Kerja:** Menyimpan nilai data pada komponen *Kapasitor* berukuran mikroskopis. Muatan listrik di kapasitor ibarat ember bocor.
		- **Sifat:** Karena kapasitor perlahan kehilangan muatan listriknya, DRAM membutuhkan sirkuit kontrol untuk melakukan **Refresh** (membaca dan menulis ulang muatan) ribuan kali per detik agar data tidak hilang (1 menjadi 0). Itulah mengapa disebut "Dinamis".
		- **Kecepatan & Harga:** Lebih lambat dari SRAM, tetapi desainnya sangat sederhana (1 transistor + 1 kapasitor per bit). Kepadatannya sangat tinggi (kapasitas besar) dan harganya murah.
		- **Penggunaan:** Digunakan sebagai **Main Memory (RAM)** komputer.
	- ## 4. [[Varian dan Teknologi DRAM Modern]]
	- **DDR SDRAM (Double Data Rate Synchronous DRAM):**
		- *Synchronous* artinya operasi RAM disinkronkan dengan *clock* / bus sistem komputer.
		- *Double Data Rate* berarti RAM ini mampu mengirimkan data 2 kali dalam 1 siklus *clock* (pada saat gelombang naik/ *rising edge* dan turun/ *falling edge*).
		- **Evolusi (DDR, DDR2, DDR3, DDR4, DDR5):** Tiap generasi meningkatkan kecepatan transfer (bandwidth), menambah kapasitas per keping, dan menurunkan voltase (lebih hemat daya).
		- **[Info Tambahan / Hati-hati]: Backward Incompatibility.** Modul RAM antar generasi memiliki posisi *notch* (lekukan pin) fisik yang berbeda serta kebutuhan voltase listrik yang berbeda. RAM DDR4 **tidak akan bisa** dicolokkan ke motherboard DDR3 atau DDR5.
	- **LPDDR (Low Power DDR):**
		- Didesain khusus untuk efisiensi daya ekstra tinggi.
		- Sangat umum disolder (tertanam) pada perangkat *mobile* seperti *smartphone*, *tablet*, dan laptop tipis (seperti MacBook dengan arsitektur ARM). Voltase operasinya bisa serendah 1.05V (LPDDR5).
	- **GDDR (Graphics DDR):**
		- Varian RAM khusus untuk **GPU (VRAM pada kartu grafis)**.
		- Dioptimalkan untuk **Bandwidth sangat tinggi** dan pemrosesan paralel yang masif. Penting untuk melakukan *rendering* video game 3D, *modeling*, dan pemrosesan *Machine Learning* yang butuh aliran data visual sangat besar dalam seketika.
	- ## 5. [[Masalah & Penyelesaian (Studi Kasus)]]
	- ### Masalah 1: Mengapa tidak menggunakan SRAM saja untuk memori utama agar komputer super cepat?
		- **Masalah:** Jika SRAM jauh lebih cepat dari DRAM, mengapa kita menggunakan DRAM untuk RAM komputer (sebesar 16GB atau 32GB)?
		- **Penyelesaian:** **Biaya dan Ukuran Fisik.** SRAM membutuhkan 6 transistor per bit, sedangkan DRAM hanya butuh 1 transistor dan 1 kapasitor. Jika dipaksakan membuat RAM 16GB menggunakan arsitektur SRAM, fisik *motherboard* tidak akan muat, dan harganya bisa mencapai ratusan juta rupiah untuk memori saja. Memori hierarki menyeimbangkan hal ini: Sedikit SRAM (Cache) dipasang pada CPU, disokong oleh banyak DRAM (RAM Utama).
	- ### Masalah 2: Komputer menjadi sangat lambat (*Lag*) saat membuka puluhan Tab Chrome bersamaan.
		- **Masalah:** RAM yang berkapasitas 8GB sudah penuh sesak oleh tab browser dan aplikasi yang berjalan, menyebabkan kursor patah-patah dan aplikasi terhenti sesaat (*not responding*).
		- **Penyelesaian:** Komputer Anda sedang melakukan **Paging / Swapping**. Ketika memori Volatile (RAM) penuh, Sistem Operasi meminjam ruang di memori Eksternal (Hardisk/SSD) sebagai RAM bayangan (*Virtual Memory*). Karena hierarki Hardisk jauh di bawah RAM (aksesnya ratusan kali lebih lambat), performa komputer merosot drastis. Solusi terbaik adalah menutup aplikasi atau menambahkan keping kapasitas RAM (upgrade ke 16GB).