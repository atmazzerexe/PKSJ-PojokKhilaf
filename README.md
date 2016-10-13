# PKSJ-PojokKhilaf
Repositori Kelompok Untuk Mata Kuliah PKSJ - Teknik Informatika ITS 2016/2017
##Laporan Tugas 1 PKSJ : Uji Penetrasi

1. Pendahuluan
Tugas ini dibuat untuk menyelesaikan Tugas 1 pada matakuliah Perancangan Keamanan & Sistem Jaringan (PKSJ) Semester Ganjil 2016/2017, Teknik Informatika ITS, Surabaya
 
Anggota Kelompok
- Ilham Gurat Adillion          5113100077
- Muhamad Rizki Prawiraatmaja   5113100120
- Dimas Rahman Oetomo           5113100163

2. Teori
 * Ubuntu Server
        adalah versi server dari Ubuntu. Perbedaan dari UBuntu server dan Ubuntu biasa adalah tidak adanya X window environment di instalasi default ubuntu server dan beberapa perbedaan pada proses instalasi. Ubuntu server menggunakan interface berbasis teks. Ubuntu server mempunyai software server penting yang sudah terinstall, contohnya: Tomcat (v8), PostgreSQL (v9.5), Docker v(1.10), Puppet (v3.8.5), Qemu (v2.5), Libvirt (v1.3.1), LXC (v2.0), and MySQL (v5.6). sumber:https://en.wikipedia.org/wiki/Ubuntu_(operating_system)#Ubuntu_Server
 
 * Kali Linux
        adalah linux turunan debian yang didesain untuk forensik digital dan uji penetrasi. Kali linux sudah terinstall lebih dari 300 program uji penetrasi termasuk diantaranya Armitage, nmap, WIreshark, John the Ripper, Aircrack-ng, Burp suite dan OWASP ZAP. Kali linux mempunyai versi 32-bit dan 64-bit. sumber: https://en.wikipedia.org/wiki/Kali_Linux
 
 * SSH
        Secure Shell adalah cryptographic network protocol yang menjalankan layanan jaringan secara aman walau di dalam jaringan yang tidak aman. Contoh penggunaannya yang paling umum adalah untuk remote login oleh user ke komputer sistem. sumber: https://en.wikipedia.org/wiki/Secure_Shell
 
 * Hydra
        adalah login cracker paralel yang mendukung serangan ke berbagai protokol. Hydra bekerja dengan cepat dan fleksibel, dan mudah ditambahkan modul-modul baru. Perangkat ini mendukung Cisco AAA, Cisco auth, Cisco enable, CVS, FTP, HTTP(S)-FORM-GET, HTTP(S)-FORM-POST, HTTP(S)-GET, HTTP(S)-HEAD, HTTP-Proxy, ICQ, IMAP, IRC, LDAP, MS-SQL, MySQL, NNTP, Oracle Listener, Oracle SID, PC-Anywhere, PC-NFS, POP3, PostgreSQL, RDP, Rexec, Rlogin, Rsh, SIP, SMB(NT), SMTP, SMTP Enum, SNMP v1+v2+v3, SOCKS5, SSH (v1 and v2), SSHKEY, Subversion, Teamspeak (TS2), Telnet, VMware-Auth, VNC and XMPP. sumber: http://tools.kali.org/password-attacks/hydra
    
 * fail2ban
        adalah intrusion prevention software yang melindungi komputer dari serangan brute force. fail2ban ditulis dalam bahasa python dan dapat berjalan pada sistem POSIX yang mempunyai interface untuk sistem kontrol paket atau firewall yang diinstal di lokal, contohnya iptables atau TCP Wrapper. sumber: https://en.wikipedia.org/wiki/Fail2ban
 
3. Instalasi Kali Linux dan Ubuntu
  1. Klik Baru
        
        ![tombolBaru](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/1.png "tombol baru")
  2. Pilih Tipe : Linux dan Versi : Ubuntu, klik lanjut
        
        ![pilihTipe](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2.png "pilih tipe")
  3. Pilih ukuran RAM, klik lanjut
        
        ![pilihRAM](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/3.png "pilih RAM")
  4. Pilih buat harddisk virtual, klik buat
        
        ![hddVirtual](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/4.png "hdd virtual")
  5. Pilih VDI, klik lanjut
        
        ![vdi](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/5.png "vdi")
  6. Pilih alokasi dinamis, klik lanjut
        
        ![alokasiDinamis](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/6.png "alokasi dinamis")
  7. Atur ukuran harddisk virtual
        
        ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/7.png "virtual hdd")
  8. Klik kanan pada virtualisasi yang dibuat, pilih pengaturan
        
        ![pengaturan](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/9.png "pengaturan")
  9. Pilih tab storage, klik controller, lalu centang Live CD/DVD dan klik gambar disket untuk memilih ISO File yang sesuai (Kali Linux/Ubuntu Server), klik OK
        
        ![storage](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/10.png "storage")
  10. Pilih virtualisasi yang dibuat, lalu klik start
        
        ![virtualisasi](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/11.png "virtualisasi")
  11. Jalankan virtualisasi
        
        ![jalankan](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/8.png "jalankan")

  * Ubuntu Server SSH
      1. Pilih SSH Server lalu Enter
      
      ![jalankan](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-24_22-34-41.png "jalankan")
4. Uji Penetrasi 1
    * THC-Hydra
      1. Cek IP Address dari komputer yang akan diserang
            ![mencariIp](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/ipaddress.PNG "Ip Address")
      2. Jalankan hydra diterminal dengan perintah
            ketik hydra -ip address komputer yang akan diserang- -tipe- -s "port" -P "tempat menyimpan password" -l "user" -e "ns(n untuk null password, s login dengan password)" -t "berapa kali percobaan yang dilakukan"
            contohnya seperti berikut:
            ![inputHydra](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-24_21-50-23.png "Input Hydra")
            
            hasilnya jika berhasil dapat dilihat sebagai berikut:
            ![hasilHydra](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-24_21-53-13.png "Hasil Hydra")
            
      3. Selesai
4. Uji Penetrasi 2
  * fail2ban
        1. Install fail2ban pada Ubuntu Server dengan perintah:
        sudo apt-get install fail2ban
        2. Copy isi dari jail.conf ke jail.local yang akan digunakan sebagai konfigurasi fail2ban nantinya
        ![kopiKonten](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-16-03.png "Copy isi jail.conf")
        3. Install iptables pada Ubuntu Server dengan perintah:
        sudo apt-get install iptables-persistent
        4. Stop service fail2ban untuk sementara dengan perintah:
        sudo service fail2ban stop
        5. Tambahkan rule firewall pada iptables. disini sebelumnya port SSH telah diubah sebelumnya menjadi 30000:
        ![ruleFirewall](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-05-52.png "Add rule firewall")
        cek kembali apakah rule telah masuk di iptables:
        ![cekIPTABLES](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-06-29.png "Cek hasil iptables")    
        6. Simpan perubahan rule dengan perintah:
        sudo dpkg-reconfigure iptables-persistent
        7. Mulai kembali fail2ban dengan perintah:
        sudo service fail2ban start
        8. Mulai perubahan konfigurasi jail.local:
        Gambar 1:
        ![jailLocal1](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-26_20-03-41.png "jail.local 1")
        Gambar 2:    
        ![jailLocal2](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-31-07.png "jail.local 2")
        Gambar 3:
        ![jailLocal3](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-23-08.png "jail.local 3")
        Gambar 4:    
        ![jailLocal4](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_16-21-03.png "jail.local 4")   
        9. Hasilnya di Kali Linux:
        Gambar 1 (Waktu yang diperlukan menjadi lebih lama):
        ![kaliLinux1](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_17-37-43.png "Hasil di Kali Linux 1")        
        Gambar 2 (Jika gagal 3 kali, IP address akan diblokir):    
        ![kaliLinux2](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_18-48-26.png "Hasil di Kali Linux 2")
        ![kaliLinux3](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-25_18-49-07.png "Hasil di Kali Linux 3")

5. Kesimpulan dan Saran
Password dan username yang umum dan mudah ditebak lebih mudah dibobol oleh tool penetrasi, sehingga berbahaya untuk keamanan data user. Fail2ban membantu mengurangi resiko kebobolan dengan melakukan proteksi dasar seperti melakukan IP block.

---------------------------------------------------

##Laporan Tugas 2 PKSJ : SQL Injection Pada Wordpress

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
 * buat database pada shell mysql (mysql -u root -p)
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/13.png "virtual hdd")
 * download dan install wordpress, lalu atur kepemilikan folder wordpress
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/17.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/18.png "virtual hdd")
 * Tambahkan string autentikasi yang disediakan langsung oleh wordpress
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/19.png "virtual hdd")  
 * Ubah konfigurasi database wordpress dengan setting yang sudah dibuat sebelumnya
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/20.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/21.png "virtual hdd")
 * Lakukan instalasi dengan menggunakan browser GUI biasa
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/22.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/23.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T2/24.png "virtual hdd")
 * Pasang Plugin yang vulnerable
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
