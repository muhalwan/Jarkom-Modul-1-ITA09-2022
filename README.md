\1. Pertama buka .pcapng soal 1-2 dan masukkan http ke display filter

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Kemudian klik kanan dan pilih opsi follow menggunakan protokol http

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Gunakan find dan cari kata server dan akan ditemukan bahwa website menggunakan website nginx/1.10.3

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.002.png)

\2. Sesuai dengan hint dari soal, coba masukan http.request.uri contains "/detail"  ke .pcappng yang disediakan di gdrive

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Akan didapatkan suatu string yang mengarah ke url dari website <http://monta.if.its.ac.id/>. Buka salah satu dari berita yang ada agar mendapatkan format urlnya, yaitu <http://monta.if.its.ac.id/index.php/topik/detailTopik/194>

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.003.png)

\3. tcp.dstport == 80 dan udp.dstport == 80

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)






\4. tcp.srcport == 21 dan udp.srcport == 21

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)






\5. tcp.srcport == 443 dan udp.srcport == 443

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)






\6. Pertama lakukan ping ke lipi.go.id untuk mendapatkan ipnya 

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.004.png)

Kemudian masukkan ip.dst == 203.160.128.158 ke display filter

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)






\7.  Pertama, run command ipconfig di command prompt 

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.005.png)

Kemudian masukkan ip.addr == 10.15.40.69 di display filter dari koneksi yang anda gunakan

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)






\8. Kita coba memberikan filter ip.src == 127.0.0.1 dan mendapatkan informasi berupa clue password dan port yaitu 9002

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.006.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.007.png)

\9. Setelah port diketahui kita coba filter dengan tcp.dstport == 9002 lalu kita akan mendapatkan data salted nya

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.008.png)![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.009.png)

Kita simpan dengan format ITA09.des

Lalu kita decrypt file salted tersebut dengan openssl menggunakan metode des3

Dengan command openssl des3 -d -in ITA09.des -out flag.txt

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.010.png)

Disini kita memerlukan password untuk mendecrypt, kita memerlukan petunjuk lain dari capture wireshark.

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.011.png)

Dari sini, cluenya adalah kesamaan, berdasarkan anime kembar lima tersebut yang sama adalah orang tua mereka atau keluarga jadi passwordnya mungkin “nakano” saat dicoba berhasil.

\10. Flag: JaRkOm2022{8uK4N\_CtF\_k0k\_h3h3h3}

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.010.png)
