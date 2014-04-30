Kenapa pemrograman fungsional? Kenapa Haskell?
==============================================

Daftar Isi
----------

* Sudahkan kita membuat kesepakatan!
  * Hal baru
  * Power
  * Kenikmatan
* Apa yang diharapkan dari buku ini
  * Sedikit tentang anda
* Apa yang diharapkan dari Haskell
  * Dibandingkan dengan bahasa statis tradisional
  * Dibandingkan dengan bahasa dinamis modern
  * Kompilasi, debugging, dan analisa performa
  * Pustaka bundled dan pustaka pihak ketiga
* Sedikit sketsa tentang sejarah Haskell
  * Prasejarah
  * Jaman dahulu kala
  * Era modern
* Resources bermanfaat
  * Materi referensi
  * Aplikasi dan pustaka
  * Komunitas Haskell
* Ucapan terima kasih
  * Bryan
  * John
  * Don
  * Terima kasih untuk reviewer

Sudahkah kita membuat kesepakatan!
----------------------------------

Haskell adalah bahasa yang dalam, dan kami pikir mempelajarinya adalah pengalaman yang sangat bermanfaat.
Kami akan fokus pada tiga elemen sementara kami menjelaskan mengapa demikian.
Yang pertama adalah *hal baru*: kami mengajak anda untuk berpikir tentang pemrograman dari perspektif yang berbeda.
Kedua *power*: kami akan menunjukan pada anda bagaimana membuat perangkat lunak yang singkat, cepat, dan aman.
Terakhir, kami menawarkan pada anda banyak *kesenangan*: kenikmatan mengaplikasikan keindahan teknik pemrograman untuk menyelesaikan masalah nyata.

### Hal baru

Haskel kemungkinan besar berbeda dengan bahasa yang kalian pernah gunakan sebelumnya.
Dibandingkan dengan kumpulan konsep-konsep kotak perlengkapan dalam mental programer, perograman fungsional menawarkan kita cara berfikir sangat berbeda tentang software.

Dalam Haskell, kita meletakkan penekanan yang kurang pada kode yang memodifikasi data.
Sebaliknya, kita fokus pada fungsi yang mengambil nilai immutable sebagai input dan menghasilkan nilai baru sebagai output.
Dengan diberikan input yang sama, fungsi ini akan selalu mengembalikan hasil yang sama.
Inilah ide dibalik pemrograman fungsional.

Seiring dengan tidak memodifikasi data, fungsi Haskell kita biasanya tidak berbicara dengan dunia luar; kita menyebut fungsi ini *murni*.
Kita membuat pembeda yang tegas antara kode yang murni dan bagian program yang membaca atau menulis berkas, berkomunikasi melalu koneksi jaringan, atau membuat tangan robot bergerak.
Hal ini membuat pengorganisasian, menyusun alasan, dan pengujian program kita.

Kita meninggalkan beberapa ide yang mungkin tampak dasar, seperti memiliki perulangan `for` yang built-in dalam bahasa ini.
Kita punya cara lain yang lebih fleksibel untuk melakukan tugas yang repetitif.

Bahkan cara dimana kita mengevaluasi ekspresi berbeda dalam Haskell.
Kita menunda setiap komputasi sampai hasilnya benar-benar dibutuhkan.
Haskell adalah bahasa yang *malas*.
Kemalasan bukan hanya soal memindahkan-mindahkan pekerjaan: ini sangat mempengaruhi bagaimana kita menulis program.

### Power

Sepanjang buku ini, kami akan menunjukkan cara alternatif Haskell terhadap fitur dari bahasa pemrograman tradisional yang powerful, fleksibel, dan menuntun pada kode yang dapat diandalkan.
Haskell secara positif dijejali dengan ide-ide mutakhir tentang bagaimana membuat perangkat lunak yang luar biasa.

Karena kode murni tida memiliki hubungan dengan dunia luar, dan data dimana ia bekerja tidah pernah diubah, jenis kejutan jahat yang pada penggalan kode secara tak nampak merusak data yang digunakan orang lain sangatlah jarang.
Apapun konteks yang fungsi murni gunakan, ini akan berperilaku secara konsisten.

Kode murni lebih mudah untuk diuji daripada kode yang berhubungan dengan dunia luar.
Ketika suatu fungsi hanya merespon pada inputnya yang nampak, kita dapat dengan mudah menyebutkan sifat yang mestinya selalu benar.
Kita dapat secara otomatis menguji apakah sifat tersebut terpenuhi untuk sejumlah besar input acak, dan ketika lulus uji tes tersebut, kita move on.
Kita masih menggunakan teknik tradisional untuk mengji kode yang berinteraksi dengan berkas, jaringan, atau perangkat keras eksotis.
Karena ada jauh lebih sedikit kode yang tak murni ini dibandingkan yang kita temui di bahasa tradisional, kita memperoleh lebih banyak jaminan bahwa perangkat lunak kita cukup solid.

Evaluasi malas memiliki beberapa efek menakutkan.
Katakanlah kita ingin menemukan k-elemen terkecil dari suatu list yang tak terurut.
Di bahasa pemrograman tradisional, pendekatan yang paling jelas adalah mengurutkan list tersebut dan mengambil k elemen pertama, tetapi hal ini sangatlah mahal.
Untuk efisiensi, kita alih-alih menulis fungsi spesial yang mengambil nilai ini dalam satu kali kerja, dan fungsi tersebut harus melakukan pembukuan yang lumayan kompleks.
Di Haskell, pendekatan-urutkan-lalu-ambil sebenarnya bekinerja dengan cukup baik: kemalasan menjaimn bahwa list tersebut akan diurutkan secara cukup untuk menemukan k-unsur minimal.

Lebih baik lagi, kode Haskell yang beroperasi secara efisien tersebut sangat kecil, dan hanya menggunakan pustaka standar.

```haskell
-- berkas: ch00/KMinima.hs
-- baris yang dimulai dengna "--" adalah komentar.

minima k xs = take k (sort xs)
```
Hal ini memakan waktu yang cukup lama guna mengembangkan nuansa intuitif bahwa evaluasi malas amatlah penting, kode yang dihasilkan lebih bersih, singkat, dan efisien.

Layaknya contoh diatas, aspek penting pada kekuatan Haskell berada pada kekompakan dari kode yang kita tulis.
Dibandingkan dengan bekerja dalam bahasa tradisional populer, ketika kita mengembangkan program di Haskell kita sering kali menulis lebih sedikit kode, yang secara substansial leibh sedikit waktu, dan lebih sedikit bug.

### Kenikmatan


Kami percaya bahwa  memulai dasar pemrograman Haskell adalah hal mudah, dan kalian akan dapat dengan sukses menulis program kecil kalian dalam hitungan jam atau hari.

Karena pemrograman yang afektif di Haskell sangatlah berbeda dari bahasa yang lain, kalian bisa menduga bahwa menguasai keduanya, bahasa dan teknik pemrograman fungsional, membutuhkan banyak pemikiran dan praktik.

Menilik kembali ke hari-hari memulai Haskell, kabar baiknya adalah kesenangan dimulai dari awal: Mendalami bahasa baru lumayan menghibur dan menantang, dimana banyak ide umum yang berbeda atau menghilang, dan untuk mencari tahu bagaimana menulis program sederhana.

Bagi kami, kesenangan awal berlangsung selama pengalman tadi tumbuh dan pemahaman kita diperdalam.
Di bahasa lainnya, sangatlah sulit melihat hubungan antara ilmu pengetahuan dan kacang-dan-baut-nya pemrograman. Di Haskell, kita mengimpor beberapa ide dari matematika abstrak dan membuatnya bekerja.
Lebih baik lagi, kita menemukan bahwa ide tersebut tidak hanya mudah untuk dipelajari, mereka juga memiliki hasil yang praktis untuk membantu kita menulis kode yang kompak, dan mudah digunakan kembali.

Selain itu, kita tidak akan menempatkan "dinding bata" manapun di jalan kalian: tidak ada teknik yang sulit atau mengerikan dalam buku ini yang harus kalian kuasai agar bisa membuat program secara efektif.

Seperti yang sudah dikatakan, Haskell merupakan bahasa yang ketat: ia akan membuat kalian lebih berpikir di depan. Hal ini mungkin akan memakan cukup waktu untuk menyesuaikan debugging banyak kode kalian sebelum menjalankannya, dari respon compiler yang memberitahu kalain bahwa sesuatu di program kalian tak masuk akal. Bahkan dengan pengalaman bertahun-tahun, kami sangat terkagum-kagum dan lega dengan seringnya program Haskell kami yang langsung bekerja pada percobaan pertama, setelah kami perbaiki kompilasi eror tadi.

## Apa yang diharapkan dari buku ini

Kami memulai project ini karena semakin tumbuhnnya jumlah orang yang menggunakan Haskell untuk menyelesaikan masalah sehari-hari.
Karena Haskell memiliki akar di akademia, beberapa buku Haskell yang ada fokus pada problem dan teknik dari pemrograman sehari-hari yang kami tertarik padanya.

Dengan buku ini, kami ingin menunjukkan pada kalian bagaimana pemrograman fungsional dan Haskell menyelesaikan masalah nyata.
Ini adalah buku praktik: setiap bab memiliki lusinan contoh kode, dan banyak yang memiliki aplikasi lengkap.
Berikut adalah comboh dari pustaka, teknik, dan peralatan yang akan kita tunjukkan pada anda bagaimana mengembangkannya.

- Membuat aplikasi yang mengunduh episode podcast dari internet dan menyimpannya history-nya di basis data SQL.
- Mengji kode kalian dengan cara yang intuitif dan powerful. Menjelaskan sifat yang seharusnya benar, dan membiarkan pustaka QuickCheck menciptakan kasus ujinya secara otomatis.
- Mengambil sejumlah foto kamera dari barcode, dan mengubahnya menjadi identifier yang dapat kalain gunakan untuk mengquery di perpustakaan atau web site penjual buku.
- Menulis kode yang mengambil data dari web. Mentraksasikan data dengan server dan klien yang ditulis dalam bahasa lain menggunakan notasi JSON. Mengembangkan pengecek tautan konkuren.

### Sedikit tentang anda

Apa yang harus kalian tahu sebelum membaca buku ini?
Kami menduga kalian sudah tahu bagaimana caranya untuk membuat program, tetapi jika kalian belum pernah menggunakan pemrograman fungsional, tak apa.

Tak peduli apa level pengalaman kalian, kami mencoba untuk mengantisipasi kebutuhan kalian: kami bertindak ekstra untuk menjelaskan ide yang baru dan memiliki potensi menjadi rumit dengan mendalam, biasanya dengan contoh dan gambar untuk lebih memperjelas poinnya.

Sebagai programer Haskell yang baru, kalian pasti akan memulai menulis cukup banyak kode dengan secara manual yang kalian bisa saja gunakan fungsi dalam suatu pustaka atau teknik pemrograman, jikalau kalian tahu keberadaannya.
Kami mengemas buku ini dengan informasi untuk membantu kalian menemukannya secepat mungkin.

Tentu saja, selalu saja akan ada tanjakan sepanjang jalan.
Jika kita mulai mengantisipasi kejutan yang sesekali muncul atau kesulitan didalam hal-hal yang menyenangkan, kalian akan memiliki pengalaman terbaik.
Celah yang kasar yang kalian temui tak akan berlangsung lama.

Seiring dengan bertambahnya pengalaman kalian sebagai programer Haskell, cara kalian menulis kode akan berubah.
Bahkan, selama kalian membaca buku ini, cara kami mempresentasikan kode akan berubah pula, seiring dengan kita mulai beranjak dari dasarnya bahasa ke teknik yang lebih powerful dan produktif.

## Apa yang diharapkan dari Haskell

Haskell adalah bahasa pemrograman *general purpose*.
Ia didesain tanpa aplikasi sempt di pikiran.
Meskipun ini membutuhkan pijakan yang kuat tentang bagaimana suatu program harus ditulis, ia tidak berpihak pada satu domain masalah ketimbang yang lain.

Sementara pada intinya, bahasa ini mendorong style murni, malas dari pemrogrman fungsional, ini adalah *default*nya, bukan hanya pilihan.
Haskell juga mendukung model yang lebih tradisional dari kode prosedural dan evaluasi *strict*. Sebagai tambahan, meskipun fokus dari bahasa ini sendiri adalah secara bulat menulis program *statycally typed*, tetap dimungkinkan untuk menulis kode Haskell dalam cara *dynamically typed*.

### Dibandingkan dengan bahasa pemrograman statik tradisional

Bahasa yang menggunakan static type system sedernaha telah menjadi andalan dari dunia pemrograman selama berdekade-dekade.
Haskell adalah bahasa yang statically typed, tapi definisi dari apa itu type, dan apa yang bisa kita lakukannya padanya, lebih fleksibel dan powerful daripada bahasa tradisional. Tipe membuat kontribusi besar pada kesingkatan, kejelasan, dan efisiensi program Haskell.

Meskipun powerful, tipe sistem Haskell seringkali tak menggangu anda. Jika kita menghilangkan type information eksplisit, Haskell compiler akan secara otomatis menyimpulkan tipe dari suatu ekspresi atau fungsi tersebut.
Dibandingkan dengan bahasa statis tradisional, yang kita harus menyuapi sejumlah besar type information, kombinasi dari power dan penyimpulan dalam tipe sistem Haskell secara signifikan mengurangi kekacauan dan redudansi kode kita.

Beberapa fitur lain dari Haskell yang digabungkan lebih jauh meningkatkan banyaknya pekerjaan yang muan dalam satu layar teks.
Ini memberikan perbaikan dalam waktu pengembangan dan agilitas: kita dapat menciptakan kode yang handal secara cepat, dan dengan mudah me-refactor kode tersebut dalam merespon perubahan persyaratan.

Kadang kala, program Haskell berjalan lebih lambat dari program yang sama yang ditulis di C atau C++.
Untuk kebanyakan kode yang kita tulis, keunggulan Haskell pada produktivitas dan relibitas mengalahkan segala kekurangan dari performa yang kecil.

Prosesor multicore sekarang dimana-mana, tetapi tetap saja sulit untuk membuat program untuk mereka dengan menggunakan teknik tradisional.
Haskell memberikan teknologi yang unik untuk membuat pemrograman multicore lebih terjangkau.
Haskell mensupport pemrograman paralel, sowftare transactional memory untuk konkurensi yang stabil, dan dan mampu berkembang ke ratusan ribu konkuren thread.

### Dibandingkan dengan pemrograman dinamis modern

Selama dekade terakhir, dynamically typed, intrerpreted languages semakin populer.
Mereka biasanya menawarkan keuntungan substansial dalam produktivitas developer.
Meskipun ini biasanya diiringi dengan performa program yang buruk, untuk banyak pekerjaan pemrograman produktivitas mengalahkan performa, atau performa tidaklah menjadi faktor yang signifikan pada kasus apapun.

Kesingkatan adalah satu area dimana Haskell dan dynamically typed languages menampilkan secara sama: di tiap kasus, kita menulis lebih sedikit kode untuk menyelesaikan suatu masalah dibanding dengan bahasa tradisional.
Program yang seringkali berada pada ukuran yang sama di dtl dan Haskell.

Ketika menghiraukan performa runtime, Haskell hampir selalu memiliki keuntungan besar.
Kode yang di compile dengan Glasgow Haskell Compiler (GHC) biasanya antara 20 sampai 60 kali lebih cepat daripada kode yang dijalankan melalui intrepreter bahasa dinamis. GHC juga menyediakan interpreter, jadi kalian dapat menjalankan script tanpa mengcompile mereka.

Perbedaan besar antara bahasa bertipe dinamis dan Haskell terletah pada filosofi mereka antara tipe.
Alasan besar dari popularitas bahasa bertime dinamis adalah jarang sekali kita memerlukan untuk secara eksplisit menyebutkan tipe. Melalui penyimpulan tipe otomatis, Haskell menawarkan keunggulan yang sama.

Diluar kesamaan permukaan ini, perbedaannya lari dengan dalam. Di bahasa pemrograman bertipe dinamis, kita dapat menciptakan konstruk yang sulit untuk diekspresikan dalam bahasa statis.
Namun, hal yang sama juga terjadi sebaliknya: dengan sistem tipe yang sepowerful Haskell, kita dapat menstruktur program dalam suatu cara yang mungkin tidak termanage atau tidak mudah di bahasa bertipe dinamis.

Penting kiranya untuk mengenali bahwa tiap pendekatan tersebut memerlukan konsekuensinya masing-masing. Secara singkat, perspektif yang dimiliki Haskell menekankan pada keamanan, sedangkan bahasa bertipe dinamis mencari fleksibilitas.
Jika seseorang telah menemukan suatu cara untuk memikirkan tipe yang merupakan paling baik, kami membayangkan bahwa tiap orang mungkin akan tahu tentangnya sekarang.

Tentu saja, kami memiliki opini kami sendiri tentang tradeoff-nya lebih menguntungkan.
Dua dari kami memiliki pengalaman pemrograman bertahun-tahun di bahasa bertipe dinamis.
Kami cinta untuk bekerja dengan mereka; kami masih menggunakan mereka tiap hari; tapi kami biasanya lebih memilih Haskell.

### Haskell di industri dan open source

Berikut adalah beberapa contoh dari sistem software besar yang telah diciptakan di Haskell.
Beberapa dari berikut open source, sedangkan yang lain adalah produk proprietary.

- Software desain ASIC dan FPGA (Lava, produk dari Bluespec Inc.)
- Software komposisi Musik (Haskore)
- Kompiler dan tools compiler-related (terutama GHC)
- Distributed revision control (Darcs)
- Web middleware (HAppS, produk dari Galois Inc.)

Berikut adalah contoh beberapa perusahaan yang menggunakan Haskell di akhir 2008, diambil dari Haskell wiki.

- ABN AMRO adalah bank internasional. Mereka menggunakan Haskell di perbankan investasi, untuk mengukur dari resiko counterparty pada portofolio penurunan finansial.
- Anygma adalah perusahaan startup. Mereka mengembangkan multimedia content creation tools menggunakan Haskell.
- Amgen adalah perusahaan biotech. Mereka menciptakan model matematika dan aplikasi kompleks lain di Haskell.
- Bluespec adalah ASIC dan FPGA desain software vendor. Produk mereka dikembangkan di Haskell, dan bahasa desain chip yang disediakan oleh produk mereka terpengaruh dari Haskell.
- Eaton menggunakan Haskell untuk desain dan verifikasi sistem kendaraan Hidrolis hibrid.

### Komilasi, debugging, dan analisa performa

Untuk pekerjaan praktis,
