Laporan Tugas 5 PKSJ : Penetration Testing Menggunakan Metasploit dan Metasploitable
------------------------------------------------------------

Anggota Kelompok
- Ilham Gurat Adillion          5113100077
- Muhamad Rizki Prawiraatmaja   5113100120
- Dimas Rahman Oetomo           5113100163

1. Pendahuluan

Tugas ini dibuat untuk menyelesaikan Tugas 5 pada matakuliah Perancangan Keamanan & Sistem Jaringan (PKSJ) Semester Ganjil 2016/2017, Teknik Informatika ITS, Surabaya. Pada tugas ini digunakan tools Metasploit yang berjalan di Kali Linux, serta OS yang menjadi sasaran serangnya adalah Metasploitable 1 dan 2. Tugas ini bertujuan untuk dapat memahami cara menemukan celah keamanan serta vulnerability yang mungkin ada pada sistem, guna menjamin keamanan dari sistem.

2. Teori

 * **Penetration Testing** adalah penyerangan secara sengaja ke sistem komputer dengan maksud untuk menemukan celah keamanan, titik lemah sekuritas sistem, memastikan keamanan suatu sistem dan mendapat akses pada sistem dengan cara mengeksploitasi celah-celah keamanan yang ada. Tahapan pada penetration testing adalah preinteraction, intelligence gathering, threat modelling, vulnerability analysis, exploitation, post-exploitation dan reporting
 
 * **Exploit** adalah sebuah software, sekumpulan data atau sekumpulan command yang memanfaatkan bug atau celah keamanan pada sistem. Exploit menyebabkan kelakuan yang tidak diinginkan atau tidak diduga pada software atau hardware komputer target
 
 * **Metasploit** adalah proyek keamanan komputer yang dapat memberi informasi tentang kelemahan sistem dengan cara dapat melakukan penetration testing dan pengembangan IDS signature. Metasploit framework adalah tool open source yang dapat digunakan untuk mengembangkan dan mengeksekusi kode eksploitasi keamanan pada target machine secara remote. 
 
 * **Metasploitable** adlah mesin virtual Ubuntu Linux yang dibuat secara sengaja untuk memiliki berbagai celah keamanan. Metasploitable didesain sebagai alat untuk tool security testing atau mendemonstrasikan celah-celah keamanan yang umum.

3. Instalasi Metasploit dan Metasploitable

 * Download metasploitable
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/pksj ketinggalan.png "virtual hdd")
 
 * Buat sebuah mesin virtual pada virtual box
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/d1.png "virtual hdd")
 
 * Pilih metasploitable sebagai VDI pada mesin virtual yang dibuat
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/d2.png "virtual hdd")
 
 * metasploitable terbuat. Start metasploitable
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/d3.png "virtual hdd")

 * Login pada metasploitable dengan username msfadmin dan password msfadmin
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m1.png "virtual hdd")
  
 * Berhasil masuk ke metasploitable
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m2.png "virtual hdd")
  
 * Install metasploit. Pastikan antivirus, windows UAC dan firewall sudah mati
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m3.png "virtual hdd")

 * Tunggu hingga selesai. Setelah itu cek localhost:3709, jika halaman ini muncul, maka instalasi metasploit berhasil
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m4.png "virtual hdd")
   
 * Setting host-only adapter pada virtualbox
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m5.png "virtual hdd")
   
 * Pasang host-only adapter pada adapter 3. (Karena pada nmap windows, terbacanya di eth2)
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m6.png "virtual hdd")

 * Atur eth2 pada /etc/network/interfaces
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/d4.png "virtual hdd")

 * cek IP metasploitable dan ip host, lalu cek ping
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m7.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m8.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m9.png "virtual hdd")

 * jalankan metasploit console. TUnggu karena startnya agak lama sampai muncul gambar demikian
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m11.png "virtual hdd")
 
4. Penyerangan 1: admin/tikiwiki/tikidblib
 
 *
 
5. Penyerangan 2: tikiwiki_graph_formula_exec
 
 *
 
6. Penyerangan 3 tambahan: unreal ircd
 
 * Lakukan nmap -O 192.168.179.102 untuk cek port yang ada. didapat port irc
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m12.png "virtual hdd")

 * cari tool yang sesuai dengan search unreal_ircd
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m13.png "virtual hdd")

 * perintahkan msfconsole untuk menggunakan unreal ircd dengan sintaks use exploit/unix/irc/unreal_ircd_3281_backdoor
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m14.png "virtual hdd")
   
 * set host yang akan diserang
 
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m15.png "virtual hdd")

 * lakukan exploit
 
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m16.png "virtual hdd")

 * didapatkan sebuah sesi. tembus ke shell metasploit dengan session itu. dengan perintah whoami didapat kita telah masuk ke user root. dengan perintah hostname didapat kalau komputer yang ditembus adalah metasploitable. dengan peintah grep root /etc/shadow didapat password dari root
 
    ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m17.png "virtual hdd")
    
 * didapat daftar password pada cat /etc/shadow
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m17b.png "virtual hdd")

 * perbandingan ls antara msf console dan metasploitable
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m18.png "virtual hdd")

 * perbandingan msf console dan metasploitable jika dilakukan touch (membuat file)
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/m19.png "virtual hdd")

7. Penyerangan 4 tambahan: vsftpd

 * perintahkan msf console untuk menggunakan vsftpd
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t1.png "virtual hdd")
   
 * lakukan exploit
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t2.png "virtual hdd")
   
 * postexploit
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t3.png "virtual hdd")


8. Penyerangan 5 tambahan: usermap_script

 * perintahkan msf console untuk menggunakan usermap_script
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t4.png "virtual hdd")
   
 * lakukan exploit dan didapat hasil postexploit
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t5.png "virtual hdd")
  
 8. Penyerangan 5 tambahan: java_rmi_server

 * perintahkan msf console untuk menggunakan java_rmi_server
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t6.png "virtual hdd")
   
 * lakukan exploit
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t7.png "virtual hdd")
  
 * hasil postexploit
 
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t8.png "virtual hdd")
  ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T5/t9.png "virtual hdd")



. Kesimpulan

 *
