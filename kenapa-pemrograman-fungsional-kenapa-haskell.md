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

Layaknya contoh diatas, aspek penting pada kekuatan Haskell
