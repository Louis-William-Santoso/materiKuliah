## 1. [[Mengapa Harus Ada Modul I/O?]]
	- Adanya batasan kecepatan transfer data dari dan ke *peripheral* I/O yang disebabkan oleh keterbatasan *hardware* dari *peripheral* I/O tersebut
	- Penggunaan metode operasi dari berbagai macam *peripheral* I/O yang berlainan (contoh: *human readable*, *machine readable*, *communication purposes*, maupun kebutuhan *real-time process*)
	- Penggunaan format dan panjang data yang berbeda-beda antara *peripheral* I/O yang satu dengan yang lainnya (contoh: *serial data transfer*, *parallel data transfer*, *single byte*, *packet data*)
- ## 2. [[Fungsi Utama Modul I/O]]
	- Sebagai *interface* dari *peripheral* I/O ke prosesor dan memori melalui *system bus*
	- Sebagai *interface* ke satu atau lebih *peripheral* I/O melalui *data link* yang khusus
- **Kebutuhan (Requirements) Modul I/O**
	- **Control & Timing**: Mengontrol proses transfer data dari dan ke prosesor/memori sesuai dengan *timing* transfer data dari *peripheral* I/O
	- **Processor Communication**: Melakukan proses pendekodean instruksi yang spesifik untuk I/O, melakukan proses transfer data dari dan ke prosesor/memori, mengecek status I/O (*ready*, *not ready*, *error*), serta melakukan pengalamatan I/O
	- **Device Communication**: Berhubungan dengan instruksi, data, dan status dari *peripheral* I/O
	- **Data Buffering**: Mengatasi masalah perbedaan kecepatan transfer data antara prosesor/memori dengan *peripheral* I/O
	- **Error Detection**: Mendeteksi *error* yang terjadi saat proses transfer data, serta mendeteksi dan mengirimkan informasi *error* yang lebih detail untuk dilaporkan ke sistem komputer
- **I/O Interface: Parallel vs. Serial**
	- **Parallel Interface**: Menggunakan banyak jalur kabel (*multiple wires*) untuk proses transmisi data
	- **Serial Interface**: Menggunakan kabel tunggal (*single wire*) untuk transmisi data, di mana pengiriman dilakukan 1 bit pada satu waktu
		- **Asynchronous**: Tidak menggunakan *clock* sebagai referensi, melainkan menggunakan kecepatan data yang sudah disepakati sebelumnya (*pre-decided baudrate*). Contoh implementasi: RS-232, RS-422, RS-485, 1-wire, Firewire, USB, dll
		- **Synchronous**: Disinkronisasi menggunakan *clock* yang sama, biasanya dibangkitkan oleh *transmitter* dan dikirimkan ke *receiver*. Contoh implementasi: I2C, SPI, microwire, CAN, dll
- **Teknik Organisasi I/O**
	- **Programmed I/O**:
		- Kontrol CPU (*CPU-Controlled*): Sepenuhnya (*Fully*)
		- Transfer data via CPU: Ya.
		- Penggunaan *Interrupt*: Tidak<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Format data: *Word / Byte*<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
	- **Interrupt-driven I/O**<!---->:
	  
	  <!----><!----><!----><!----><!----><!---->
	  
	  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Kontrol CPU (*CPU-Controlled*): Sepenuhnya (*Fully*)<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Transfer data via CPU: Ya<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Penggunaan *Interrupt*: Ya<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Format data: *Word / Byte*<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
	- **Direct Memory Access (DMA)**<!---->:
	  
	  <!----><!----><!----><!----><!----><!---->
	  
	  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Kontrol CPU (*CPU-Controlled*): Separuh (*Half*)<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Transfer data via CPU: Tidak<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Penggunaan *Interrupt*: Ya<!---->.
		  
		  <!----><!----><!----><!----><!----><!---->
		  
		  <!----><!----><!----><!----><!----><!----><!----><!----><!---->
		- Format data: Blok (*Block*)<!---->.