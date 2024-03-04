# Tugas Matkul Digital Forensik
Hai, saya Andika. Disini, saya ingin membagikan pengalaman latihan autopsy. 
Adapun langkah-langkahnya sebagai berikut :

## Download Aplikasi Autopsy dan HxD
* Link Autopsy : [https://www.autopsy.com/download/]
* Link HxD : [https://mh-nexus.de/en/hxd/]

## Membuat Folder Case
Disini, saya meletakkan file dan folder suspect di local drive D. 
Didalamnya, saya membuat folder "001-H-jij-XX" dimana 001 merupakan nomor kasus, H merupakan sebuah tag atau semacam indikator jenis investigasi, jij merupakan tag penyelidik, dan XX merupakan inisial anggota penyelidik. 

![1](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/6647349c-b5c9-4605-b1e0-a37cc35ff02c)
![2](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/46eea4ae-3593-40f0-8d4d-646b660f0f8a)

## Membuat Sub Folder 001-H-jij-XX
Saya membuat beberapa sub folder yang terdiri dari Autopsy, Docs, Image, Reports, dan temp. 

![3](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/e8b83bbd-b876-4242-ba84-cefc1f2a715d) 

## Membuat Dokumen Teks 001-H-jij-XX-docs.txt
Saya membuat dokumen teksnya berada di dalam folder Docs sebelumnya. Dengan adanya file ini, saya dapat membuat dokumentasi berupa catatan waktu dan riwayat aktifitas. Adapun untuk memasukkan keterangan waktu, bisa dilakukan dengan klik F5. 

![4](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/b1d38a7a-aea1-4f78-aa1a-3973c64006dd)
![5](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/25ccb63c-b335-4475-acbd-e74fd6a1e66d)

## Membuat File Exhibit001 & Menambahkan File SuspectData.dd
Saya membuat file tersebut berada di dalam folder Image sebelumnya. 

![6](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/54754f1f-c046-49bc-99c2-249527cb219d)

Setelah itu, ditambahkan file SuspectData.dd yang didapat dari link youtube. 

![7](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/d8d7db9d-b47e-43a2-9b26-6e4ad56162d9)

## Buka aplikasi Autopsy
## Pilih new case
## Isi case information 

![8](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/75a405d2-2d44-4fca-af30-32fed46dbff5)

Disini, saya menggunakan nomor kasus untuk base directory agar siapapun yang membaca catatan ini, melihat bahwa catatan itu selalu berada di direktori yang sama. 

## Isi optional information 

![9](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/910ae850-acaf-4fa7-b051-44a173331aae)

Disini terdapat dua bagian yaitu Case dan Examiner dimana Case berisi nomor kasus dan Examiner berisi nama, no HP, email, dan organisasi analysis. Khusus pada bagian organisasi analysis, perlu juga untuk ditambahkan organisasi terlebih dahulu dengan klik Manage Organization. 

## Isi step

Setelah klik finish pada bagian sebelumnya. Kali ini, terdapat steps yang dimulai dengan.. 
* Select host name yaitu Exhibit001
* Select Data Source Type yaitu klik disk image or VM file
* Select Data Source yang terdiri dari path Image atau file yang dicurigai "SuspectData.dd", timezone wilayah yakni Asia Jakarta, dan hash value. Di bagian hash value ini terdapat value md5 dan SHA256 yang dimana bisa diperoleh dari mengetik command Get-FileHash pada Powershell.

![10](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/38171dca-868b-4554-ae31-240d2b9eff02)

* Configure Ingest yaitu semua pilihan dichecklist kecuali yang ada pada gambar berikut :

![Screenshot_20240304_231113](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/2f05b525-a807-4f45-a24d-b3cb7bae54c2)

* Setelah semua step dijalankan, data source saya tadi beserta komponen detailnya diproses pada bagian Add Data Source. 

## Melihat gambar dan raw data pada Exhibit001
Dalam data source Exhibit001, terdapat lagi direktori SuspectData.dd yang berisi gambar dan raw data. Setelah itu, klik sebuah image lalu pilih bagian hex dan klik launch in HxD untuk menginstall. 

![Screenshot_2024_0304_232229](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/98c213c6-e10f-4177-ad46-1c1f9f0853a0)

Setelah itu, kita dapat melihat tampilan detail dari sebuah file image yang dipilih

![IMG_20240304_233223](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/fc75a139-dc34-45d0-898d-1e4d401d1750) 

## Fitur Search
Saya mencoba untuk mencari gambar kucing dengan keyword CAT di kolom pencarian keyword search, maka akan keluar hasil beberapa images kucing seperti pada gambar berikut. 

![11](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/b5e8669b-02c9-435d-a04e-4401f86911e8) 

## Fitur History
Di aplikasi Autopsy, kita dapat melihat hal apa yang saya cari sebelumnya dengan cara mengakses menu Analysis Result -> keyword hits -> single literal keyword search pada sidebar. 
Sebagai contoh, disini tertulis cat(8) yang artinya keyword cat ini sudah pernah saya gunakan untuk mencari dan angka 8 maksudnya yaitu banyaknya jumlah images yang muncul sesuai dengan keyword yang dicari. 

![12](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/4a066f93-d364-4061-9023-f9be9525ff1b)

## Fitur Bookmark
Kita juga dapat menyimpan gambar yang kita sukai dengan fitur ini. Adapun tata caranya yaitu dengan klik sebuah image -> klik kanan -> Add File Tag -> Bookmark. 
Untuk dapat mengetahui gambar apa saja yang telah disimpan, kita dapat mengakses menu Tags -> Bookmark -> File Tags pada sidebar. 

![13](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/d4fd5bce-38d5-46c0-8bb6-5d16ba8e98c9) 

## Ekstrak File

![Screenshot_2024_0305_004242](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/2eb4f3d6-8dff-400e-b3c3-beda68a1e5ee) 

Gambar yang telah dibookmark dapat diekstrak agar bisa diunduh dalam perangkat. Adapun path yang saya tuju yakni folder Image sehingga setelah diekstrak, gambarnya akan tersimpan pada folder Image. 

## Generate Report
Klik menu Generate Report pada navbar, lalu klik pilihan HTML Report untuk memproses data yang dicurigai (SuspectData.dd).

![14](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/8286653a-059b-4c66-82bb-ce89088b2e1f)

## Configure Report
Klik pilihan Specific Tagged Results untuk data yang dilaporkan yang dapat melakukan hasil yang diberi tags tertentu lalu checklist bookmark dan finish. 

![15](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/7bc1f6bd-7fad-4e5b-b23f-da4e72f464ab)

## Link & Hasil laporan
Link ini berisi data yang telah ditandai, jika link ini diklik maka akan memperlihatkan file laporan yang berisikan perjalanan yang dimulai dari menyesuaikan kasus Autopsy dengan yang ada pada dokumentasi. Adapun pada sidebar, terdapat beberapa file yang diberi tags dan juga terdapat bookmark gambar kucing. Jadi, jika saya klik salah satu pilihan pada sidebar tersebut, maka saya dapat melihat file secara langsung sehingga terjadilah laporan untuk memudahkannya.

![16](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/d06546ed-7d45-4fe4-be46-3d3646afa5f3) 
![17](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/a38c39b2-33be-4326-8a93-52cdf51cf865) 

## Kesimpulan Percobaan

Jadi, kesimpulan yang saya dapat adalah setiap apa yang dilakukan pada aplikasi Autopsy, seperti edit, bookmark, add tag, dan remove maka akan masuk ke file folder

![18](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/4e128e3a-d0c3-4bdb-aec9-3284ae9f033b) 

Adapun hasil latihan yang telah saya lakukan, sebagai berikut :

![19](https://github.com/arianz/Autopsy-Exercise---1203210019/assets/55643185/11be393a-3c9d-4ed4-8429-14e8d820c3d4) 
