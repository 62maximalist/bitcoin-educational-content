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


## Tambahkan passphrase
Kini setelah kita memiliki Aplikasi Bitcoin, kita dapat menambahkan passphrase ke seed phrase kita. Kita tidak bisa melakukan itu sebelumnya ketika seed pertama kali dibuat karena pada awalnya, kita tidak memiliki Aplikasi Bitcoin, dan kita perlu terhubung ke Ledger Live untuk mendapatkannya.

Pergi ke menu "settings" di dalam perangkat, kemudian submenu "security". Kemudian pilih passphrase. Kamu akan melihat "Advanced feature". Klik tombol kanan, kamu akan melihat "read manual..." dan kemudian setelah klik tombol kanan lagi, kamu akan melihat "back". Tapi itu bukan akhirnya. Secara intuitif, kamu mungkin berpikir itu sudah selesai, tapi klik tombol kanan lagi. kamu akan melihat "set up passphrase".

Kamu dapat pilih untuk "attach to PIN" atau "Set temporarily". Kalau aku merekomendasikan "attach to the PIN". Dengan cara itu, kamu dapat mengakses dompet yang berbeda tergantung pada PIN yang Anda masukkan ketika pertama kali menyalakan perangkat. Jika kamu pilih "set temporarily", kamu harus memasukkan passphrase setiap kali Anda ingin mengakses dompet tersebut, tapi itu selalu dari PIN default.

Masukkan passphrase dan konfirmasikan.

Ini akan meminta Anda untuk "Current PIN". Ini bukan PIN yang kamu asosiasikan dengan passphrase baru. Ini adalah PIN yang kamu masukkan ketika Anda menyalakan perangkat untuk sesi ini.

Nah, sekarang kamu dapat keluar ke menu utama dengan memilih opsi kembali beberapa kali.

## Mengawasi Dompet

Dalam artikel sebelumnya, aku pernah menjelaskan cara mengunduh dan memverifikasi Sparrow wallet, dan cara menghubungkannya ke node milikmu sendiri, atau node publik. Kamu harus mengikuti panduan ini:

- Pasang Bitcoin Core (https://armantheparman.com/bitcoincore/)

- Pasang Sparrow Bitcoin Wallet (https://armantheparman.com/download-sparrow/)

- Hubungkan Sparrow Bitcoin Wallet ke Bitcoin Core (https://armantheparman.com/sparrowcore/)

Pilihan selain Sparrow Bitcoin Wallet yang bisa kamu jadikan pilihan adalah Electrum Desktop Wallet, tapi kamu akan melanjutkan menjelaskan Sparrow Bitcoin Wallet karena kita menilai itu yang terbaik untuk kebanyakan orang. Pengguna lanjutan mungkin suka menggunakan Electrum sebagai alternatif.

Kita sekarang akan memuatnya dan menghubungkan Ledger, dengan dompet yang mengandung passphrase. Dompet ini tidak pernah terpapar ke Ledger Live karena dibuat SETELAH kita menghubungkan perangkat ke Ledger Live. Pastikan kamu tidak pernah menghubungkannya ke Ledger Live lagi untuk tidak memaparkan dompet pribadi barumu.

Buat Dompet Baru:

![image](assets/14.webp)

Namai dengan sesuatu yang cantik

![image](assets/15.webp)

Perhatikan kotak centang, "Has existing transaction". Jika ini adalah dompet yang telah kamu gunakan sebelumnya, maka centang kotak ini, jika tidak saldo Anda akan salah ditampilkan sebagai nol. Mencentang kotak ini meminta Sparrow untuk memeriksa database Bitcoin Core (blockchain) untuk transaksi sebelumnya. Untuk panduan ini, kita menggunakan dompet baru, jadi kamu dapat meninggalkan kotak tidak dicentang.

![image](assets/16.webp)

Klik pada "Connected Hardware Wallet" dan pastikan perangkat benar-benar terhubung, dinyalakan, PIN dimasukkan, dan kamu telah memasuki Aplikasi Bitcoin.

![image](assets/17.webp)

Klik "Scan" dan kemudian "Import Keystore" di layar berikutnya.

![image](assets/18.webp)

Tidak ada yang perlu diedit di layar berikutnya, Ledger telah mengisinya untuk kamu. Klik "Apply"

![image](assets/19.webp)
Layar berikutnya memungkinkan kamu untuk menambahkan kata sandi. Jangan keliru dengan "frasa sandi"; banyak orang akan melakukannya. Penamaannya tidak beruntung. Kata sandi memungkinkan kamu untuk mengunci dompet ini di komputermu. Ini spesifik untuk perangkat lunak ini di komputer ini. Ini bukan bagian dari kunci pribadi Bitcoin kamu.
![image](assets/20.webp)

Setelah jeda, sementara komputer berpikir, kamu akan melihat tombol di sebelah kiri berubah dari abu-abu menjadi biru. Selamat, dompetmu sekarang siap digunakan. Sekarang kamu bisa melakukan transaksi sesuka hati.

![image](assets/21.webp)

## Menerima

Untuk menerima Bitcoin, kamu tinggal buka tab Alamat di sebelah kiri, lalu pilih salah satu alamat yang tersedia. Klik kanan alamat tersebut dan pilih "Salin Alamat". Setelah itu, tempel alamat itu di bursa tempat kamu akan mengirim Bitcoin, atau kasih langsung ke orang yang mau bayar kamu.

Saat pertama kali pakai dompet, sebaiknya coba terima sedikit Bitcoin dulu, lalu kirimkan ke alamat lain — entah ke alamat lain di dompet yang sama atau balik lagi ke bursa untuk memastikan dompetnya benar-benar berfungsi seperti seharusnya.

Setelah menulis kata-kata cadangan (seed phrase), pastikan kamu mencadangkannya. Satu salinan aja nggak cukup buat minimal dua salinan di kertas (atau logam, kalau mau lebih aman), dan simpan di dua tempat yang berbeda dan aman. Ini buat jaga-jaga kalau ada bencana yang bisa ngancurin dompet dan cadanganmu sekaligus. Untuk penjelasan lengkap, cek bagian "Menggunakan Dompet Perangkat Keras Bitcoin."

## Mengirim

![image](assets/22.webp)

Untuk mengirim Bitcoin, tempel alamat tujuan di kolom "Bayar ke", lalu isi kolom Label dengan catatan apa saja (karena kolom ini wajib diisi di Sparrow). Setelah itu, masukkan jumlah Bitcoin yang ingin kamu kirim, dan kalau mau, kamu juga bisa atur biaya transaksinya secara manual.


Dompet nggak bisa menandatangani transaksi kalau perangkat keras (HWW) belum terhubung. Tugas HWW adalah menerima transaksi, menandatanganinya, lalu mengirimkannya kembali dalam keadaan sudah ditandatangani. Saat kamu menandatangani, pastikan alamat tujuan yang muncul di perangkat sama persis dengan yang ada di layar komputer dan di faktur yang kamu terima (misalnya dari email).

Kalau kamu pakai koin yang nilainya lebih besar dari jumlah yang mau dikirim, sisanya akan otomatis dikirim balik ke salah satu alamat milik dompetmu sendiri (namanya alamat perubahan). Banyak orang nggak sadar soal ini, lalu panik waktu lihat di blockchain seolah-olah ada Bitcoin yang dikirim ke alamat asing padahal itu cuma balik ke alamat perubahan mereka sendiri.

## Firmware

Kalau mau update firmware, kamu harus sambungin perangkat ke Ledger Live. Tapi sebelum itu, aku saranin kamu hapus dulu perangkatnya. Pastikan kamu udah nyimpen kata-kata cadangan (seed phrase) dan frasa sandi, biar nanti bisa dipulihkan lagi. Aku lebih milih hapus dulu karena untuk update, perangkat harus terhubung ke Ledger Live, dan aku nggak mau dompet baruku (yang pakai frasa sandi) terekspos ke Ledger Live sama sekali. Aku pribadi kurang percaya Ledger 100%, walaupun mereka bilang nggak ngambil info kunci publik dari perangkat. Tapi aku juga nggak bisa buktiin itu, kecuali kalau aku bisa baca kodenya dan ngerti perangkat kerasnya.

## Kesimpulan
Artikel ini menunjukkan kepada kita cara menggunakan Ledger HWW dengan cara yang lebih aman dan lebih privat daripada yang diiklankan - tetapi artikel ini saja tidak cukup. Seperti yang kami katakan di awal, kamu harus menggabungkannya dengan informasi yang disediakan dalam "Menggunakan Dompet Perangkat Keras Bitcoin". Tips:

Alamat Lightning Statis: dandysack84@walletofsatoshi.com
https://armantheparman.com/ledgersparrow/

Untuk mendalami topik ini lebih lanjut dan memperkuat keamanan dompetmu di Ledger Nano dengan passphrase BIP39, kalian bisa cek tutorial lengkap ini:

https://planb.network/tutorials/wallet/backup/passphrase-ledger-9ae6d9a2-7293-438a-8fe0-e59147ef2f49


