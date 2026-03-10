## Modul 2: Pengenalan Tools (Wireshark)
Laporan pekan 2 ini kita akan menjalankan wireshark untuk keperluan analisis lalu lintas jaringan.
### 1. Tujuan Praktikum
* Mahasiswa dapat melakukan instalasi tool yang digunakan (Wireshark).
* Mahasiswa dapat menggunakan tool (Wireshark) untuk menangkap dan mengidentifikasi paket data.

### 2. Prerequisites (Prasyarat)
Sebelum menjalankan aplikasi di Windows, pastikan hal-hal berikut telah terpenuhi:
* **Sistem Operasi:** Perangkat menggunakan Windows 10 atau 11.
* **Hak Akses Administrator:** Diperlukan izin administrator untuk menginstal driver dan menjalankan fungsi penangkapan paket (*packet capturing*).
* **Npcap/WinPCap Driver:** Library ini harus terinstal agar Wireshark dapat berinteraksi dengan kartu jaringan (NIC). Jika belum ada, biasanya akan ditawarkan saat proses instalasi Wireshark.
* **Antarmuka Jaringan (Interface):**  (Ethernet atau Wi-Fi) harus dalam keadaan aktif dan terhubung ke jaringan agar lalu lintas data dapat terbaca.

### 3. Menjalankan Wireshark
1. Setelah aplikasi terbuka, perhatikan bagian **Capture**.
2. Pilih salah satu **Interface** jaringan yang muncul (misalnya Wi-Fi atau Ethernet). Pastikan memilih yang memiliki grafik aktivitas (garis naik turun).
3. Klik dua kali pada interface tersebut atau klik ikon **Sirip Hiu Biru** di pojok kiri atas untuk memulai penangkapan paket secara *live*.
4. Untuk menguji, buka browser dan akses sebuah situs web, lalu perhatikan paket-paket yang muncul di jendela utama Wireshark.
5. Membuka browser dan mengakses halaman berikut: "http://gaia.cs.umass.edu/wireshark-labs/INTRO-wireshark-file1.html"

**hasil nya akan seperti dibawah ini :**
![Gambar website intro wireshark](../image/week-2%20gambar%20website.png)
**Jangan lupa untuk mengecek http bukan htpps**

6. lalu Mengamati paket HTTP GET yang dikirim dari komputer ke server.
7. dan jugaMengamati detail paket pada bagian packet details.
8. untuk mengecek di dalam wireshark kita bisa mengeklik ini.

![Gambar website intro wireshark](../image/week-2%20wireshark%20tutorial.png)

9. lalu untuk mengecek apakah data dari website tersebut untuk membaca kita bisa menulis `http` pada bagian filter

![Gambar website intro wireshark](../image/week-2%20gambar%20wireshark%202.png)

**setelah itu kalian klick `enter` untuk menjalan filter pencariannya.**

![Gambar website intro wireshark](../image/week-2%20wireshark%203.png)

10. dari gambar tersebut kita telah melihat kita dapat jaringan dari `http` tadi pada bagian wireshark.

### 4. Analisis
Berdasarkan percobaan yang telah kita lakukan, Wireshark dapat digunakan sebagai melihat aktivitas jaringan secara detail.Apalagi browser mengakses sebuah halaman web,komputer tersebut  akan mengirimkan permintaan HTTP GET ke server. Server kemudian merespon dengan mengirimkan data halaman web kepada client.

### 5. Kesimpulan

Melalui praktikum ini, penggunaan Wireshark memungkinkan kita untuk melihat secara visual bagaimana data mengalir di dalam jaringan. Pemahaman mengenai filtering dan struktur paket sangat krusial dalam melakukan troubleshooting maupun analisis keamanan jaringan.
