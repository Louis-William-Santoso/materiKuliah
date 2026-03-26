## 1. [[Arsitektur Von Neumann]]
	- **Konsep Inti:**
		- Merupakan arsitektur komputer di mana **data dan instruksi program disimpan dalam satu blok memori fisik yang sama** dan menggunakan jalur (*bus*) yang sama pula.
		- Komputer membaca instruksi dan data dari tempat yang sama secara bergantian.
	- **Kelebihan:**
		- Perangkat keras dan desainnya jauh lebih sederhana (karena hanya butuh satu bus data dan satu bus alamat).
		- Sangat mudah untuk menyimpan data maupun instruksi karena sistem menganggapnya sama-sama sebagai memori eksternal ke internal.
	- **Kelemahan (Von Neumann Bottleneck):**
		- Terjadi antrean (bottleneck) memori karena bus digunakan secara bergantian. CPU tidak bisa membaca instruksi dan membaca/menulis data secara bersamaan.
		- **Risiko Overwrite:** Karena tidak ada pemisahan blok, data dan instruksi bisa saling menimpa (*overwrite*). Bahkan sistem bisa saja salah membaca instruksi sebagai data, atau sebaliknya, akibat kesalahan penempatan (*typo error* dalam manajemen memori).
	- ## 2. [[Arsitektur Harvard]]
	- **Konsep Inti:**
		- Merupakan arsitektur yang memiliki **dua blok memori dan dua jalur (bus) yang terpisah secara fisik**: satu khusus untuk *Instruksi* (program) dan satu lagi khusus untuk *Data*.
		-
	- **Kelebihan:**
		- **Kecepatan Eksekusi:** Tidak ada *memory bottleneck*. CPU dapat mengambil (fetch) instruksi dan mengakses data secara bersamaan dalam satu siklus *clock*.
	- **Kelemahan:**
		- Keterbatasan alokasi memori yang kaku. Karena memori dibagi secara fisik, sisa memori kosong di blok instruksi tidak bisa dipinjam untuk menyimpan data yang penuh, begitu pula sebaliknya.
		- Implementasi *hardware* (terutama jalur sirkuit pada CPU/Motherboard) lebih kompleks dan mahal karena membutuhkan pin dan bus ganda.
	- **[Info Tambahan] Penggunaan Modern:**
		- Komputer modern (PC/Laptop) seringkali menggunakan hibrida: Sistem memori utamanya (RAM) menggunakan desain *Von Neumann*, namun Cache L1 di dalam CPU dipisah menjadi L1 Instruction Cache dan L1 Data Cache (mengadopsi konsep *Harvard*) untuk kecepatan.
		- Arsitektur murni Harvard sering ditemukan pada *Microcontroller* (seperti Arduino/AVR) yang menjalankan program statis.
	- ## 3. [[Mekanisme Interrupt pada CPU]]
	- **Konsep Inti:**
		- **Interrupt:** Mekanisme sistem komputer yang mengizinkan modul I/O (seperti keyboard, mouse, disk) untuk "menginterupsi" pekerjaan normal dari prosesor.
		- **Tujuan:** Mengurangi waktu tunggu/menganggur (*wait/idle time*) prosesor saat berkomunikasi dengan I/O yang notabene memiliki kecepatan transfer jauh lebih lambat dari CPU.
	- **Siklus Interrupt:**
	  1. Saat peripheral I/O siap, modul mengirim sinyal **INTR** (*Interrupt Request*) ke CPU.
	  2. CPU merespons dengan sinyal **INTA** (*Interrupt Acknowledge*).
	  3. CPU menunda pekerjaan aslinya, menyimpan status (*state*) saat ini ke dalam memori/stack.
	  4. CPU mengeksekusi **ISR** (*Interrupt Service Routine* / *Interrupt Handler*) khusus untuk mengurus I/O tersebut.
	  5. Setelah selesai, CPU mengembalikan status awal dan melanjutkan program utamanya.
	- **Jenis Eksekusi Interrupt:**
		- **Sequential Interrupts:** Jika ada beberapa interrupt, CPU menolak interrupt baru hingga interrupt yang sedang ditangani selesai (diproses berurutan).
		- **Nested Interrupts:** Interrupt dengan prioritas lebih tinggi bisa memotong interrupt berprioritas rendah yang sedang berjalan.
	- ## 4. [[Masalah & Penyelesaian (Studi Kasus)]]
	- ### Masalah 1: Polling vs Interrupt
		- **Masalah:** Mengapa CPU kita lambat jika harus membaca input dari keyboard dengan metode *Programmed I/O* (Polling)?
		- **Penyelesaian:** Pada metode *polling*, CPU terus-menerus bertanya "Apakah ada tombol yang ditekan?" setiap milidetik. Ini membuang siklus berharga CPU (CPU *idle/wait*). Dengan **Interrupt**, CPU bebas menjalankan tugas berat (seperti merender video). Hanya ketika tombol benar-benar ditekan, *Keyboard Controller* mengirimkan aliran arus listrik (Interrupt Request) yang memaksa CPU menengok dan menangani *input* huruf tersebut.
	- ### Masalah 2: Efisiensi Arsitektur Von Neumann
		- **Masalah:** Karena Von Neumann lambat (satu jalur untuk data dan instruksi), bagaimana cara PC modern tetap bekerja sangat cepat?
		- **Penyelesaian:** PC modern menanamkan **Cache Memory** (SRAM yang beroperasi pada kecepatan prosesor) di dalam kepingan CPU. Instruksi dari RAM utama yang lambat ditarik secara massal (satu blok sekaligus) ke Cache. Di dalam CPU (L1 Cache), arsitekturnya dipecah menjadi *Harvard* (jalur terpisah untuk instruksi dan data), sehingga *core* CPU tidak pernah kekurangan pasokan data.