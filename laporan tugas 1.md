
Laporan Tugas 1 PKSJ : Uji Penetrasi
------------------------------------

1. Teori
 * Ubuntu Server
    Ubuntu server adalah versi server dari Ubuntu. Perbedaan dari UBuntu server dan Ubuntu biasa adalah tidak adanya X window environment di instalasi default ubuntu server dan beberapa perbedaan pada proses instalasi. Ubuntu server menggunakan interface berbasis teks. Ubuntu server mempunyai software server penting yang sudah terinstall, contohnya: Tomcat (v8), PostgreSQL (v9.5), Docker v(1.10), Puppet (v3.8.5), Qemu (v2.5), Libvirt (v1.3.1), LXC (v2.0), and MySQL (v5.6). sumber:https://en.wikipedia.org/wiki/Ubuntu_(operating_system)#Ubuntu_Server
 
 * Kali Linux
    Kali linux adalah linux turunan debian yang didesain untuk forensik digital dan uji penetrasi. Kali linux sudah terinstall lebih dari 300 program uji penetrasi termasuk diantaranya Armitage, nmap, WIreshark, John the Ripper, Aircrack-ng, Burp suite dan OWASP ZAP. Kali linux mempunyai versi 32-bit dan 64-bit. sumber: https://en.wikipedia.org/wiki/Kali_Linux
 
 * SSH
    SSH (Secure Shell adalah cryptographic network protocol yang menjalankan layanan jaringan secara aman walau di dalam jaringan yang tidak aman. Contoh penggunaannya yang paling umum adalah untuk remote login oleh user ke komputer sistem. sumber: https://en.wikipedia.org/wiki/Secure_Shell
 
 * Hydra
    Hydra adalah login cracker paralel yang mendukung serangan ke berbagai protokol. Hydra bekerja dengan cepat dan fleksibel, dan mudah ditambahkan modul-modul baru. Perangkat ini mendukung Cisco AAA, Cisco auth, Cisco enable, CVS, FTP, HTTP(S)-FORM-GET, HTTP(S)-FORM-POST, HTTP(S)-GET, HTTP(S)-HEAD, HTTP-Proxy, ICQ, IMAP, IRC, LDAP, MS-SQL, MySQL, NNTP, Oracle Listener, Oracle SID, PC-Anywhere, PC-NFS, POP3, PostgreSQL, RDP, Rexec, Rlogin, Rsh, SIP, SMB(NT), SMTP, SMTP Enum, SNMP v1+v2+v3, SOCKS5, SSH (v1 and v2), SSHKEY, Subversion, Teamspeak (TS2), Telnet, VMware-Auth, VNC and XMPP. sumber: http://tools.kali.org/password-attacks/hydra
    
 * fail2ban
    fail2ban adalah intrusion prevention software yang melindungi komputer dari serangan brute force. fail2ban ditulis dalam bahasa python dan dapat berjalan pada sistem POSIX yang mempunyai interface untuk sistem kontrol paket atau firewall yang diinstal di lokal, contohnya iptables atau TCP Wrapper. sumber: https://en.wikipedia.org/wiki/Fail2ban
 
2. Instalasi Kali Linux dan Ubuntu
  1. Klik Baru
  2. Pilih Tipe : Linux dan Versi : Ubuntu, klik lanjut
  3. Pilih ukuran RAM, klik lanjut
  4. Pilih buat harddisk virtual, klik buat
  5. Pilih VDI, klik lanjut
  6. Pilih alokasi dinamis, klik lanjut
  7. Atur ukuran harddisk virtual
  8. Klik kanan pada virtualisasi yang dibuat, pilih pengaturan
  9. Pilih tab storage, klik controller, lalu centang Live CD/DVD dan klik gambar disket untuk memilih ISO File yang sesuai (Kali Linux/Ubuntu Server), klik OK
  10. Pilih virtualisasi yang dibuat, lalu klik start
  11. Menjalani instalasi di dalam virtual linux
  * Ubuntu Server SSH
      1. Pilih SSH Server lalu Enter
3. Uji Penetrasi 1
    * THC-Hydra
      1. Cek IP Address dari kedua komputer
      2. Jalankan hydra diterminal dengan perintah
            ketik hydra -ip address komputer yang akan diserang- -tipe- -s "port" -P "tempat menyimpan password" -l "user" -e "ns(n untuk null password, s login dengan password)" -t "berapakali percobaanaaa"
            contohnya seperti berikut:
            Reference-style: 
            ![alt text][inputHydra]

            [inputHydra]: https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-24_21-50-23.png "Input hydra"
            
            hasilnya jika berhasil dapat dilihat sebagai berikut
            Reference-style: 
            ![alt text][hasilHydra]

            [hasilHydra]: https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/2016-09-24_21-53-13.png "hasil hydra"
            
      3. Selesai
4. Uji Penetrasi 2
  * fail2ban
