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
