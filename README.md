1. Pertama buka .pcapng soal 1-2 dan masukkan http ke display filter

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Kemudian klik kanan dan pilih opsi follow menggunakan protokol http

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Gunakan find dan cari kata server dan akan ditemukan bahwa website menggunakan website nginx/1.10.3

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.002.png)


2. Sesuai dengan hint dari soal, coba masukan http.request.uri contains "/detail"  ke .pcappng yang disediakan di gdrive

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

Akan didapatkan suatu string yang mengarah ke url dari website <http://monta.if.its.ac.id/>. Buka salah satu dari berita yang ada agar mendapatkan format urlnya, yaitu <http://monta.if.its.ac.id/index.php/topik/detailTopik/194>

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.003.png)


3. tcp.dstport == 80 dan udp.dstport == 80

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)


4. tcp.srcport == 21 dan udp.srcport == 21

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)


5. tcp.srcport == 443 dan udp.srcport == 443

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)


6. Pertama lakukan ping ke lipi.go.id untuk mendapatkan ipnya 

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.004.png)

Kemudian masukkan ip.dst == 203.160.128.158 ke display filter

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)


7.  Pertama, run command ipconfig di command prompt 

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.005.png)

Kemudian masukkan ip.addr == 10.15.40.69 di display filter dari koneksi yang anda gunakan

![](Aspose.Words.95029e30-4cf8-431f-be7f-f10787143d51.001.png)


8. Untuk mencari clue-clue tentang percakapan mereka, kita pertama menerapkan display filter yaitu data contains jawaban, disini kita akan mencari paket yang memiliki data berupa jawaban karena mereka sedang membicarakan tentang jawaban soal shift.  Lalu, pada TCP Stream dari filter yang telah diterapkan kita mendapatkan clue-clue berupa: enkripsi dengan openssl metode des3, terdapat file salted, komunikasi lewat tcp port 9002, dan password file adalah nama karakter anime kembar lima.  

![image](https://user-images.githubusercontent.com/73457972/191682610-715c9f1a-1b10-425f-aafe-f20892805254.png)

![image](https://user-images.githubusercontent.com/73457972/191682642-2284645c-18be-46cb-a007-df26dbc1136a.png)

 
9. Dari clue yang telah didapatkan kita mengetahui bahwa file salt yang mereka kirim menggunakan tcp port 9002 kita akan menerapkan display filter berupa tcp.port == 9002 karena mereka saling komunikasi keluar-masuk lewat port 9002 tersebut. Setelah kita dapatkan data saltnya kita akan save raw dengan nama ITA09.des3.

![image](https://user-images.githubusercontent.com/73457972/191682717-a0676307-092e-4061-bca7-b517ef4178bc.png)

![image](https://user-images.githubusercontent.com/73457972/191682736-e4a46fef-5bfe-49fe-899b-e2e2276f3c0e.png)


10. Berdasarkan clue dari nomor 8 kita mengetahui bahwa enkripsi tersebut menggunakan openssl dengan metode des3, kita bisa mengenkripsinya dengan command openssl des3 -d -in ITA09.des3 -out flag.txt.

![image](https://user-images.githubusercontent.com/73457972/191682829-79c66533-68ff-4b4f-85b1-cecedda240ad.png)

Tetapi kita masih belum tahu password dari enkripsi tersebut. Kita akan mencari clue lain dari paket pcapng dengan filter data contains password. Lalu, kita mendapatkan clue tambahan bahwa “passwordnya bisa jadi kesamaan diantara kita” dari sini berdasarkan clue pertama nama karakter yang memiliki kesamaan di anime kembar lima adalah nama “nakano” yang merupakan nama kembar lima tersebut. Setelah memasukkan password tersebut kita berhasil mendapatkan flagnya “JaRkOm2022{8uK4N_CtF_k0k_h3h3h3}”

![image](https://user-images.githubusercontent.com/73457972/191682857-daeaf318-f924-4035-84ca-7e4251ae0c80.png)

![image](https://user-images.githubusercontent.com/73457972/191682868-5960c9ce-8985-4356-b366-1541a08074d2.png)
