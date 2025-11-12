---
name: "Bitcoin Core (macOS & Windows)"
description: Memasang Bitcoin Core di Mac atau Windows
---

![cover](assets/cover.webp)

Memasang Bitcoin Core di komputer biasa sebenarnya bisa dilakukan, tapi kurang ideal. Kalau kamu nggak keberatan membiarkan komputermu menyala 24/7, cara ini akan berjalan dengan baik. Tapi kalau kamu perlu mematikannya, kamu mungkin bakal merasa kesal karena harus menunggu proses sinkronisasi setiap kali menyalakan perangkat lagi.

Panduan ini ditujukan untuk pengguna Mac atau Windows. Pengguna Linux kemungkinan besar sudah tahu cara melakukannya sendiri, tapi instruksinya kurang lebih mirip dengan yang ada di Mac.

## Mulai Bersih

Idealnya, kamu perlu menggunakan komputer yang bersih, bebas dari malware. Bahkan kalau kamu pakai hardware wallet, malware tetap bisa menipu kamu dan membuatmu kehilangan bitcoin.

Kamu bisa menghapus semua data di komputer lama dan menjadikannya komputer khusus untuk Bitcoin, atau beli komputer/laptop baru yang memang didedikasikan untuk itu.

## Hard Drive

Bitcoin Core akan memakan sekitar 400 gigabyte ruang di drive kamu, dan ukurannya akan terus bertambah seiring waktu. Kamu bisa memakai drive internal, tapi bisa juga menambahkan hard drive eksternal. Aku akan jelaskan dua opsi itu.
Idealnya, kamu pakai solid-state drive (SSD). Kalau komputermu tergolong lama, kemungkinan besar belum punya SSD internal. Cukup beli SSD eksternal berukuran 1 atau 2 terabyte dan gunakan itu. Drive biasa memang bisa dipakai, tapi kamu mungkin akan menghadapi berbagai masalah dan kecepatannya akan jauh lebih lambat.

![image](assets/fr/01.webp)

## Unduh Bitcoin Core

Kunjungi situs bitcoin.org (**pastikan kamu tidak pergi ke bitcoin.com**, itu situs shitcoin milik Roger Ver yang menipu orang supaya membeli Bitcoin Cash alih-alih Bitcoin).
Setelah kamu sampai di sana, agak aneh karena letak unduhan perangkat lunaknya tidak langsung terlihat jelas. Buka menu Resources, lalu klik Bitcoin Core, seperti yang ditunjukkan pada gambar di bawah ini:

![image](assets/fr/02.webp)

Ini akan membawamu ke halaman unduhan:

![image](assets/fr/03.webp)

Klik tombol oranye Unduh Bitcoin Core:

![image](assets/fr/04.webp)

Ada beberapa opsi yang bisa kamu pilih tergantung pada jenis komputermu. Dua opsi pertama yang relevan untuk panduan ini adalah Windows dan Mac. Pilih salah satu dari bilah sebelah kiri. Setelah kamu mengkliknya, proses unduhan akan dimulai secara otomatis, biasanya tersimpan di folder Downloads.

## Verifikasi unduhan (bagian 1)

Anda memerlukan file yang berisi hash dari berbagai rilis. File ini dulu ada di halaman unduhan bitcoin.org, tetapi sekarang telah pindah ke bitcoincore.org/en/download:

![image](assets/fr/05.webp)

Anda memerlukan file hash biner SHA256. File ini berisi hash SHA256 dari berbagai paket unduhan Bitcoin Core.

Selanjutnya, kita perlu meng-hash unduhan Bitcoin Core dan membandingkannya dengan apa yang dikatakan file tersebut hash seharusnya. Kemudian kita tahu unduhan identik dengan apa yang diharapkan, menurut bitcoincore.org.

Navigasikan ke direktori Unduhan lagi dan eksekusi perintah ini (ganti X dengan nama file unduhan node bitcoin penuh secara tepat):

```bash
shasum -a 256 XXXXXXXXXXXX # <--- UNTUK MAC
certutil -hashfile XXXXXXXXXXX SHA256 # <--- UNTUK WINDOWS
```

Anda akan mendapatkan output hash. Catat itu, dan bandingkan dengan hash yang terkandung dalam file SHA256SUMS.

Jika outputnya identik, maka Anda telah memverifikasi bahwa tidak ada bit data yang telah diubah... hampir. Kita masih perlu memastikan file SHA256SUMS tidak berbahaya.

Untuk melanjutkan ke langkah berikutnya, kita harus memiliki gpg terinstal di komputer kita.
Untuk melakukan itu, lihat panduan SHA256/gpg saya, dan gulir sekitar setengah jalan ke bagian "Download gpg", dan cari subjudul sistem operasi Anda. Kemudian kembali ke sini.
## Dapatkan Kunci Publik

Kembali ke halaman unduhan, dapatkan file tanda tangan hash SHA256

![image](assets/fr/06.webp)

Klik dan simpan file ke disk, sebaiknya direktori Downloads.

File ini berisi tanda tangan oleh berbagai orang, dari file SHA256SUMS.

Kami ingin kunci publik pengembang utama, Wladimir J. van der Laan di gantungan kunci komputer kita. ID kunci publiknya adalah:
1 - 01EA 5486 DE18 A882 D4C2 6845 90C8 019E 36C2 E964

Salin teks tersebut ke dalam perintah berikut:

```bash
gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys 01EA5486DE18A882D4C2684590C8019E36C2E964
```

Sebagai informasi, kapan saja, Anda dapat melihat kunci apa saja yang ada di gantungan kunci komputer dengan perintah ini:

```bash
gpg --list-keys
```

## Verifikasi unduhan (bagian 2)

Kami memiliki kunci publik, jadi sekarang kami dapat memverifikasi file SHA256SUMS yang berisi hash dari unduhan Bitcoin Core, dan tanda tangan untuk hash tersebut.

Buka Terminal atau CMD lagi, dan pastikan Anda berada di direktori Downloads. Dari sana, jalankan perintah ini:

```bash
gpg –verify SHA256SUMS.asc SHA256SUMS
```

File pertama yang terdaftar adalah ejaan tepat dari file tanda tangan. File kedua yang terdaftar harus menjadi ejaan tepat dari file teks yang berisi hash. Kedua file harus berada dalam direktori yang sama dan Anda perlu berada dalam direktori file tersebut, jika tidak, Anda harus mengetikkan jalur lengkap untuk setiap file.

Ini adalah output yang harus Anda dapatkan

![image](assets/fr/07.webp)

Aman untuk mengabaikan pesan PERINGATAN – itu hanya mengingatkan Anda bahwa Anda belum bertemu Wladimir di bagian kunci dan secara pribadi bertanya kepadanya apa kunci publiknya, dan kemudian memberitahu komputer Anda untuk mempercayai kunci ini sepenuhnya.

Jika Anda mendapatkan pesan ini, Anda sekarang tahu bahwa file SHA256SUMS.asc tidak telah diubah setelah Wladimir menandatanganinya.

## Instal Bitcoin Core

Anda tidak seharusnya memerlukan instruksi rinci tentang cara menginstal programnya.

![image](assets/fr/08.webp)

## Jalankan Bitcoin Core

Di Mac, Anda mungkin mendapatkan peringatan (Apple masih anti-Bitcoin)

![image](assets/fr/09.webp)

Klik OK, lalu buka Preferensi Sistem Anda

![image](assets/fr/10.webp)

Klik ikon Keamanan dan Privasi:

![image](assets/fr/11.webp)

Kemudian klik "buka bagaimanapun juga":

![image](assets/fr/12.webp)

Kesalahan akan muncul lagi, tetapi kali ini Anda akan memiliki tombol BUKA yang tersedia. Klik itu.

![image](assets/fr/13.webp)

Bitcoin Core harus dimuat dan Anda akan disajikan dengan beberapa opsi:

![image](assets/fr/14.webp)

Di sini Anda dapat memilih untuk menggunakan jalur default untuk tempat blockchain akan diunduh, atau Anda dapat memilih drive eksternal Anda. Saya merekomendasikan tidak mengubah jalur default jika Anda akan menggunakan drive internal, itu membuat hal-hal lebih mudah untuk diatur saat Anda menginstal perangkat lunak lain untuk berkomunikasi dengan Bitcoin Core.
Anda dapat memilih untuk menjalankan node yang dipangkas, ini menghemat ruang, tetapi membatasi apa yang dapat Anda lakukan dengan node Anda. Bagaimanapun, Anda akan mengunduh seluruh blockchain dan memverifikasinya, jadi jika Anda memiliki ruang, simpan apa yang telah Anda unduh, dan jangan pangkas jika Anda bisa menghindarinya.
Setelah Anda konfirmasi, blockchain akan mulai diunduh. Ini akan memakan waktu berhari-hari.

![image](assets/fr/15.webp)

Anda dapat mematikan komputer dan kembali untuk mengunduh jika Anda mau, ini tidak akan menyebabkan kerusakan.

