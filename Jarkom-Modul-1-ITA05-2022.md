# Jarkom-Modul-1-ITA05-2022

---

| Nama                            |    NRP     |
| ------------------------------- | :--------: |
| Muhammad Hanif Fatihurrizqi     | 5027201068 |
| Abadila Barasmara Bias Dewandra | 5027201052 |
| Fadly Rachman Drajad Julianton  | 5027201038 |

## 1

Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!

1. Lakukan filter http:
   ![Filter nomor 1](/images/image1.png)
2. Kemudian lakukan follow stream, yakni http stream. Bisa dilihat Host: monta.if.its.ac.id melalukan request GET, lalu memiliki balasan di bawahnya dengan server **nginx/1.10.3**
   ![Hasil follow dan GET](/images/image9.png)

## 2

Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?

1. Pada soal ini kita diarahkan untuk menemukan hasil telusur dari ishaq saat menggunak keyword “detail topik”. Untuk mencari hasil telusurnya, kita filter string dari keyword tersebut dengan `http.request.uri contains "/detail"` . Hasilnya diperoleh:
   ![Hasil Filter nomor 2](/images/image18.png)
2. Setelah itu kita menuju ke web http://monta.if.its.ac.id/index.php/topik/detailTopik/194 yang memiliki tampilan berikut:
   ![Topik Tugas Akhir](/images/image13.png)
3. Sehingga topik tugas akhir yang dicari Ishaq adalah **Evaluasi unjuk kerja User Space Filesystem (FUSE)** .

## 3

Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!

`udp.dstport == 80 || tcp.dstport == 80`
![menuju port 80](/images/image16.png)

## 4

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

`udp.srcport == 21 || tcp.srcport == 21`
![dari port 21](/images/image4.png)

## 5

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

`udp.srcport == 443 || tcp.srcport == 443`
![dari port 43](/images/image11.png)

## 6

Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !

1. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !
   Ping lipi.go.id untuk medapakan ip address
   ![ip lipi](/images/image6.png)
2. Lalu lakukan filter ip pada wireshark:
   `ip.dst == 203.160.128.158`
   ![dari lipi.go.id](/images/image2.png)

## 7

Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

1. Untuk mendapatkan ip addres kita, kita bisa lakukan request ke web, lalu filter HTTP pada wireshark:
   ![ping self](/images/image8.png)
2. Dan bisa melihat ip address kita (ip asal)
   ![my ip](/images/image3.png)
3. Maka lakukan filter dari ip kita dengan:
   `ip.src == 192.168.0.107`
   ![menuju port 80](/images/image17.png)

## 8

Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

1. Untuk menemukan percakapan yang dilakukan pada protokol TCP
   ![TCP filter](/images/image7.png)
2. kita melakukan follow ke TCP stream. Bisa dilihat `TCP stream` pada 12. 29, 41, dan 90 memiliki percakapan, dengan ke-29 bernilai salt yang digunakan untuk soal selanjutnya.
   ![talk 1](/images/image15.png)
   ![talk 1](/images/image12.png)
   ![talk 1](/images/image14.png)
   ![salt](/images/image10.png)

## 9

Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.

Untuk mendapatkan file des3 kita menggunakan filter `tcp stream eq 29` dan men save as
dengan format ITA05.des3 kemudian kami jalankan

```bash
openssl des3 -d -salt -in ITA05.des3 -out flag.txt -k nakano
```

dimana input file adalah adalah ITA05 dan output file adalah flag.txt
![openssl](/images/image5.png)

## 10

Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

menggunakan syntax

```bash
cat flag.txt
```

Hasil sudah ada di soal no 9
