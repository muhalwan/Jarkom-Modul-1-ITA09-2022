# Jarkom-Modul-1-ITA09-2022

1. Pertama buka .pcapng soal 1-2 dan masukkan http ke display filter

Kemudian klik kanan dan pilih opsi follow menggunakan protokol http

Gunakan find dan cari kata server dan akan ditemukan bahwa website menggunakan website nginx/1.10.3


2. Sesuai dengan hint dari soal, coba masukan http.request.uri contains "/detail"  ke .pcappng yang disediakan di gdrive

Akan didapatkan suatu string yang mengarah ke url dari website http://monta.if.its.ac.id/. Buka salah satu dari berita yang ada agar mendapatkan format urlnya, yaitu http://monta.if.its.ac.id/index.php/topik/detailTopik/194


3. tcp.dstport == 80 dan udp.dstport == 80

4. tcp.srcport == 21 dan udp.srcport == 21

5. tcp.srcport == 443 dan udp.srcport == 443

6. Pertama lakukan ping ke lipi.go.id untuk mendapatkan ipnya 

Kemudian masukkan ip.dst == 203.160.128.158 ke display filter

7. Pertama, run command ipconfig di command prompt 

Kemudian masukkan ip.addr == 10.15.40.69 di display filter dari koneksi yang anda gunakan

8. Kita coba memberikan filter ip.src == 127.0.0.1 dan mendapatkan informasi berupa clue password dan port yaitu 9002

9. Setelah port diketahui kita coba filter dengan tcp.dstport == 9002 lalu kita akan mendapatkan data salted nya

Kita simpan dengan format ITA09.des
Lalu kita decrypt file salted tersebut dengan openssl menggunakan metode des3
Dengan command openssl des3 -d -in ITA09.des -out flag.txt

Disini kita memerlukan password untuk mendecrypt, kita memerlukan petunjuk lain dari capture wireshark.

Dari sini, cluenya adalah kesamaan, berdasarkan anime kembar lima tersebut yang sama adalah orang tua mereka atau keluarga jadi passwordnya mungkin “nakano” saat dicoba berhasil.

10. Flag: JaRkOm2022{8uK4N_CtF_k0k_h3h3h3}

