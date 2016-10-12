Laporan Tugas 2 PKSJ : SQL Injection Pada Wordpress
---------------------------------------------------

Anggota Kelompok
- Ilham Gurat Adillion          5113100077
- Muhamad Rizki Prawiraatmaja   5113100120
- Dimas Rahman Oetomo           5113100163

1. Pendahuluan

Tugas ini dibuat untuk menyelesaikan Tugas 2 pada matakuliah Perancangan Keamanan & Sistem Jaringan (PKSJ) Semester Ganjil 2016/2017, Teknik Informatika ITS, Surabaya
 
2. Teori
 * **LAMP** adalah istilah yang merupakan singkatan dari Linux, Apache, MySQL dan Perl/PHP/Phyton. Merupakan sebuah paket perangkat lunak bebas yang digunakan untuk menjalankan sebuah aplikasi secara lengkap. Komponen-komponen dari LAMP adalah: Linux (sistem operasi), Apache HTTP Server (web server), MariaDB atau MySQL (sistem basis data) dan PHP atau Perl atau Python (bahasa pemrograman yang dipakai). LAMP adalah prasyarat sebelum menginstall wordpress (sumber: https://id.wikipedia.org/wiki/LAMP)

 * **Wordpress** adalah sebuah aplikasi sumber terbuka (open source) yang sangat populer digunakan sebagai mesin blog (blog engine). WordPress dibangun dengan bahasa pemrograman PHP dan basis data (database) MySQL. PHP dan MySQL, keduanya merupakan perangkat lunak sumber terbuka (open source software).[4] Selain sebagai blog, WordPress juga mulai digunakan sebagai sebuah CMS (Content Management System) karena kemampuannya untuk dimodifikasi dan disesuaikan dengan kebutuhan penggunanya (sumber: https://id.wikipedia.org/wiki/WordPress)
 
 * **sqlmap** adalah tool testing uji penetrasi yang menjalankan proses deteksi dan eksploitasi SQL injection secara otomatis pada server database. sqlmap mempunyai kemampuan deteksi yang bagus, banyak fitur uji penetrasi, database fingerprinting, data fetching dari database, akses underlying file system dan mengeksekusi perintah untuk OS via out-of-band connections (sumber: sqlmap.org)
 
 * **wpscan** WPScan adalah blackbox WordPress vulnerability scanner yang dapat digunakan untuk men-scan instalasi remote wordpress untuk mendapatkan celah keamanan (sumber: http://tools.kali.org/web-applications/wpscan)
 
 * **the mole** adalah tool SQL injection otomatis berbasis python. The mole menggunakan union technique atau teknik query berbasis boolean. Fiturnya mendunkung  injeksi berbasis Mysql, SQL Server, Postgres dan Oracle, interface command line, auto-complete perintah, mendukung filter, exploit dari GET/POST/cooki, python 3, exploit sql injection binary, kesederhanaan penggunaan (sumber: http://kali4hackers.blogspot.co.id/2014/07/the-mole-for-kali-linux.html)
 
3. Keterangan plugin
 * **LeagueManager** adalah plugin yang digunakan untuk menampilkan informasi tentang liga olahraga pada blog pengguna. Fitur leaguemanager yang digunakan adalah 3.9.1
 
 * **Video Player** adalah plugin yang digunakan untuk menambahkan video pada website user. versi video player yang digunakan adalah 1.5.16

3. Instalasi Wordpress dan LAMP
 * update wpscan
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/38.png "virtual hdd")
 * lakukan scan vulnearbility pada website
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/32.png "virtual hdd")
 * didapatkan plugin yang vulnerable
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/33.png "virtual hdd")
 * lakukan scan username pada website
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/34.png "virtual hdd")
 * username didapatkan
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/35.png "virtual hdd")
 * lakukan scan password pada website
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/36.png "virtual hdd")
 * password didapatkan
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/37.png "virtual hdd")

4. Penetrasi dengan sqlmap

5. Penetrasi dengan wpscan

6. Penetrasi dengan the mole

7. Kesimpulan dan Saran
