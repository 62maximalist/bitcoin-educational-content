---
name: Ledger Nano S

description: Cara menyiapkan perangkat Ledger Nano S kamu
---

![image](assets/cover.webp)

Dompet hardware (cold wallet) – €60 – Cocok buat pemula – Amanin Bitcoin senilai €2.000 sampai €50.000

Ledger itu solusi buatan Prancis buat ngamanin Bitcoin dengan cara yang simpel dan praktis.

Di tutorial ini, kita juga bahas soal passphrase — fitur keamanan lanjutan buat nyimpen jumlah besar, mulai dari €20.000 sampai €100.000.

https://www.youtube.com/watch?v=_vsHNTLi8MQ

# Menghubungkan Ledger ke Sparrow Bitcoin Wallet (panduan penulisan)

Pastikan kamu udah baca dulu bagian “Menggunakan Bitcoin Hardware Wallets”. Di sini, kita bakal skip beberapa langkah umum dan langsung fokus ke hal-hal yang khusus buat Ledger.

## Menyiapkan perangkat

Ledger udah dilengkapi kabel USB bawaan. Pastikan kamu pakai kabel itu—jangan asal ambil kabel lama yang ada di rumah. Soalnya, beberapa kabel USB cuma bisa ngisi daya doang. Nah, kabel bawaan Ledger ini bisa ngirim data dan daya sekaligus. Dulu gue pernah coba pakai kabel charger HP yang nganggur, eh ternyata device-nya gagal konek.

Colokin ke komputer kamu, dan perangkatnya bakal langsung nyala otomatis.

![image](assets/1.webp)

Jelajahi opsi-opsinya. Kamu akan melihat

1. Atur sebagai perangkat baru
2. Pulihkan dari frasa pemulihan

Intinya, di bagian ini kamu ditanya: mau bikin seed baru langsung dari perangkat, atau udah punya seed sendiri yang mau dipakai? Secara umum, praktik terbaik sih bikin seed sendiri. Tapi ngejalaninnya dengan aman itu level lanjutan banget—dan nggak dibahas di artikel ini. Jadi untuk sekarang, pilih aja opsi “Atur sebagai perangkat baru”.

Selanjutnya, kamu bakal diminta buat pilih PIN. Perlu diingat: ini bukan bagian dari seed Bitcoin kamu—PIN ini khusus buat ngunci perangkat Ledger-nya aja.

Setelah itu, perangkat bakal nunjukin 24 kata yang harus kamu cek satu per satu dan catat dengan hati-hati.

Agak membingungkan, tapi pas kamu sampai di akhir, layar bakal bilang “tekan kiri untuk verifikasi kata-kata kamu”. Padahal itu bukan buat lanjut ke tahap berikutnya—itu cuma biar kamu bisa balik lagi ngecek kata-katanya. Yang bener, tekan kanan buat lanjut, lalu konfirmasi dengan menekan tombol kiri dan kanan secara bersamaan.

Bagian selanjutnya lumayan bikin kesel. Perangkat bakal acak urutan 24 kata tadi, dan kamu harus konfirmasi satu per satu—dari kata pertama sampai ke-24. Setiap kali, kamu harus muter lewat semua pilihan kata buat milih yang bener. Tapi setelah selesai, tinggal tekan dua tombol barengan buat konfirmasi dan lanjut ke tahap berikutnya.

![image](assets/2.webp)

Di dasbor, kamu bakal lihat ada tombol pengaturan dan tombol plus (+) buat install aplikasi. Tapi sebelum itu bisa dipakai, kamu harus sambungin dulu perangkatnya ke Ledger Live. Tenang, langkah itu bakal kita bahas setelah ini...

## Unduh Ledger Live

Kamu bisa download Ledger Live dari website resminya, tapi kalau mau lebih yakin soal keamanan, mending ambil langsung dari GitHub—karena di situ tempat kode sumber resminya disimpan.

Google "ledger live GitHub" atau klik tautan ini https://github.com/LedgerHQ/ledger-live-desktop

![image](assets/3.webp)

Scroll ke bawah sampai kamu melihat judul, "Downloads"…

![image](assets/4.webp)

Di bagian bawah, kamu akan melihat tautan: Instruksi untuk memverifikasi hash dan tanda tangan dari paket instalasi tersedia di halaman ini. Klik ini.(https://live.ledger.tools/lld-signatures)

![image](assets/5.webp)

Kamu bisa download Ledger Live langsung dari situs resminya. Di bagian atas halaman, bakal ada pilihan link download sesuai sistem operasi. Tinggal klik yang sesuai, terus lanjut install seperti biasa.

Selanjutnya, kita mau verifikasi hash dari file yang tadi kamu download—buat nambah lapisan keamanan. Ledger biasanya ngasih hash resmi dari setiap file yang mereka rilis, dan itu bisa kamu temuin di halaman download-nya. Nah, kita bakal nge-hash file unduhan kamu, terus bandingin hasilnya sama hash resmi tadi. Kalau hasilnya identik, berarti file-nya aman dan nggak diutak-atik.

Buka terminal pada Mac atau CMD di windows. Ikuti perintah berikut...

cd Downloads

<Enter>

```bash
shasum -a 512 ledger-live-desktop-2.32.2-mac.dmg # <--- Untuk Mac
certutil -hashfile ledger-live-desktop-2.32.2-win.exe SHA512 # <--- Untuk Windows
```

<Enter>

-------------- lanjut disini

Semoga udah jelas ya, perintah dimulai setelah tanda panah (>). Kalau nama file-nya beda karena artikel ini udah agak lama, pastikan kamu ganti nama file di perintahnya sesuai file yang kamu download. Setiap perintah dijalankan dengan menekan tombol <Enter>. Kadang perintahnya bisa keliatan kepotong di browser, tapi sebenarnya semuanya ditulis dalam satu baris, ya.

Lihat output dari hash dan pastikan itu identik dengan yang dipublikasikan di GitHub.

Idealnya sih, kamu juga perlu lebih teliti dan pastiin kalau hash yang dipublikasikan itu beneran asli, bukan palsu. Cara ngeceknya bisa lewat tanda tangan GPG. Tapi bagian itu nggak dibahas di artikel ini. Kalau kamu penasaran (dan sebaiknya kamu pelajari juga nantinya), coba telusuri artikel ini lebih lanjut ya.

## Terhubung ke Ledger Live

Sebelum kamu buka Ledger Live, ada baiknya nyalain VPN dulu buat bantu jaga privasi. Ledger emang tetap bakal tahu semua alamat Bitcoin kamu, tapi setidaknya mereka nggak bisa ngelacak alamat IP kamu—yang bisa ngarah ke lokasi rumahmu. Kalau butuh rekomendasi, Mullvad VPN itu salah satu layanan yang bagus dan harganya juga masuk akal (nggak di-endorse ya, emang itu yang aku pakai sendiri).

Install dulu softwarenya ke komputer kamu, lalu jalankan kayak biasa.

![image](assets/6.webp)

Pilih perangkatmu, dan pilih "Pertama kali menggunakan..."

![image](assets/7.webp)

Setelah itu, kamu bakal dibawa lewat wizard (panduan langkah demi langkah). Tapi karena semua langkahnya udah kita lakuin sebelumnya, kamu bisa langsung klik-klik aja buat lanjut.

![image](assets/8.webp)

Setelah lewat beberapa langkah dan kuis, Ledger Live bakal ngecek apakah perangkat kamu asli. Pastikan perangkatnya udah terhubung dan kamu udah masukin PIN. Nanti bakal muncul permintaan di perangkat, apakah kamu ngizinin Ledger Live buat nyambung. Jawab aja “iya”, tentu aja harus dikonfirmasi di perangkat.

![image](assets/9.webp)

Nanti bakal muncul pop-up yang isinya beberapa iklan shitcoin, nyamar jadi “catatan rilis”. Cuek aja, langsung skip bagian itu. Setelah itu, kamu bakal masuk ke tampilan utama seperti ini.

![image](assets/10.webp)

Kamu harus klik "Tambah akun" untuk mendapatkan Dompet Bitcoin.

![image](assets/11.webp)

Pastikan kamu memilih Bitcoin, dan bukan Bitcoin Cash atau shitcoin lainnya. Ini akan memeriksa perangkat, dan kamu harus mengonfirmasi untuk melanjutkan DI PERANGKAT. Ini akan menghitung alamat selama beberapa menit. Kemudian klik SELESAI.

![image](assets/12.webp)
![image](assets/13.webp)

Oke, sekarang kamu udah punya “manajer dompet shitcoin” di komputer—yang sebenarnya cuma pembungkus doang buat bisa ngakses dompet Bitcoin. Sebenarnya, kamu nggak butuh banget software ini lagi setelah instalasi awal. Tujuan utamanya cuma satu: masukin aplikasi Bitcoin ke perangkat Ledger kamu. Dan ini satu-satunya cara resmi, kecuali kamu mau ngoprek pake teknik rekayasa perangkat lunak tingkat ekstrem.

Ingat bahwa sebelumnya, di perangkat, kita memiliki tombol pengaturan dan tombol tanda tambah. Sekarang kami memiliki tombol ekstra - tombol Aplikasi Bitcoin.

Kamu dapat mematikan Ledger Live sekarang.

-----------------------lanjut disini besok

## Tambahkan passphrase
Kini setelah kita memiliki Aplikasi Bitcoin, kita dapat menambahkan passphrase ke seed phrase kita. Kita tidak bisa melakukan itu sebelumnya ketika seed pertama kali dibuat karena pada awalnya, kita tidak memiliki Aplikasi Bitcoin, dan kita perlu terhubung ke Ledger Live untuk mendapatkannya.

Pergi ke menu "settings" di dalam perangkat, kemudian submenu "security". Kemudian pilih passphrase. Anda akan melihat "Advanced feature". Klik tombol kanan, Anda akan melihat "read manual..." dan kemudian setelah klik tombol kanan lagi, Anda akan melihat "back". Tapi itu bukan akhirnya. Secara intuitif, Anda mungkin berpikir itu sudah selesai, tapi klik tombol kanan lagi. Anda akan melihat "set up passphrase".

Anda dapat memutuskan untuk "attach to PIN" atau "Set temporarily". Saya merekomendasikan "attach to the PIN". Dengan cara itu, Anda dapat mengakses dompet yang berbeda tergantung pada PIN yang Anda masukkan ketika pertama kali menyalakan perangkat. Jika Anda "set temporarily", Anda harus memasukkan passphrase setiap kali Anda ingin mengakses dompet tersebut, tapi itu selalu dari PIN default.

Masukkan passphrase dan konfirmasikan.

Ini akan meminta Anda untuk "Current PIN". Ini bukan PIN yang Anda asosiasikan dengan passphrase baru. Ini adalah PIN yang Anda masukkan ketika Anda menyalakan perangkat untuk sesi ini.

Anda sekarang dapat keluar ke menu utama dengan memilih opsi kembali beberapa kali.

## Mengawasi Dompet

Dalam artikel sebelumnya, saya menjelaskan cara mengunduh dan memverifikasi Sparrow wallet, dan cara menghubungkannya ke node Anda sendiri, atau node publik. Anda harus mengikuti panduan ini:

- Pasang Bitcoin Core (https://armantheparman.com/bitcoincore/)

- Pasang Sparrow Bitcoin Wallet (https://armantheparman.com/download-sparrow/)

- Hubungkan Sparrow Bitcoin Wallet ke Bitcoin Core (https://armantheparman.com/sparrowcore/)

Sebagai alternatif menggunakan Sparrow Bitcoin Wallet adalah Electrum Desktop Wallet, tapi saya akan melanjutkan menjelaskan Sparrow Bitcoin Wallet karena saya menilai itu yang terbaik untuk kebanyakan orang. Pengguna lanjutan mungkin suka menggunakan Electrum sebagai alternatif.

Kita sekarang akan memuatnya dan menghubungkan Ledger, dengan dompet yang mengandung passphrase. Dompet ini tidak pernah terpapar ke Ledger Live karena dibuat SETELAH kita menghubungkan perangkat ke Ledger Live. Pastikan Anda tidak pernah menghubungkannya ke Ledger Live lagi untuk tidak memaparkan dompet pribadi baru Anda.

Buat Dompet Baru:

![image](assets/14.webp)

Namai dengan sesuatu yang cantik

![image](assets/15.webp)

Perhatikan kotak centang, "Has existing transaction". Jika ini adalah dompet yang telah Anda gunakan sebelumnya, maka centang kotak ini, jika tidak saldo Anda akan salah ditampilkan sebagai nol. Mencentang kotak ini meminta Sparrow untuk memeriksa database Bitcoin Core (blockchain) untuk transaksi sebelumnya. Untuk panduan ini, kita menggunakan dompet baru, jadi Anda dapat meninggalkan kotak tidak dicentang.

![image](assets/16.webp)

Klik pada "Connected Hardware Wallet" dan pastikan perangkat benar-benar terhubung, dinyalakan, PIN dimasukkan, dan Anda telah memasuki Aplikasi Bitcoin.

![image](assets/17.webp)

Klik "Scan" dan kemudian "Import Keystore" di layar berikutnya.

![image](assets/18.webp)

Tidak ada yang perlu diedit di layar berikutnya, Ledger telah mengisinya untuk Anda. Klik "Apply"

![image](assets/19.webp)
Layar berikutnya memungkinkan Anda untuk menambahkan kata sandi. Jangan keliru dengan "frasa sandi"; banyak orang akan melakukannya. Penamaannya tidak beruntung. Kata sandi memungkinkan Anda untuk mengunci dompet ini di komputer Anda. Ini spesifik untuk perangkat lunak ini di komputer ini. Ini bukan bagian dari kunci pribadi Bitcoin Anda.
![image](assets/20.webp)

Setelah jeda, sementara komputer berpikir, Anda akan melihat tombol di sebelah kiri berubah dari abu-abu menjadi biru. Selamat, dompet Anda sekarang siap digunakan. Buat dan kirim transaksi sesuka hati Anda.

![image](assets/21.webp)

## Menerima

Untuk menerima beberapa bitcoin, pergi ke tab Alamat di sebelah kiri dan pilih salah satu alamat untuk menerima. Cukup klik kanan alamat yang Anda inginkan, dan pilih "salin alamat". Kemudian pergi ke bursa tempat uang dikirim dari dan tempelkan di sana. Atau Anda dapat memberikan alamat tersebut kepada pelanggan yang dapat menggunakannya untuk membayar Anda.

Ketika Anda menggunakan dompet untuk pertama kalinya, Anda harus menerima jumlah yang sangat kecil, berlatih mengirimkannya ke alamat lain, baik di dalam dompet atau kembali ke bursa, untuk membuktikan bahwa dompet berfungsi seperti yang diharapkan.

Setelah Anda melakukan itu, Anda harus mencadangkan kata-kata yang Anda tulis. Satu salinan saja tidak cukup. Miliki setidaknya dua salinan kertas (logam lebih baik), dan simpan di dua lokasi yang berbeda dan aman. Ini mengurangi risiko bencana alam menghancurkan HWW dan cadangan kertas Anda dalam satu insiden. Lihat "Menggunakan Dompet Perangkat Keras Bitcoin" untuk diskusi lengkap tentang ini.

## Mengirim

![image](assets/22.webp)

Saat melakukan pembayaran, Anda perlu menempelkan alamat yang Anda bayar di bidang "Bayar ke". Anda sebenarnya tidak bisa meninggalkan Label kosong, itu hanya untuk catatan dompet Anda sendiri, tetapi Sparrow tidak mengizinkannya - cukup masukkan sesuatu (hanya Anda yang akan melihatnya). Masukkan jumlah dan Anda juga dapat secara manual menyesuaikan biaya yang Anda inginkan.

Dompet tidak dapat menandatangani transaksi kecuali HWW terhubung. Itulah tugas HWW - untuk menerima transaksi, menandatanganinya, dan mengembalikannya, sudah ditandatangani. Pastikan saat Anda menandatangani di perangkat, Anda secara visual memeriksa alamat yang Anda bayar sama di perangkat dan di layar komputer, dan faktur yang Anda terima (misalnya Anda mungkin telah menerima email untuk membayar alamat tertentu).

Perhatikan juga jika Anda memilih untuk menggunakan koin yang lebih besar dari jumlah pembayaran, maka sisanya akan dikirim kembali ke salah satu alamat perubahan dompet Anda. Beberapa orang tidak mengetahui hal ini, dan melihat transaksi mereka di blockchain publik, dan berpikir bahwa beberapa bitcoin dikirim ke alamat penyerang, tetapi sebenarnya, itu adalah alamat perubahan mereka sendiri.

## Firmware

Untuk memperbarui firmware, Anda perlu terhubung ke Ledger Live. Jika Anda ingin melakukan ini, Anda harus menghapus perangkat terlebih dahulu, dan pastikan Anda memiliki kata-kata cadangan dan frasa sandi Anda tersedia untuk mengembalikan perangkat. Alasan saya lebih suka menghapus perangkat terlebih dahulu adalah bahwa Anda harus menghubungkan perangkat Anda ke Ledger Live untuk memperbarui firmware, dan saya lebih suka tidak memaparkan dompet baru Anda (yang dengan frasa sandi) ke Ledger Live, sama sekali. Saya hanya tidak percaya Ledger tidak mengekstrak informasi kunci publik saya dari perangkat saat saya terhubung ke Ledger Live. Mereka mengklaim mereka tidak melakukannya, tetapi saya tidak dapat memverifikasi itu sendiri kecuali saya membaca kode, dan memahami perangkat keras internal juga.

## Kesimpulan
Artikel ini menunjukkan kepada Anda cara menggunakan Ledger HWW dengan cara yang lebih aman dan lebih privat daripada yang diiklankan - tetapi artikel ini saja tidak cukup. Seperti yang saya katakan di awal, Anda harus menggabungkannya dengan informasi yang disediakan dalam "Menggunakan Dompet Perangkat Keras Bitcoin". Tips:

Alamat Lightning Statis: dandysack84@walletofsatoshi.com
https://armantheparman.com/ledgersparrow/

Untuk mendalami topik ini lebih lanjut dan memperkuat keamanan dompet Anda di Ledger Nano dengan passphrase BIP39, saya mengundang Anda untuk memeriksa tutorial lengkap ini:

https://planb.network/tutorials/wallet/backup/passphrase-ledger-9ae6d9a2-7293-438a-8fe0-e59147ef2f49


