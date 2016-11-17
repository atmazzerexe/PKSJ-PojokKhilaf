Laporan Tugas 4 PKSJ : Intrusion Detection System Dengan Ossec
------------------------------------------------------------

Anggota Kelompok
- Ilham Gurat Adillion          5113100077
- Muhamad Rizki Prawiraatmaja   5113100120
- Dimas Rahman Oetomo           5113100163

1. Pendahuluan

Tugas ini dibuat untuk menyelesaikan Tugas 4 pada matakuliah Perancangan Keamanan & Sistem Jaringan (PKSJ) Semester Ganjil 2016/2017, Teknik Informatika ITS, Surabaya. Pada tugas ini digunakan tools Ossec yang berjalan di Linux, serta OS yang dideteksi pergerakannya adalah Windows 10. Tugas bertujuan untuk dapat memahami cara deteksi intruse di os yang ditetapkan sebagai agent dengan tools Ossex.

2. Teori

  * **Virtual Machine** Mesin Virtual adalah emulasi sistem komputer. Mesin virtual memiliki fitur  dan fungsionalitas yang sama seperti komputer/mesin fisik biasa. Selain itu, dapat juga dilakukan virtualisasi untuk satu ekseskusi program saja.  Mesin virtual juga dapat mengemulasikan OS pada arsitektur komputer berbeda dan memungkinkan eksekusi sebuah program atau aplikasi pada OS untuk arsitektur komputer berbeda. (sumber: https://en.wikipedia.org/wiki/Virtual_machine)
 
  * **Virtual Box** Virtual Box adalah tool untuk melakukan virtualisasi yang mempunyai banyak fitur dan berperforma baik.  VirtualBox memungkinkan dijalankannya suatu mesin virtual dalam bentuk berbagai jenis OS dalam host dengan berbagai OS pula. Contohnya, Dalam komputer host ber-OS windows, dapat kita jalankan mesin virtual ber-OS Linux (sumber: https://www.virtualbox.org/manual/ch01.html)

  * **Hyper-v** Microsoft HYper-V atau Viridian adalah sebuah tool untuk membuat mesin virtual pada  windows. Hyper-V membagi komputer menjadi parent partition dan child partition. Stack virtualisasi berjalan pada parent partition dan lalu membuat child partition sebagai lokasi untuk guest OS. (sumber: https://en.wikipedia.org/wiki/Hyper-V)
  
  * **Intrusion Detection System** IDS merupakan perangkat atau aplikasi perangkat lunak yang memonitor jaringan untuk mengetahui aktivitas intrusi yang terjadi. Setiap intrusi yang ditangkap akan dilaporkan ke administrator atau di kumpulkan menggunakan security information and event management (SIEM) sistem. (sumber: https://en.wikipedia.org/wiki/Intrusion_detection_system)
  
  * **Ossec** Ossec merupakan aplikasi host-based intrusion detection system(HIDS) yang open-source. Program ini melakukan log analysis, integrity checking, windows registry monitoring, rootkit detection, time based a;erting, dan active response, Ossec dapat mendeteksi intrusi berbagai macam sistem operasi salah satunya adalah Linux, OpenBSD, FreeBSD, OS X, Solaris and Windows. (Sumber: https://en.wikipedia.org/wiki/OSSEC)

3. Instalasi Ossec dan Agent Ossec

 * Install build-essential dengan mengetik
   `# apt-get install build-essential`
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/1.png "virtual hdd")
 
 * Install mysql-dev dan postgresql-dev dengan mengetik
   `# apt-get install mysql-dev postgresql-dev`
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/2.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/3.png "virtual hdd")

 * Download file instalasi ossec dengan mengetik
   '# wget -U ossec https://bintray.com/artifact/download/ossec/ossec-hids/ossec-hids-2.8.3.tar.gz'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/4.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/5.png "virtual hdd")
   
   '# wget -U ossec https://raw.githubusercontent.com/ossec/ossec-docs/master/docs/whatsnew/checksums/2.8.3/ossec-hids-2.8.3.tar.gz.sha256'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/6.png "virtual hdd")
   
 * Cek data downloadan dengan perintah
   '# cat ossec-hids-2.8.3.tar.gz.sha256'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/7.png "virtual hdd")
   
 * Untar file yang didownload
   '# tar -zxvf ossec-hids-*.tar.gz (or gunzip -d; tar -xvf)'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/8.png "virtual hdd")

 * Install ossec dengan perintah 
   '# ./install.sh'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/9.png "virtual hdd")
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/10.png "virtual hdd")

 * ossec sudah bisa dijalankan dengan perintah
   '# /var/ossec/bin/ossec-control start'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/11.png "virtual hdd")

 * download install ossec client pada windows dengan link https://bintray.com/artifact/download/ossec/ossec-hids/ossec-agent-win32-2.8.3.exe
 
 * jalankan ossec client, masukkan IP virtual
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/12.png "virtual hdd")

 * untuk mendapatkan key, tambahkan agen dengan mengerun perintah
   '# /var/ossec/bin/manage_agents'
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/13.png "virtual hdd")
   
 * isi data-data agen yang diperlukan
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/14.png "virtual hdd")

 * lalu didapatkan key untuk ossec client
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/20.png "virtual hdd")
    
 * masukkan key ke windows agent, ossec agent siap dijalankan
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/24.png "virtual hdd")
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/21.png "virtual hdd")
   
 * untuk keperluan pengujian, pada agent dibuatlah sebuah folder dummy ('C:\Masuk") beserta file-nya
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/22.png "virtual hdd")
 
 * kemudian di server ossec, dengan menggunakan gedit dan autentikasi root, tambahkan konfigurasi untuk mengawasi folder di agent windows secara real-time, melaporkan perubahan file, serta meningkatkan frekuensi pengecekan
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/23.png "virtual hdd") 

 * tambahkan pula konfigurasi untuk mencatat log event windows beserta jenis-jenis event yang terjadi

   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/25.png "virtual hdd")
   
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/26.png "virtual hdd")
   
 * restart ossec server, lalu mulai perubahan data pada windows agent, misal dengan merubah user permission dari folder "C:\Masuk"
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/27.png "virtual hdd")
 
 * simpan perubahan dan peringatan akan muncul pada log file ossec yang terletak di /var/ossec/logs/alerts/alerts.log
 
   ![virtualHDD](https://github.com/atmazzerexe/PKSJ-PojokKhilaf/blob/master/Gambar/T4/27.png "virtual hdd")
   
4. Kesimpulan
 * Ossec memiliki kelebihan dibandingkan snort dimana instalasi dan perubahan rule dapat dilakukan lebih mudah. Namun, kompatibilitas dengan OS Windows 8 Ke atas masih dipertanyakan karena terdapat beberapa fungsi yang tidak bekerja seperti pengaplikasian rule dari server ke Windows.
