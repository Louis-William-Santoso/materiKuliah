# [[AI Fundamental]]
- **Tags:** #AiFund #kuliah #semester4
- ## 1. [[Introduction to AI]]
	- **Definisi Dasar AI**: Kecerdasan Buatan (AI) secara luas didefinisikan sebagai segala bentuk kecerdasan yang dicapai oleh entitas benda mati atau *non-living thing*.
	- **Perdebatan Pendekatan AI (Weak vs Strong)**:
		- **Weak AI**: Didukung oleh pandangan para peneliti dari *Massachusetts Institute of Technology* (MIT). Pendekatan ini menyatakan bahwa sebuah sistem dapat dikatakan cerdas terlepas dari bagaimana tugas tersebut diselesaikan. Artinya, AI tidak harus meniru cara berpikir kognitif manusia, asalkan program tersebut dapat beroperasi dan menyelesaikan tugasnya dengan benar.
		- **Strong AI**: Didukung oleh pandangan dari *Carnegie-Mellon University*. Pendekatan ini meyakini bahwa perilaku cerdas sebuah mesin harus didasarkan pada metodologi yang sama persis dengan cara kerja otak manusia. Pendekatan *Strong AI* inilah yang sering menjadi dasar imajinasi dalam film-film fiksi ilmiah di Hollywood.
		  *Definisi Kecerdasan Manusia**: Mengacu pada R. Sternberg (1994), kecerdasan didefinisikan sebagai kemampuan kognitif seorang individu untuk belajar dari pengalaman masa lalu, bernalar dengan baik, mengingat informasi penting, serta kemampuannya dalam mengatasi tuntutan hidup sehari-hari.
	- **Cara Penyelesaian Berbasis Heuristik Manusia**: Heuristik merupakan seperangkat panduan (*guidelines*) atau "jalan pintas" mental yang sering kali berhasil untuk memecahkan suatu masalah, di mana hasil yang menguntungkan sangat mungkin dicapai meskipun tidak ada jaminan 100% mutlak berhasil. Salah satu contoh perangkat lunak era 1950-1960an yang menggunakan metode heuristik ini adalah *General Problem Solver* (GPS) yang awalnya ditujukan sebagai mesin pemecah masalah universal.
	- **Representasi Pengetahuan (*Knowledge Representation*)**: Agar sistem AI bisa menghasilkan keputusan cerdas, mereka harus menyerap dan menyimpan pengetahuan dalam format tertentu. Representasi yang tepat akan mempercepat komputasi solusi secara komprehensif[cite: 223].
	- **Logika Proposisional**: Pengetahuan disimpan menggunakan kalimat deklaratif bernilai benar (*true*) atau salah (*false*). Contoh representasinya: `P` = "Anda belajar AI dengan baik", `Q` = "Anda lulus mata kuliah AI".
	- **Aturan Produksi (Sistem Pakar)**: Banyak pakar mengekspresikan pengetahuannya dengan sistem aturan logis berbasis kondisi struktur logis IF-THEN.
	- **Logika Fuzzy (*Fuzzy Logic*)**: Kehidupan sehari-hari penuh dengan kondisi yang buram atau ambigu (misalnya, ruangan yang "sedikit dingin"). Jika logika tradisional (Boolean) hanya menggunakan batas tegas yang hitam-putih (skala 0 atau 1), Logika Fuzzy merepresentasikan ambiguitas ini menggunakan interval nilai desimal antara 0 hingga 1[cite: 247, 838].
	  
	  ---
- ## 2. [[Uninformed Search (Pencarian Buta)]]
	- **Konsep Dasar**: Pencarian *uninformed* atau *blind search* adalah algoritma pencarian solusi yang berjalan murni tanpa menggunakan pengetahuan spesifik seputar domain masalah tersebut (*problem domain knowledge*). Karena ketidaktahuannya ini, algoritma akan dipaksa untuk mencoba seluruh (*all*) alternatif cabang yang ada hingga solusi akhirnya ditemukan.
	- **Dua Algoritma Utama**: BFS (*Breadth First Search*) dan DFS (*Depth First Search*). Perbedaan utama dari kedua metode ini hanyalah terletak pada kriteria pemilihan urutan alternatif rute mana yang dieksplorasi terlebih dahulu.
	  * **Detail Algoritma Depth First Search (DFS)**:
	  * DFS bekerja dengan prinsip menyelam sedalam mungkin ke dalam pohon pencarian secepat yang ia bisa, sebelum akhirnya berpindah ke cabang lain.
	  * **Manajemen Antrean**: DFS mengandalkan dua senarai utama:
	    * *Open list*: Berisi semua node di pohon yang saat ini masih ditahan untuk dieksplorasi/diekspansi lebih lanjut.
	    * *Closed list*: Berisi node-node yang sudah tuntas dieksplorasi seluruh cabangnya dan tidak akan dipertimbangkan lagi.
	  * **Langkah-langkah Penyelesaian (Traversing) DFS**:
	    1. [cite_start]Mulai traversal algoritma dari titik awal atau *node v*[cite: 34].
	    2. [cite_start]Kunjungi node tetangga *w* yang berdampingan langsung dengan *node v*[cite: 35].
	    3. [cite_start]Segera ulangi kembali proses algoritma DFS ini secara terus-menerus ke bawah, dimulai dari *node w* tersebut (terus menggali secara vertikal)[cite: 35].
	    4. [cite_start]Apabila algoritma mencapai sebuah status *node u* di mana semua node tetangganya telah habis dikunjungi (jalan buntu), maka pencarian akan dilacak mundur (*backtracked*) ke belakang menuju node terakhir yang sebelumnya pernah dikunjungi, asalkan node tersebut masih memiliki cabang lain yang belum tersentuh[cite: 36, 627].
	    5. [cite_start]Proses pencarian akan berhenti total (*ends*) ketika sudah tidak ada lagi node baru yang bisa diraih dari kumpulan node-node lama yang telah dikunjungi[cite: 628].
	  
	  ---
- ## Minggu 3: Informed Search (Heuristic Search)
  * [cite_start]**Konsep Dasar**: Menyadari bahwa pencarian buta (seperti DFS/BFS) umumnya sangat tidak efisien [cite: 844][cite_start], *informed search* menyuntikkan informasi tambahan (*domain knowledge*) ke dalam mekanisme pencariannya[cite: 844, 845]. [cite_start]Tujuan utamanya adalah membuat algoritma selalu mengeksplorasi node yang "kemungkinan besar" merupakan node paling dekat dengan status tujuan[cite: 845].
  * [cite_start]**Fungsi Heuristik / $h(n)$**: Fungsi yang dirancang untuk memperkirakan atau mengestimasi tingkat "kebaikan" (*goodness*) dari posisi sebuah node $n$ saat ini[cite: 846]. [cite_start]Secara spesifik, $h(n)$ dihitung sebagai estimasi biaya jalur yang paling murah, atau sisa jarak dari *node n* menuju ke titik akhir (*goal state*)[cite: 847].
  * [cite_start]**Detail dan Cara Penyelesaian 4 Metode Utama**[cite: 848]:
  * **1. Hill-Climbing Search**: 
    * [cite_start]*Cara Penyelesaian*: Algoritma ini akan melihat probabilitas satu langkah di depannya (*looks one step ahead*)[cite: 849]. [cite_start]Jika ia menemukan node penerus (*successor*) yang memiliki bobot lebih baik dari kondisinya sekarang, algoritma akan langsung melangkah pindah ke penerus terbaik tersebut[cite: 850].
    * *Kelemahan Kritis*: Algoritma ini dirancang untuk tidak bisa "mengingat" langkah sebelumnya. [cite_start]Karenanya, metode Hill-Climbing sama sekali tidak mengizinkan terjadinya pelacakan mundur (*backtracking*) jika suatu saat ia terjebak di jalan buntu[cite: 850].
    * *Contoh*: Dalam masalah *puzzle*, nilai fungsi $f(n) = h(n)$ direpresentasikan dari "jumlah balok yang salah tempat". [cite_start]Semakin kecil angkanya, berarti algoritma semakin dekat dengan bentuk tujuan[cite: 851].
  * **2. Greedy Best-First Search**:
    * [cite_start]*Cara Penyelesaian*: Pendekatan ini berupaya meminimalkan estimasi biaya rute dengan cara selalu mengekspansi node yang secara heuristik dirasa paling dekat dengan sasaran[cite: 853]. [cite_start]Evaluasi keputusannya murni hanya menggunakan fungsi sisa jarak $f(N) = h(N)$[cite: 854].
  * **3. Branch and Bound / Uniform Cost Search**:
    * *Cara Penyelesaian*: Algoritma ini menggunakan variabel $g(n)$ yaitu total *biaya atau jarak aktual* sesungguhnya yang sudah dilewati dari asal hingga titik saat ini. Sistem akan selalu mengekspansi node di dalam antrean (*open list*) yang memiliki $g(n)$ paling rendah. 
  * **4. A* Search Algorithm**:
    * *Cara Penyelesaian*: Merupakan pengembangan komprehensif, node dinilai menggunakan perhitungan fungsi $f(n) = g(n) + h(n)$. Algoritma mempertimbangkan baik biaya aktual nyata di masa lalu $g(n)$ dan menggabungkannya dengan estimasi heuristik $h(n)$ untuk masa depannya, lalu mengekspansi nilai total terendah lebih dahulu.
  
  ---
- # Mini Kuis Logseq (Format Flashcards)
  
  Anda dapat menyematkan tag `#card` di blok pertanyaan induk di Logseq agar sistemnya secara otomatis mengubah struktur ini menjadi *Flashcard*.
- ## Kuis Detail Minggu 1 #card
	- **Pertanyaan:** Apa perbedaan fundamental antara pendekatan *Weak AI* dan *Strong AI* dalam literatur studi kecerdasan buatan, dan institusi mana yang biasanya menyokong aliran tersebut?
	- **Jawaban & Pembahasan:**
		- **Weak AI** (didukung oleh MIT) menilai bahwa sistem sudah layak disebut cerdas selama ia berhasil memecahkan masalah atau menunjukkan perilaku cerdas secara tepat, tanpa perlu mempedulikan apakah sistem memproses tugas tersebut dengan cara kognitif biologis yang sama seperti pikiran manusia.
		- **Strong AI** (didukung oleh Carnegie-Mellon University) bersikeras bahwa perilaku cerdas sebuah sistem barulah sah diakui apabila mesin beroperasi dan berpikir menggunakan proses fundamental atau metodologi yang sama persis dengan yang dipakai otak manusia.
- ## Kuis Detail Minggu 2 #card
	- **Pertanyaan:** Dalam algoritma transversal *Depth First Search* (DFS), apa yang terjadi ketika algoritma tersebut tiba di suatu node `u`, di mana ternyata semua node tetangganya (*neighboring nodes*) sudah habis dieksplorasi seluruhnya?
	- **Jawaban & Pembahasan:**
	  Ketika mencapai titik jalan buntu seperti ini, algoritma DFS akan melakukan proses pelacakan mundur atau **backtracking**. Algoritma akan menelusuri mundur jejak langkahnya dan kembali ke node paling terakhir dikunjungi di masa lalu yang diketahui masih menyimpan cabang/node *w* yang belum dieksplorasi (*unvisited*). Sistem kemudian melanjutkan galian ke dalam dari titik tersebut.
- ## Kuis Detail Minggu 3 #card
	- **Pertanyaan:** Apa alasan spesifik mengapa algoritma heuristik *Hill-Climbing Search* sangat rawan gagal mencapai hasil yang optimal jika grafnya memiliki banyak jalur buntu?
	- **Jawaban & Pembahasan:**
	  Kelemahan paling fatal dari metode *Hill-Climbing Search* adalah algoritma ini didesain agar tidak menyimpan memori tentang jalur-jalur sebelumnya yang telah ia lewati ("tidak mengingat posisinya di masa lalu"). Konsekuensi dari hal tersebut adalah metode ini sama sekali tidak mengizinkan adanya fitur pelacakan mundur (*does not allow backtracking*) dan juga tidak bisa melompat mencoba jalur alternatif lain. Jika algoritma ini salah langkah dan masuk ke cabang yang buntu (*local maxima*), maka ia otomatis terjebak tanpa solusi.