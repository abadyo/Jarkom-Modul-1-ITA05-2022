# Jarkom-Modul-1-ITA05-2022

---

| Nama        | NRP          | 
| ------------- |:-------------:|
| Muhammad Hanif Fatihurrizqi      | 5027201068 |
| Abadila Barasmara Bias Dewandra      | 5027201052      | 
| Fadly Rachman Drajad Julianton | 5027201038 | 

## 1
Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!

1. Lakukan filter http:
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
2. Kemudian lakukan follow stream, yakni http stream. Bisa dilihat Host: monta.if.its.ac.id melalukan request GET, lalu memiliki balasan di bawahnya dengan server **nginx/1.10.3**
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 2
Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?

1. Pada soal ini kita diarahkan untuk menemukan hasil telusur dari ishaq saat menggunak keyword “detail topik”. Untuk mencari hasil telusurnya, kita filter string dari keyword tersebut dengan `http.request.uri contains "/detail"` . Hasilnya diperoleh:
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
2. Setelah itu kita menuju ke web http://monta.if.its.ac.id/index.php/topik/detailTopik/194 yang memiliki tampilan berikut:
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
3. Sehingga topik tugas akhir yang dicari Ishaq adalah **Evaluasi unjuk kerja User Space Filesystem (FUSE)** .

## 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80! 

`udp.dstport == 80 || tcp.dstport == 80`
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 4
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

`udp.srcport == 21 || tcp.srcport == 21`
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 5
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

`udp.srcport == 443 || tcp.srcport == 443`
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 6
Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !

1. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !
Ping lipi.go.id untuk medapakan ip address
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
2. Lalu lakukan filter ip pada wireshark:
`ip.dst == 203.160.128.158`
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 7
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

1. Untuk mendapatkan ip addres kita, kita bisa lakukan request ke web, lalu filter HTTP pada wireshark:
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
2. Dan bisa melihat ip address kita (ip asal)
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
3. Maka lakukan filter dari ip kita dengan:
`ip.src == 192.168.0.107`
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 8
Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

1. Untuk menemukan percakapan yang dilakukan pada protokol TCP
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
2. kita melakukan follow ke TCP stream. Bisa dilihat `TCP stream` pada 12. 29, 41, dan 90 memiliki percakapan, dengan ke-29 bernilai salt yang digunakan untuk soal selanjutnya.
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 9
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.

Untuk mendapatkan file des3 kita menggunakan filter `tcp stream eq 29` dan men save as 
dengan format ITA05.des3 kemudian kami jalankan 
```bash
openssl des3 -d -salt -in ITA05.des3 -out flag.txt -k nakano 
```
dimana input file adalah adalah ITA05 dan output file adalah flag.txt
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

## 10
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

menggunakan syntax
```bash
cat flag.txt
```
hasilnya:
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")





