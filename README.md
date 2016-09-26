# PKSJ-PojokKhilaf
Repositori Kelompok Untuk Mata Kuliah PKSJ - Teknik Informatika ITS 2016/2017
##Laporan Tugas 1 PKSJ : Uji Penetrasi
------------------------------------

1. Teori
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
 
2. Instalasi Kali Linux dan Ubuntu
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
3. Uji Penetrasi 1
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
