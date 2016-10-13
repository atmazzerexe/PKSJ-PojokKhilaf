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
 
 * **sqlsus** adalah tool sql injection open source berbasis perl. dari command line, bisa didapatkan informasi mengenai struktur database, inject sql query, download file, crawling website, upload dan control backdoor, cloning database dan lain-lain. (sumber: http://tools.kali.org/vulnerability-analysis/sqlsus)
 
3. Keterangan plugin
 * **LeagueManager** adalah plugin yang digunakan untuk menampilkan informasi tentang liga olahraga pada blog pengguna. Fitur leaguemanager yang digunakan adalah 3.9.1
 
 * **Video Player** adalah plugin yang digunakan untuk menambahkan video pada website user. versi video player yang digunakan adalah 1.5.16
 
 * **CP Reservation Calendar** adalah plugin yang digunakan untuk melakukan pemilhan tanggal dari kalendar untuk reservasi. versi CP reservation calendar yang digunakan adalah 1.1.6

3. Instalasi Wordpress dan LAMP
 * Install Apache (sudo apt-get install apache2)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/00.png "virtual hdd")
 * Atur server name (sudo nano /etc/apache2/apache2.conf) lalu restart apache
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/01.png "virtual hdd")
 * Enable ufw firewall (sudo ufw app list)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/02.png "virtual hdd")
 * Apache punya akses di port 80 dan 443 (sudo ufw app info "Apache Full")
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/03.png "virtual hdd")
 * Meng-allow incoming traffic (sudo ufw allow in "Apache Full")
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/04.png "virtual hdd")
 * Apache berhasil, Server dapat diakses via lynx (lynx http://192.168.56.101)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/05.png "virtual hdd")
 * Install MySQL (sudo apt-get install mysql-server) dan atur keamanan (sudo mysql_secure_installation)
     ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/06_2.png "virtual hdd")
 * Install PHP (sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql)
     ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/06.png "virtual hdd")
 * Atur agar Apache memprioritaskan untuk membuka file index.php (sudo nano /etc/apache2/mods-enabled/dir.conf)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/07.png "virtual hdd")
 * Cek status Apache (sudo systemctl status apache2) lalu restart apache (sudo systemctl restart apache2)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/11.png "virtual hdd")
 * lihat list PHP Modules yang bisa diinstall
     ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/09.png "virtual hdd")
 * Install PHPModules (sudo apt-get install)
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/10.png "virtual hdd")
 * dalam /var/www/html buat file info.php berisikan "<?php phpinfo();", lalu akses dengan lynx. jika keluar halaman info maka instalasi berhasil (lynx http://192.168.56.101/info.php)
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/12.png "virtual hdd")
 * download dan install wordpress, lalu buat database pada shell mysql (mysql -u root -p)
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/13.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/17.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/18.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/19.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/20.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/21.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/22.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/23.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/24.png "virtual hdd")
 * Install Plugin yang vulnerable
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/26.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/25.png "virtual hdd")
 
4. Penetrasi dengan sqlmap
 * karena sqlmap sudah terinstall didalam Kali Linux maka langsung menscan database mysql melalui Plugin LeagueManager
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/29.png "virtual hdd")
 * Dapat ditemukan ada celah untuk injeksi
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/30.png "virtual hdd")
 * Hasil serupa juga dapat ditemukan pada Plugin CP Reservation Calendar
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/39.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/41.png "virtual hdd")

5. Penetrasi dengan wpscan
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

6. Penetrasi dengan sqlsus
 * Karena sudah terinstall pada Kali Linux maka pengguna dapat melakukan generate file konfigurasi dari sqlsus
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/42.png "virtual hdd")
 * Ubah isi konfigurasi dari sqlsus dengan alamat serang yang dituju, jenis serangannya, serta metode penyerangannya
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/43.png "virtual hdd")
 * jalankan sqlsus dengan file konfigurasi yang sudah diubah sebelumnya
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/44.png "virtual hdd")
 * start sqlsus, jika berhasil, username akan terlihat
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/45.jpg "virtual hdd")


7. Kesimpulan dan Saran
 * plug in dan versi wordpress yang digunakan harus up to date untuk mengurangi celah untuk di exploit.
