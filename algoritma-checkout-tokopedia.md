# Algoritma Checkout Tokopedia

## Deskriptif
1. Start
2. Carilah barang yang akan dibeli di Tokopedia
3. Lalu pilih lah produk yang akan dibeli di Tokopedia
4. Sesuaikan dengan ukuran dan warna barang yang akan dibeli
5. Jika spesifikasi yang ingin dibeli tidak ada, maka cari dari toko lain
6. Jika barang yang diinginkan sesuai dengan spesifikasi, Masukan keranjang untuk barang yang akan dibeli
7. Masukan keranjang terhadap barang yang sudah sesuai dengan spesifikasi
8. Jika barang lebih dari 1 maka kalikan jumlah barang dengan harga barang
8. Pilih metode pembayaran yang akan digunakan
9. Jika user membayar melalui gopay, maka akan di arahkan ke aplikasi gopay untuk melakukan pembayaran
10. Jika pada saat di gopay saldo nasabah tidak cukup maka pembayaran gagal
11. Jika berhasil maka akan muncul pembayaran sukses
12. Jika user membayar melalui virtual account bank maka akan diberikan kode pembayaran 
13. Jika kode pembayaran tersebut belum dibayarkan sesuai dari waktu yang ditentukan maka pembayaran gagal
14. Jika kode pembayaran tersebut dibayarkan sesuai dari waktu yang ditentukan maka pembayaran berhasil
15. Finish

## Flowchart

```mermaid
flowchart TD
idStart(("Start"))
idInput[/"Input: Barang, Harga, jumlahBarang"/]
idCariBarang["Cari Barang"]
idKondisi1{Barang = true && Harga = true}
kondisi1True["Masukan Keranjang"]
kondisi1False[/Output: Carilah Toko Lain/]
idKondisi2{jumlahBarang > 1}
kondisi2True["totalHarga = jumlahBarang * Harga"]
kondisi2False["totalHarga = 1 * hargaBarang"]
idProses["Lakukan Checkout"]
idPilihMetodePembayaran["Pilih Metode Pembayaran"]
idKondisi3{metodePembayaran != Gopay}
kondisi3True["Gunakan Virtual Akun"]
kondisi3False["Masuk Aplikasi Gopay"]
idKondisi4{"Pembayaran > Waktu Bayar"}
kondisi4True[/"Output: Pembayaran Gagal"/]
kondisi4False[/"Output: Pembayaran Berhasil"/]
idMasukanBank["Buka aplikasi Bank"]
idLakukanPembayaran1["Lakukan Pembayaran"]
idLakukanPembayaran2["Lakukan Pembayaran"]
idKondisi5{"Pembayaran > Waktu Bayar"}
idKondisi5True[/"Output: Pembayaran Gagal"/]
idKondisi5False[/"Output: Pembayaran Berhasil"/]
idStop(((Stop)))


idStart --> idInput --> idCariBarang --> idKondisi1
idKondisi1 -- True --> kondisi1True
idKondisi1 -- False --> kondisi1False
kondisi1True --> idKondisi2
idKondisi2 -- True --> kondisi2True
idKondisi2 -- False --> kondisi2False
kondisi2True --> idProses
kondisi2False --> idProses
idProses --> idPilihMetodePembayaran
idPilihMetodePembayaran --> idKondisi3
idKondisi3 -- True --> kondisi3True
idKondisi3 -- False --> kondisi3False
kondisi3False --> idLakukanPembayaran2 --> idKondisi4
idKondisi4 -- True --> kondisi4True
idKondisi4 -- False --> kondisi4False
kondisi3True --> idMasukanBank --> idLakukanPembayaran1 --> idKondisi5
idKondisi5 -- True --> idKondisi5True
idKondisi5 -- False --> idKondisi5False
kondisi1False --> idStop
kondisi4True --> idStop
kondisi4False --> idStop
idKondisi5True --> idStop
idKondisi5False --> idStop
```