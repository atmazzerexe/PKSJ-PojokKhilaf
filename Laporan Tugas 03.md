Laporan Tugas 3 PKSJ : Analisis Malware dengan Cuckoo Sandbox
------------------------------------------------------------

Anggota Kelompok
- Ilham Gurat Adillion          5113100077
- Muhamad Rizki Prawiraatmaja   5113100120
- Dimas Rahman Oetomo           5113100163

1. Pendahuluan

Tugas ini dibuat untuk menyelesaikan Tugas 3 pada matakuliah Perancangan Keamanan & Sistem Jaringan (PKSJ) Semester Ganjil 2016/2017, Teknik Informatika ITS, Surabaya. Pada tugas ini digunakan tools Cuckoo Sandbox, serta OS yang digunakan adalah Windows XP virtual. Tugas bertujuan untuk dapat memahami cara analisa malware pada file pdf dengan tools cuckoo sandbox

2. Teori

  * **Malware** Malicious Software adalah software yang digunakan untuk mengganggu operasi sebuah komputer, mengumpulkan informasi penting, mencuri akses komputer atau menampilkan iklan secara paksa. Malware didefinisikan oleh fungsi maliciousnya yang berjalan berlawanan dengan kebutuhan user komputer. Malware seringkali bersifat stealthy, sehingga dapat mencuri informasi tanpa sepengetahuan user komputer. (sumber: https://en.wikipedia.org/wiki/Malware)

  * **Virtual Machine** Mesin Virtual adalah emulasi sistem komputer. Mesin virtual memiliki fitur  dan fungsionalitas yang sama seperti komputer/mesin fisik biasa. Selain itu, dapat juga dilakukan virtualisasi untuk satu ekseskusi program saja.  Mesin virtual juga dapat mengemulasikan OS pada arsitektur komputer berbeda dan memungkinkan eksekusi sebuah program atau aplikasi pada OS untuk arsitektur komputer berbeda. (sumber: https://en.wikipedia.org/wiki/Virtual_machine)
 
  * **Virtual Box** Virtual Box adalah tool untuk melakukan virtualisasi yang mempunyai banyak fitur dan berperforma baik.  VirtualBox memungkinkan dijalankannya suatu mesin virtual dalam bentuk berbagai jenis OS dalam host dengan berbagai OS pula. Contohnya, Dalam komputer host ber-OS windows, dapat kita jalankan mesin virtual ber-OS Linux (sumber: https://www.virtualbox.org/manual/ch01.html)

  * **Hyper-v** Microsoft HYper-V atau Viridian adalah sebuah tool untuk membuat mesin virtual pada  windows. Hyper-V membagi komputer menjadi parent partition dan child partition. Stack virtualisasi berjalan pada parent partition dan lalu membuat child partition sebagai lokasi untuk guest OS. (sumber: https://en.wikipedia.org/wiki/Hyper-V)

  * **Sandbox** Sandbox adalah mekanisme security untuk memisahkan program yang berjalan dari program yang lain. Seringkali digunakan untuk mengetes program atau kode yang tidak dipercaya/untrusted tanpa merusak host machine atau OS pengetes. SAndbox tersusun dari set sumberdaya untuk digunakan guest program, yang dikontrol ketat, contohnya memory dan space disk. (sumber: https://en.wikipedia.org/wiki/Sandbox_(computer_security))

  * **Cuckoo** Cuckoo adalah tool sistem analisis malware otomatis yang bersifat open source. Tool ini digunakan secara otomatis menjalankan dan menganalisa file dan membuat analisis komprehensif tentang apa saja yang dilakukan malware saat berjalan pada sebuah OS terisolasi. Cuckoo dapat meretrieve: traces, modifikasi file, memory dump, network traffic, screenshot pada saat program berjalan dan memory dump dari mesin. (sumber: http://docs.cuckoosandbox.org/en/latest/introduction/what/)

3. File Malware yang dites (Tipe: PDF)

  * **Nama file**, diidentifikasi terkena malware .......... didapat dari .........
  
  * **Nama file**, diidentifikasi terkena malware .......... didapat dari .........

4. Dokumentasi Tahapan Pengerjaan

  **Pada komputer HOST lakukan**

  * **buat sebuah mesin virtual dengan OS Ubuntu**
  ** **Klik imstall Ubuntu**
  * **lakukan update dan upgrade mesin virtual ubuntu** dengan perintah 
# sudo apt-get update
# sudo apt-get upgrade

  **Pada mesin virtual lakukan**

  * **install dependensi cuckoo** dengan perintah ated malware analysis framework. When installing Cuckoo for the first time, we can quickly determine that it's not all that easy to install Cuckoo [1]. Therefore, to ease the pain we've described the process of how to install Cuckoo on Debian operating system together will all dependencies.
# apt-get install python python-sqlalchemy python-bson python-dpkt python-jinja2 python-magic python-pymongo python-gridfs python-libvirt python-bottle python-pefile bridge-utils python-pyrex
# pip install jinja2 pymongo bottle pefile cybox maec django chardet

  * **install tcpdump** digunakan untuk sniff packet pada jaringan, dengan perintah
# apt-get install tcpdump
# setcap cap_net_raw,cap_net_admin=eip /usr/sbin/tcpdump

 * **install pydeep**
 
 * **install yara
 
 * **install yara-python** dengan perintah
# pip install yara-python

 * **install distorm**
 
 * **install volatility**
 
 * **lakukakn setting** untuk menghindari error pada Virtual Box dengan perintah
# apt-get install build-essential linux-headers-`uname -r` libvpx1
 
 * **install virtual box** dengan mendownload dan menginstall virtual box terbaru dari websitenya
 
 * **install extension pack virtual box**
 
 * **install rdesktop** untuk dapat menampilkan headless V-Box
 
 * **tambah user cuckoo** dengan perintah
# adduser cuckoo
# usermod -G vboxusers cuckoo

 * **install cuckoo** dengan mendowload cuckoo terbaru dari websitenya, lalu mengekstrak tar yang didapat
 
 * **Buat networking interface untuk Virtual Box** pada ip 192.168.56.1/24 dengan perintah
# VBoxManage hostonlyif create
# ip link set vboxnet0 up
# ip addr add 192.168.56.1/24 dev vboxnet0

 * **set networking interface pada Virtual Box** agar otomatis load saat startup dengan menambah line berikut pada /etc/rc.local
 VBoxManage list vms 2>&1 >> /dev/null
 
 * **cek jalannya cuckoo** dengan perintah ./cuckoo.py
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo1.png "virtual hdd")
 
 ** Pada mesin virtual lakukan instalasi virtual windows XP**
 
 * **buat definisi mesin virtual windows XP**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo2.png "virtual hdd")
  
 * **alokasikan RAM pada virtual Windows XP**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo3.png "virtual hdd")

 * **buat storage VDI**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo4.png "virtual hdd")
 
 * **attach VDI pada virtual machine**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo5.png "virtual hdd")

 * **download dan tautkan ISO windows XP**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo6.png "virtual hdd")
    
 * **jalankan virtual windows XP**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo8.png "virtual hdd")
 
 * **tampilkan via rdesktop 192.168.56.1**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo9.png "virtual hdd")
 
 * **lakukan instalasi windows XP**

 * **tambahkan interface network NAT sekunder** agar dapat terkoneksi dengan internet
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo11.png "virtual hdd")
 
 **Pada virtual WIndows  XP**
 
 * **install python**
 
 * **disable autoupdates**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo12.png "virtual hdd")
 
 * **disable firewall**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo13.png "virtual hdd")
 
 * **install adobe reader**
 
 * **install agent cuckoo**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo14.png "virtual hdd")
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo15.png "virtual hdd")
 
 * **hapus NIC**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo16.png "virtual hdd")
 
 * **ambil snapshot**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo17.png "virtual hdd")
 
 **Konfigurasi Cuckoo**
 
 * **cek apakah konek dengan internet** dengan membandingkan ip virtual XP dengan yang ddisimpan di konfigurasi VBox

 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo18.png "virtual hdd")
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo19.png "virtual hdd")

 * **jalankan cuckoo.py**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo21.png "virtual hdd")
 
 * **cek apakah server bisa mengakses guest virtual machine**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo23.png "virtual hdd")
 
 **Analisa Malware**
 
 * **buka versi web dengan menjlankan ./utils/web.py**

 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo30.png "virtual hdd")

 * **hasil analisa terlihat di web interface**
 
 **MEnjalankan malware sebagai normal user** karena berbahaya jika diakses lewat root
 
 * **rubah home directory user cuckoo**
 
  ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo32.png "virtual hdd")
  
 * **jalankan cuckoo.py**
 
 ![virtualHDD](https://www.proteansec.com/images/2015/02/cuckoo33.png "virtual hdd")


5. Kesimpulan
