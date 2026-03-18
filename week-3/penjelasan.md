# Modul 3: Pengenalan Tools (Wireshark)
Laporan pekan 3 ini kita akan menjalankan wireshark untuk mengetahui cara kerja protokol HTTP.
## Tujuan Praktikum
* Mahasiswa dapat melakukan menginvestigasi cara kerja protokol HTTP menggunakan Wireshark.
* Mahasiswa dapat menggunakan tool (Wireshark) untuk menangkap dan mengidentifikasi paket data.

## Prerequisites (Prasyarat)
Sebelum menjalankan aplikasi di Windows, pastikan hal-hal berikut telah terpenuhi:
* **Sistem Operasi:** Perangkat menggunakan Windows 10 atau 11.
* **Hak Akses Administrator:** Diperlukan izin administrator untuk menginstal driver dan menjalankan fungsi penangkapan paket (*packet capturing*).
* **Npcap/WinPCap Driver:** Library ini harus terinstal agar Wireshark dapat berinteraksi dengan kartu jaringan (NIC). Jika belum ada, biasanya akan ditawarkan saat proses instalasi Wireshark.
* **Antarmuka Jaringan (Interface):**  (Ethernet atau Wi-Fi) harus dalam keadaan aktif dan terhubung ke jaringan agar lalu lintas data dapat terbaca.

## 1. Basic HTTP GET/response interaction
**langkah kali ini memulai eksplorasi HTTP file HTML sederhana seperti langkah berikut :**

1. Jalankan browser web Anda.
2. Jalankan packet sniffer Wireshark. Masukkan "http" (hanya huruf, bukan tanda kutip, dan
dalam huruf kecil) di display-filter-specification window (textfield filter paket di bagian atas
daftar paket), sehingga hanya pesan HTTP yang diambil yang akan ditampilkan nanti di
jendela daftar paket.
3. Tunggu sedikit lebih dari satu menit, dan kemudian mulai pengambilan paket Wireshark.
4. Masukkan berikut ini : "http://gaia.cs.umass.edu/wireshark-labs/HTTPwireshark-file1.html", Browser Anda akan menampilkan file HTML satu baris yang sangat
sederhana.
5. Hentikan pengambilan paket Wireshark

![halaman wireshark search htpp](../image/week-2%20wireshark%203.png)

## 2. HTTP CONDITIONAL GET/response interaction
**langkah kali ini digunakan oleh browser untuk mengoptimalkan penggunaan bandwidth melalui caching objek.**

1. jalankan browser web Anda, dan pastikan cache browser Anda dibersihkan.
2.  Mulai tangkap paket dengan Wireshark.
3. Masukkan URL : "http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html" Browser Anda akan menampilkan file HTML lima baris yang sangat sederhana.

![halaman website contoh html](../image/week-3%20gett.png)

4. Masukkan kembali URL yang sama ke browser Anda dengan cepat (atau cukup tekan tombol refresh di browser Anda).
· Hentikan pengambilan paket Wireshark, dan masukkan “http” di jendela spesifikasi filter tampilan, sehingga hanya pesan HTTP yang diambil yang akan ditampilkan nanti di jendela daftar paket.

![halaman wireshark saat sniffing](../image/week-3%20conditional_get.png)
 wireshark saat sniffing
## 3. Retrieving Long Documents
**Fitur analisis ini bertujuan untuk menunjukkan bagaimana protokol TCP menangani pengiriman data yang melebihi batas ukuran kapasitas paket standar (MTU).**

1. Jalankan browser web Anda, dan pastikan cache browser Anda dibersihkan.
2.  Mulai tangkap paket dengan Wireshark
3.  Masukkan URL berikut "http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html" Browser Anda seharusnya menampilkan Bill of Rights AS yang agak panjang.

![halaman website contoh html](../image/week-3%20documents-logs.png)


4.  Hentikan pengambilan paket Wireshark, dan masukkan “http” di jendela tampilan-filterspesifikasi, sehingga hanya pesan HTTP yang diambil yang akan ditampilkan.

![halaman  wireshark saat sniffing](../image/week-3%20wireshark%20doc-logs.png)

## 4. HTML Documents dengan Embedded Objects
**Fitur analisis ini bertujuan untuk menunjukkan bagaimana browser bekerja secara paralel atau sekuensial untuk menyusun sebuah halaman web lengkap. Sebuah halaman web seringkali bukan hanya satu file tunggal, melainkan gabungan dari file HTML dasar beserta objek lain (seperti gambar, skrip, atau gaya) yang mungkin disimpan di server yang sama atau berbeda**

1. Jalankan browser web Anda, dan pastikan cache browser Anda dibersihkan.
2. Mulai tangkap paket dengan Wireshark.
3.  Masukkan URL berikut  "http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html"

![halaman website contoh html](../image/week-3%20html-doc.png)


4. Browser Anda harus menampilkan file HTML pendek dengan dua gambar. Kedua gambar ini direferensikan dalam file HTML dasar. Artinya, gambar itu sendiri tidak terdapat dalam HTML.alih-alih hanya terdapat URL kedua gambar pada file HTML tersebut.Browser Anda harus mengambil logo ini dari URL situs web yang disematkan pada file HTML.
5. Hentikan pengambilan paket Wireshark, dan masukkan “http” di jendela tampilan-filterspesifikasi, sehingga hanya pesan HTTP yang diambil yang akan ditampilkan.

![halaman  wireshark saat sniffing](../image/week-3%20object.png)
6. kita dapat lihat disitu ada get person.png untuk gambarnya.

## 4. HTTP Authentication
**Fitur ini menunjukkan bagaimana protokol HTTP menangani hak akses pengguna melalui mekanisme HTTP Basic Authentication. Kita akan melihat bagaimana username dan password dikirimkan melalui jaringan dan memahami mengapa metode ini memiliki risiko keamanan yang signifikan jika tidak dibarengi dengan enkripsi tingkat lanjut (seperti HTTPS).**

Melalui praktikum ini, penggunaan Wireshark memungkinkan kita untuk melihat secara visual bagaimana data mengalir di dalam jaringan. Pemahaman mengenai filtering dan struktur paket sangat krusial dalam melakukan troubleshooting maupun analisis keamanan jaringan.

1. Jalankan browser web Anda, dan pastikan cache browser Anda dibersihkan.
2. Mulai tangkap paket dengan Wireshark.
3. Masukkan URL berikut  "http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html"
4. **Akun: Menggunakan username `wireshark-students` dan password `network`.**

![halaman website contoh html](../image/week-3%20login.png)

**setelah login**

![halaman website contoh html](../image/week-3%20setelah-login.png)

5. Hentikan pengambilan paket Wireshark, dan masukkan “http” di jendela tampilan-filterspesifikasi, sehingga hanya pesan HTTP yang diambil yang akan ditampilkan.

![halaman  wireshark saat sniffing](../image/week-3%20sniffing%20login.png)

***untuk melihat unicode passwordnya pada bagian get yang diatas OK tersebut***

6. keamanan data nya menggunakan format **`Base64`**

7. Kesimpulan Keamanan: Eksperimen ini membuktikan bahwa HTTP Basic Authentication sangat tidak aman jika dilakukan melalui koneksi HTTP standar, karena data sensitif dikirim secara "telanjang" di jaringan.

### 5. Kesimpulan

1. **Mekanisme Segmentasi TCP:**
File HTML berukuran besar (lebih dari standar MTU ~1500 byte) tidak dikirim dalam satu paket tunggal, melainkan dipecah oleh TCP menjadi beberapa segmen (TCP segment of a reassembled PDU) untuk kemudian disusun kembali oleh browser.

2. **Sifat Referensial Halaman Web:**
Satu halaman web yang kompleks terdiri dari banyak permintaan HTTP yang terpisah. Browser harus melakukan GET tambahan untuk setiap objek (gambar/logo) yang disematkan dalam file HTML dasar.

3. **Proses Handshake Autentikasi:**
Akses ke halaman terproteksi diawali dengan penolakan server (HTTP 401 Unauthorized) sebelum browser mengirimkan kredensial melalui header Authorization.

4. **Kerentanan Keamanan HTTP:**
Protokol HTTP mengirimkan data kredensial (username & password) hanya menggunakan Base64 Encoding, bukan enkripsi. Artinya, data tersebut sangat mudah dibaca oleh pihak ketiga menggunakan alat packet sniffer seperti Wireshark, sehingga sangat tidak aman tanpa lapisan HTTPS.