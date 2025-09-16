### $_$ - Post Test 2 PBO - $_$
--------------------------------------------------------------------------------------------

#### Disusun oleh:

Nama: Zahraturramadhani

NIM: 2409116014

Kelas: Sistem Informasi A'2024

--------------------------------------------------------------------------------------------


<h2 align="center">💵💸💹 Manajemen Catatan Keuangan Harian (Budget Tracker) 💰🪙💴 </h2> 

<h2 align="center">=================================================</h2> 
<h1 align="center">🛡️ POCKET GUARD 🛡️</h1>
<h2 align="center">=================================================</h2> 

### ~ 📗 Deskripsi Singkat 📒  ~

Program ini dibuat untuk membantu mencatat dan mengelola catatan keuangan harian. Aplikasinya bernama Pocket Guard, aplikasi Java sederhana berbasis console.

Di dalam program, setiap catatan keuangan dapat diisi lengkap dengan tanggal, keterangan singkat, jenis catatan (pemasukan atau pengeluaran), kategori (gaji, makan, transportasi, hiburan, belanja, tabungan,tagihan), metode pembayaran (cash, e-wallet, atau transfer), serta jumlah uang yang dikeluarkan atau diterima.

Aplikasi ini bisa menambah catatan baru, melihat seluruh daftar catatan, mengubah jika ada kekeliruan, atau menghapus catatan yang tidak diperlukan. Program juga dapat menampilkan ringkasan saldo (total pemasukan, total pengeluaran, dan selisihnya) sehingga kondisi keuangan mudah dipantau.

Tersedia pula fitur filter catatan berdasarkan jenis, kategori, dan metode pembayaran, serta fitur search berdasarkan keterangan yang keterangan tersebut diinputkan dalam menu tambah catatan keuangan. Selain itu, batas pengeluaran bulanan dapat ditetapkan, bila pengeluaran melewati batas, program akan menampilkan peringatan agar pengelolaan uang lebih terkendali.

Secara keseluruhan, Pocket Guard membantu melacak arus kas harian, menjaga keseimbangan keuangan, dan membiasakan pencatatan keuangan secara teratur.

### ~ Penjelasan Program  ~

1. Penjelasan 3 class
   
   <img width="416" height="181" alt="image" src="https://github.com/user-attachments/assets/e4f86337-d31c-4f65-a248-5c8884b513b9" />

> Pada program "Pocket Guard" ini terdapat 3 class, yaitu: App.Java, TransaksiService.Java, dan Transaksi.Java
>
> Pada struktur di atas, App.java di paket com.mycompany.posttest2pbo.main berperan sebagai titik masuk program sekaligus antarmuka teks sederhana dengan menampilkan menu utama dan meneruskan pilihan pengguna ke kelas layanan.
> 
> Seluruh logika bisnis ditempatkan di TransaksiService.java pada paket com.mycompany.posttest2pbo.service, mulai dari CRUD, ringkasan saldo, pengaturan batas pengeluaran, filter dan fitur search, sampai utilitas tampilan tabel serta validasi input. Khusus menu Ubah, input kosong (langsung Enter) dibiarkan untuk mempertahankan nilai lama, sedangkan pada tambah, filter, dan set batas, input kosong ditolak agar data tetap bersih.
> 
>  Data transaksi itu sendiri dimodelkan oleh Transaksi.java di paket com.mycompany.posttest2pbo.model, yang hanya berisi struktur atribut (id, tanggal, keterangan, jenis, kategori, metodePembayaran, jumlah) dengan modifier private, constructor untuk menginisialisasi objek, serta getter–setter public agar akses data tetap terkontrol. Alurnya sederhana: App memanggil TransaksiService, dan TransaksiService mengelola kumpulan objek Transaksi, sehingga pola MVC ringan terpenuhi dengan pemisahan paket sesuai fungsinya.

2. Penjelasan properties
   
   <img width="372" height="206" alt="image" src="https://github.com/user-attachments/assets/b15cf25f-1a5e-48a8-9637-d9dbe106175a" />

> Pada program "Pocket Guard" ini terdapat 6 properties yaitu: "id", "tanggal", "keterangan", "jenis", "kategori", "metode pembayaran", dan "jumlah"
>
> Pada kelas Transaksi, setiap baris private adalah properti/atribut data milik satu transaksi: id (int) sebagai identitas unik; tanggal (String) untuk waktu transaksi dengan format yyyy-mm-dd; keterangan untuk deskripsi singkat; jenis menandai Pemasukan atau Pengeluaran; kategori mengelompokkan seperti Gaji, Makan, Transportasi, dan lain-lain; metodePembayaran menyatakan Cash/E-Wallet/Transfer; dan jumlah (double) menyimpan nominal. Semua dibuat private untuk enkapsulasi agar akses dan perubahan dilakukan lewat getter–setter, sehingga data aman dan valid.

3. Penjelasan constructor
   
   <img width="766" height="225" alt="image" src="https://github.com/user-attachments/assets/c7cf604e-d6fe-4b73-8b39-a9a9b42530c9" />

> Konstruktor Transaksi(...) adalah metode khusus yang namanya sama dengan kelas dan tidak punya tipe kembalian; ia dieksekusi otomatis saat membuat objek baru. Parameter yang diterima (id, tanggal, keterangan, jenis, kategori, metodePembayaran, jumlah) dipetakan ke atribut objek melalui kata kunci this, sehingga this.id = id; artinya nilai parameter id dimasukkan ke properti id milik objek. Dengan pola ini, setiap objek Transaksi selalu terbentuk dalam keadaan sudah terisi data lengkap dan konsisten. Contoh pemakaian: new Transaksi(1, "2025-09-01", "Gaji Bulanan", "Pemasukan", "Gaji", "Transfer", 5000000); akan langsung menghasilkan catatan transaksi yang siap digunakan tanpa perlu set nilai satu per satu.

4. Penjelasan access modifier
   
   Berikut adalah beberapa access modifier yang saya gunakan pada program:
   
   a. Transaksi.Java

   <img width="1140" height="857" alt="image" src="https://github.com/user-attachments/assets/d1804ef8-1907-434f-9f06-1ca9a15236f4" />

   > Kelas Transaksi dideklarasikan public agar bisa dipakai lintas paket. Seluruh atribut id, tanggal, keterangan, jenis, kategori, metodePembayaran, dan jumlah bermodifier private untuk menerapkan enkapsulasi sehingga nilainya tidak bisa diubah langsung dari luar kelas. Nilai awal diisi melalui konstruktor public Transaksi(...), sedangkan akses dan perubahan data dilakukan lewat getter dan setter yang juga public. Dengan susunan ini, objek selalu dibuat dalam keadaan valid dan setiap perubahan melewati kontrol metode yang disediakan.

   b. TransaksiService.Java
   
   <img width="591" height="157" alt="image" src="https://github.com/user-attachments/assets/71db12a2-d9dc-4132-8d2b-278cface7d0e" />
   
   <img width="440" height="98" alt="image" src="https://github.com/user-attachments/assets/0d78466b-f13f-4a89-a387-b20c93da268e" />

   > TransaksiService dideklarasikan public supaya bisa dipanggil dari App meski berada di paket berbeda. Di dalam kelas ini, state seperti daftar dan input ditandai private agar tidak bisa diakses dari luar, dan diberi final supaya referensinya tidak diganti selama program berjalan; variabel kontrol seperti autoId dan batasPengeluaranBulanan juga private agar hanya logika di service yang boleh mengubahnya. Metode public void tambahCatatan() berfungsi sebagai antarmuka layanan yang dipanggil dari App, dan pola yang sama dipakai untuk operasi lain seperti lihat, ubah, hapus, ringkasan saldo, filter/search, set batas, hingga tampilkan tabel semuanya public karena menjadi API yang dipakai UI. Sementara itu, detail implementasi dan utilitas seperti tambahSeed, hitungTotalJenis, formatRupiah, findById, serta berbagai helper validasi input disembunyikan dengan private karena hanya digunakan secara internal. Dengan susunan ini, enkapsulasi terjaga: App cukup memanggil metode publik tanpa menyentuh data langsung, sedangkan data dan cara kerjanya tetap aman di dalam service.

   c. App.Java
   
    <img width="605" height="74" alt="image" src="https://github.com/user-attachments/assets/eaaf08f4-c297-40b9-a97f-4a7c09ef09bd" />

   > App dideklarasikan public agar bisa dijalankan dari luar paket, dan public static void main(String[] args) adalah titik masuk program di Java. Di dalamnya dibuat objek TransaksiService dengan new TransaksiService(); objek ini nanti dipakai untuk memanggil operasi publik seperti seed(), tambahCatatan(), lihatSemuaCatatan(), ubahCatatan(), hapusCatatan(), dan seterusnya melalui logika menu. Modifier public pada kelas dan method memastikan keduanya dapat dipanggil oleh runtime maupun kelas lain, sedangkan static pada main membuatnya bisa dieksekusi tanpa perlu membuat objek App.
    
6. Penjelasan packages, dengan memisahkan class berdasarkan fungsinya:
    - packages main > isinya adalah kode yang menyimpan menu user

      <img width="298" height="23" alt="image" src="https://github.com/user-attachments/assets/7db00e9f-91d9-4e3e-a1bf-13141128816d" />

    - packages service > menyimpan kode logika CRUD

      <img width="319" height="22" alt="image" src="https://github.com/user-attachments/assets/91e647ee-a680-4c26-bc18-29dfa9e0a33f" />

    - packages model > menyimpan struktur data seperti atribut dan constructor

      <img width="325" height="23" alt="image" src="https://github.com/user-attachments/assets/83dff364-4006-4a8d-af4e-e19c95fb479f" />

   > Struktur proyek dipisah ke tiga paket sesuai fungsinya. Paket com.mycompany.posttest2pbo.main menampung antarmuka konsol dan entry point aplikasi, yaitu kelas App yang menampilkan menu dan meneruskan pilihan pengguna. Paket com.mycompany.posttest2pbo.service berisi logika bisnis: seluruh operasi CRUD, validasi input, filter dan search, ringkasan saldo, pengaturan batas, serta utilitas tampilan tabel di sinilah proses data berlangsung tanpa bergantung pada UI. Paket com.mycompany.posttest2pbo.model menyimpan struktur data, yaitu kelas Transaksi dengan atribut, constructor, serta getter–setter. Pemisahan ini membuat kode rapi, mudah dirawat dan diuji, serta sesuai ketentuan tugas tentang packages berdasarkan fungsi.

7. Penjelasan penerapan MVC
   
> 1. com.mycompany.posttest2pbo.model
Berisi Model aplikasi, yaitu kelas Transaksi. Kelas ini menyimpan struktur data transaksi: seluruh atribut dibuat private (enkapsulasi), ada constructor untuk inisialisasi saat objek dibuat, serta getter–setter public untuk akses terkontrol. Paket ini tidak berisi logika bisnis murni representasi data.
>
> 2. com.mycompany.posttest2pbo.service
Berisi Controller/Service yang mengeksekusi logika bisnis. Kelas TransaksiService mengelola daftar Transaksi (CRUD lengkap), validasi input, filter dan search, ringkasan saldo, pengaturan batas pengeluaran, serta utilitas tampilan tabel. Metode yang dipakai UI bersifat public (misal tambahCatatan, lihatSemuaCatatan, ubahCatatan, hapusCatatan, menuFilter, ringkasanSaldo, setBatasPengeluaran), sedangkan helper dan utilitas disembunyikan sebagai private.
>
> 3. com.mycompany.posttest2pbo.main
Berisi View/entry point aplikasi. Kelas App menampilkan menu konsol dan menangani interaksi pengguna, lalu memanggil metode publik pada TransaksiService. Di sinilah program dimulai melalui public static void main(String[] args) yang membuat instance service dan menjalankan alur menu.
>
> Alur singkat
Pengguna berinteraksi lewat App → App memanggil metode di TransaksiService → TransaksiService membuat/mengubah/membaca objek Transaksi di model dan mengembalikan hasil ke UI. Struktur ini memenuhi MVC sederhana dan memisahkan tanggung jawab dengan jelas.

### ~ Penjelasan Alur Program (Output Program)  ~

<h1 align="center"><img width="369" height="306" alt="image" src="https://github.com/user-attachments/assets/9aaa0cd6-68b4-4dd0-903c-988aa4aedf47" /></h1>


> Saat program dijalankan, muncul pesan pembuka “SELAMAT DATANG DI POCKET GUARD – Aplikasi Catatan Keuangan Harian Anda”. Setelah itu tampil Menu Utama berisi pilihan untuk menambah catatan, melihat daftar catatan, mengubah atau menghapus catatan, menampilkan ringkasan saldo, memfilter catatan (berdasarkan jenis, kategori, atau metode pembayaran) dan searching berdasarkan keterangan, menetapkan batas pengeluaran bulanan, serta opsi keluar untuk mengakhiri program.
>
> ### ✨ Penjelasan Masing-Masing Menu ✨
> 
> 1. Tambah Catatan Keuangan
>    
>    Menu ini digunakan untuk menambahkan catatan keuangan baru. Data yang dimasukkan meliputi tanggal, keterangan, jenis (pemasukan/pengeluaran), kategori, metode pembayaran, dan jumlah. Setelah disimpan, catatan langsung masuk ke daftar utama.
>    
> 2. Lihat Semua Catatan Keuangan
>    
>    Menampilkan seluruh daftar catatan keuangan dalam bentuk tabel yang rapi. Pengguna bisa melihat detail lengkap seperti ID, tanggal, jenis, kategori, metode pembayaran, jumlah, dan keterangan.
>    
> 3. Ubah Catatan Keuangan
>    
>    Menu ini berfungsi untuk memperbarui data catatan keuangan yang sudah ada. Cukup masukkan ID catatan, lalu ganti data yang ingin diperbarui seperti tanggal, keterangan, jenis, kategori, metode pembayaran, maupun jumlah.
>    
> 4. Hapus Catatan Keuangan
>    
>    Digunakan untuk menghapus catatan keuangan yang sudah tidak diperlukan. Cukup masukkan ID catatan, lalu data akan dihapus permanen dari daftar.
>    
> 5. Ringkasan Saldo
>    
>    Menampilkan ringkasan keuangan berupa total pemasukan, total pengeluaran, dan saldo akhir (selisih antara pemasukan dan pengeluaran). Dengan menu ini kondisi keuangan bisa dipantau secara cepat.
>    
> 6. Filter dan Search
>    
>    Menu ini menampilkan sub-menu filter dan search (berdasarkan keterangan) yang bisa digunakan untuk menyaring catatan keuangan berdasarkan:
>    
>    a. Jenis (pemasukan/pengeluaran)
>    
>    b. Kategori (makan, transportasi, hiburan, belanja, tabungan, dll.)
>    
>    c. Metode pembayaran (cash, e-wallet, transfer)
>
>    d. Search (cari berdasarkan keterangan)
>
>    Fitur ini mempermudah pencarian data tertentu agar lebih spesifik.
>    
> 7. Set Batas Pengeluaran
>    
>    Menu ini digunakan untuk menetapkan batas pengeluaran bulanan. Jika total pengeluaran melewati batas yang ditetapkan, sistem akan memberikan peringatan agar pengelolaan keuangan lebih terkendali.
>    
> 8. Keluar
>    
>    Menu ini digunakan untuk keluar dari aplikasi. Setelah memilih opsi ini, sistem akan menampilkan pesan penutup sebelum program dihentikan.

#### 1. Menu Tambah Catatan Keuangan

<img width="688" height="407" alt="image" src="https://github.com/user-attachments/assets/feae8186-3ee4-44f1-9104-c23d6dc6ec5b" />


> Ketika menginputkan angka 1 pada menu utama maka akan diarahkan ke menu "Tambah Catatan Keuangan" seperti yang tertera pada gambar di atas

<img width="905" height="217" alt="image" src="https://github.com/user-attachments/assets/cb715ebe-5e17-4511-ae2b-66bccd306636" />

> Setelah itu bakal diminta untuk menginputkan "Tanggal", "Keterangan", "Jenis Transaksi", "Kategori Transaksi", "Metode Pembayaran", serta "Nominal Transaksi". Ketika berhasil menambahkan data baru akan muncul pesan "Data Berhasil Ditambahkan"

<img width="1025" height="408" alt="image" src="https://github.com/user-attachments/assets/df4b47e0-b4bd-4266-8b85-14f4d19fd624" />

> Setelah data baru berhasil ditambahkan, program akan langsung menampilkan ulang seluruh daftar catatan keuangan dalam bentuk tabel. Tabel ini memuat informasi lengkap seperti ID, Tanggal, Jenis (pemasukan/pengeluaran), Kategori, Metode Pembayaran, Jumlah, serta Keterangan.
>
> Di bagian bawah tabel, program juga memberikan pilihan "Apakah Ingin Menambah Catatan Lagi? (Y/T):".
> 
>  a. Jika menginputkan "Y", maka akan diarahkan untuk menginputkan catatan baru mulai dari menginputkan tanggal sampai nominal transaksinya. Ketika berhasil menambahkan data maka akan muncul pesan bahwa "Data Berhasil Ditambahkan".
> 
> <img width="957" height="219" alt="image" src="https://github.com/user-attachments/assets/ec4aabe8-aede-4d4a-8296-e7e4c56c4584" />
>
> Dan setelah berhasil menambahkan data baru, program akan langsung menampilkan ulang seluruh daftar catatan keuangan dalam bentuk tabel dan diarahkan kembali ke pertanyaan "Apakah Ingin Menambah Catatan Lagi? (Y/T):", Seperti yang tertera pada gambar di bawah ini.
> 
> <img width="1016" height="389" alt="image" src="https://github.com/user-attachments/assets/93414b8b-46ec-4601-8c40-3704b477d5a5" />
>
> b. Jika  menginputkan "T" maka akan di arahkan ke menu utama program ini.
> 
> <img width="386" height="348" alt="image" src="https://github.com/user-attachments/assets/c1a16e7a-c0f0-4a95-b777-fffb111a0ec5" />


- Pada menu "Tambah Catatan Keuangan", ketika nominal transaksi diinputkan menggunakan huruf alih-alih angka, sistem akan menampilkan peringatan berupa pesan "Harus angka! Silakan input ulang". Pesan ini memastikan agar data yang dimasukkan valid sesuai format angka, sehingga perhitungan transaksi dapat berjalan dengan benar, seperti terlihat pada gambar di bawah ini.
  
  <img width="936" height="202" alt="image" src="https://github.com/user-attachments/assets/0aa64c3f-7944-46ad-b028-b2f69707e823" />

- Selain validasi input angka, pada menu "Tambah Catatan Keuangan", setiap kali catatan pengeluaran baru ditambahkan, sistem akan otomatis menghitung ulang total seluruh pengeluaran. Jika total pengeluaran tersebut melebihi batas bulanan yang sudah ditentukan sebelumnya, maka aplikasi akan langsung menampilkan peringatan agar anggaran tetap terkontrol, seperti yang terlihat pada gambar di bawah ini.
  
  <img width="1061" height="586" alt="image" src="https://github.com/user-attachments/assets/26b2b15c-c5ed-4aae-a019-1fb9122c2e78" />

- Selain validasi input angka, pada menu "Tambah Catatan Keuangan", setiap kali mengosongkan inputan "misal mengosongkan input tanggal", maka sistem akan menampilkan peringatan berupa pesan "Tidak boleh kosong. Coba lagi".

  <img width="670" height="128" alt="image" src="https://github.com/user-attachments/assets/677956e8-ef34-4d7d-bc29-62b201ee3dc0" />

#### 2. Menu Lihat Semua Catatan Keuangan 

<img width="1032" height="684" alt="image" src="https://github.com/user-attachments/assets/f9e507f9-4769-4189-bfe8-c6ad65a0efad" />


> Ketika menginputkan angka 2 pada menu utama maka akan diarahkan ke menu "Lihat Semua Catatan Keuangan" seperti yang tertera pada gambar di atas.
>
> Pada menu ini, seluruh catatan keuangan yang sudah dimasukkan akan ditampilkan dalam bentuk tabel yang rapi, berisi informasi ID, Tanggal, Jenis (Pemasukan/Pengeluaran), Kategori, Metode, Jumlah, dan Keterangan.
>
> Selain itu, pada bagian bawah tabel akan muncul perintah "Ketik 0 untuk kembali" yang berfungsi untuk kembali ke menu utama.

#### 3. Menu Ubah Catatan Keuangan

<img width="1018" height="717" alt="image" src="https://github.com/user-attachments/assets/207e61d0-10be-427f-bc5f-da01b1fbb83c" />

> Ketika menginputkan angka 3 pada menu utama maka akan diarahkan ke menu "Ubah Catatan
Keuangan" seperti yang tertera pada gambar di atas.
>
>  Pada menu ini, seluruh daftar transaksi ditampilkan lengkap dengan ID, tanggal, jenis, kategori, metode pembayaran, jumlah, dan keterangan, sehingga catatan yang ingin diperbarui dapat dipilih dengan mudah.

<img width="1036" height="602" alt="image" src="https://github.com/user-attachments/assets/23f136c0-7b04-4160-be1e-0c0c8d68a6a6" />

<img width="1016" height="331" alt="image" src="https://github.com/user-attachments/assets/33144f74-7c63-402f-8659-55d029c3a935" />

> Setelah itu sistem akan meminta ID dari transaksi yang ingin diubah. Setelah ID dimasukkan, tersedia opsi untuk mengganti setiap field transaksi, mulai dari tanggal, keterangan, jenis, kategori, metode pembayaran, hingga nominal. Jika pada salah satu field tidak diberikan input baru dan langsung menekan Enter, maka nilai lama akan tetap dipertahankan. Dengan mekanisme ini, perubahan data dapat dilakukan secara fleksibel tanpa perlu menghapus atau menambahkan ulang catatan transaksi.
>
> Sebagai contoh, pada gambar ditunjukkan transaksi dengan ID 11 yang sebelumnya berisi data pemasukan dengan kategori gaji. Beberapa field kemudian diganti, seperti tanggal, keterangan, jenis, kategori, metode pembayaran, dan nominal transaksi. Setelah proses selesai, sistem akan menampilkan pesan “Data berhasil diubah” serta menampilkan kembali tabel catatan keuangan yang sudah diperbarui.

- ID sebelum diubah catatan keuangan nya
  <img width="981" height="25" alt="image" src="https://github.com/user-attachments/assets/57381df9-080b-4e93-a6d5-9150a7dc04fa" />
  
- ID sesudah diubah catatan keuangan nya
  <img width="982" height="28" alt="image" src="https://github.com/user-attachments/assets/1ee1b467-dc9e-4597-8483-5d6e32354b6e" />

Setelah proses Ubah Catatan Keuangan selesai dilakukan, sistem akan menampilkan daftar catatan terbaru yang sudah diperbarui. Selanjutnya, akan diberikan pilihan seperti yang terlihat pada gambar di bawah ini:

<img width="1028" height="395" alt="image" src="https://github.com/user-attachments/assets/9b6c060f-669d-451d-b795-be444910a6db" />

> a. Jika menginputkan "Y"
> 
>  <img width="1038" height="673" alt="image" src="https://github.com/user-attachments/assets/688421af-a675-4f78-8fb7-3b94081e9652" />
>  <img width="1009" height="339" alt="image" src="https://github.com/user-attachments/assets/e6e7773f-d2e4-4fcb-9dba-dca93c0be3c8" />
>
>  Program akan kembali menampilkan menu Ubah Catatan Keuangan. Pada tahap ini dapat dimasukkan ID lain untuk diperbarui. Dengan begitu, proses ubah catatan bisa dilakukan berulang kali sesuai kebutuhan tanpa harus kembali ke menu utama terlebih dahulu.
>
> b. Jika  menginputkan "T"
> 
>  <img width="385" height="349" alt="image" src="https://github.com/user-attachments/assets/bb046725-13d4-4df0-890a-25350b46a088" />

>
>  Program akan langsung keluar dari menu ubah catatan dan kembali ke Menu Utama. Hal ini memudahkan jika tidak ingin lagi melakukan perubahan pada catatan yang ada.

- Pada saat menginputkan ID yang tidak tersedia di dalam tabel, sistem akan memberikan peringatan "ID tidak ditemukan" seperti gambar di bawah ini.
  
  <img width="1199" height="815" alt="image" src="https://github.com/user-attachments/assets/7b99194b-783e-4dd7-a122-0a5cb58b09fe" />

  Hal ini menunjukkan bahwa ID yang dimasukkan tidak sesuai dengan daftar transaksi yang ada. Setelah itu, sistem tetap menampilkan ulang tabel catatan keuangan terbaru agar bisa memastikan ID mana yang valid.

  Dengan cara ini, tidak akan terjadi kesalahan dalam mengubah data transaksi karena hanya ID yang tersedia dalam tabel yang dapat diproses.
  
- Pada saat mencoba menginputkan ID dengan huruf (contoh: "sebelas") alih-alih angka (11), sistem akan otomatis menolak input tersebut. Program akan menampilkan pesan error "Harus angka! Silakan input ulang:".
  
  <img width="994" height="474" alt="image" src="https://github.com/user-attachments/assets/c6004323-fdf3-4281-bf23-ab5368a095b0" />

  Pesan ini memastikan bahwa input yang diterima hanya berupa angka valid sesuai ID transaksi.
  
- Apabila nominal transaksi diinputkan dengan huruf (contoh: "tiga juta") alih-alih angka (3000000), sistem akan langsung menolak input tersebut dan menampilkan pesan error "Harus angka! Silakan input ulang:" seperti pada gambar di bawah ini.
  
  <img width="497" height="211" alt="image" src="https://github.com/user-attachments/assets/115dfe19-20a1-409c-85be-36bf89500fcc" />
  <img width="1266" height="462" alt="image" src="https://github.com/user-attachments/assets/cffebac3-341f-4648-94b3-ab0c20ce469b" />

  Setelah itu, sistem akan meminta untuk memasukkan ulang nilai nominal dengan format angka yang benar. Begitu input diperbaiki, data transaksi akan berhasil diperbarui dan ditampilkan kembali pada tabel catatan keuangan.

- Pada menu "Ubah Catatan Keuangan", jika mengosongkan inputan yang ingin di update "misal mengosongkan inputan input tanggal baru, keterangan baru, jenis baru, kategori baru, metode pembayaran baru, dan nominal transaksi baru" maka nilai lama yang akan dipertahankan.

  <img width="1001" height="518" alt="image" src="https://github.com/user-attachments/assets/6668a812-564b-472c-8717-4abb92e583d6" />


#### 4. Menu Hapus Catatan Keuangan  

<img width="998" height="724" alt="image" src="https://github.com/user-attachments/assets/2f9ce51e-330b-4a68-978a-a1401913bc5e" />

<img width="1003" height="445" alt="image" src="https://github.com/user-attachments/assets/fe4b41d1-0b6c-4445-a10e-340ccdebd398" />

>  Ketika  menginputkan angka 4 pada menu utama, sistem akan mengarahkan ke menu Hapus Catatan Keuangan. Pada tahap ini, tabel catatan keuangan akan ditampilkan terlebih dahulu agar tidak terjadi kebingungan mengenai data mana yang ingin dihapus. Setelah tabel ditampilkan, sistem kemudian meminta untuk menginputkan ID catatan yang ingin dihapus.
>
> Jika ID yang diinputkan sesuai dengan data yang ada, maka sistem akan menampilkan pertanyaan konfirmasi "Apakah Anda yakin ingin menghapus data dengan ID ... (Y/T)?".
> 
> a. Jika  menginputkan "Y"
> 
>  <img width="531" height="108" alt="image" src="https://github.com/user-attachments/assets/765e9670-676f-4baa-9cb1-a1aec2497058" />
>
>   Maka catatan akan dihapus dari daftar, dan sistem menampilkan pesan "Data berhasil dihapus".
>
>   - Tampilan tabel sebelum dihapus datanya
>     <img width="987" height="308" alt="image" src="https://github.com/user-attachments/assets/6141a705-e19c-4652-b2f7-ef0abdd308b0" />
>    
>   - Tampilan tabel setelah di hapus datanya
>     <img width="1000" height="289" alt="image" src="https://github.com/user-attachments/assets/e3e67acc-690e-4c74-9fa3-3895c3bdfa05" />
>
> b. Jika menginputkan "T"
> 
>   <img width="550" height="105" alt="image" src="https://github.com/user-attachments/assets/cecccff0-205f-4406-bb0f-483ed10689ac" />
>
>   Maka proses penghapusan dibatalkan, dan sistem menampilkan pesan "Penghapusan dibatalkan".

Setelah berhasil menghapus data, sistem akan menampilkan pertanyaan "Apakah Ingin Menghapus Catatan Lagi? (Y/T):" seperti terlihat pada gambar di bawah.

  <img width="1006" height="448" alt="image" src="https://github.com/user-attachments/assets/9f3618d5-4345-4936-892d-d81015957710" />

> a. Jika menginputkan "Y"
> 
>   <img width="1009" height="551" alt="image" src="https://github.com/user-attachments/assets/66af7810-6277-41dc-98e3-cb2ad9d5e119" />
>
>  Program akan kembali menampilkan tabel catatan keuangan terbaru, kemudian meminta untuk  menginputkan ID catatan lain yang ingin dihapus. Proses ini dapat dilakukan berulang kali sampai dipilih untuk berhenti. Dengan cara ini, lebih dari satu catatan dapat dihapus dalam satu kali sesi tanpa harus kembali ke menu utama terlebih dahulu.
>
> b. Jika menginputkan "T"
> 
>  <img width="394" height="352" alt="image" src="https://github.com/user-attachments/assets/08b57eb1-5e35-477b-971d-9116a3f91602" />

>
>  Program akan langsung kembali ke Menu Utama tanpa menghapus catatan tambahan.

<img width="1024" height="485" alt="image" src="https://github.com/user-attachments/assets/72867780-f83f-4f8e-9a36-7014f33cd9dd" />

> Jika ID yang diinputkan tidak sesuai atau tidak ada dalam daftar catatan keuangan, maka sistem akan menampilkan pesan "ID tidak ditemukan".
>
> Hal ini bertujuan agar tidak terjadi kesalahan dalam menghapus catatan yang tidak ada pada tabel. Setelah itu, sistem tetap memberikan pilihan "Apakah Ingin Menghapus Catatan Lagi? (Y/T):" sehingga dapat dicoba kembali dengan memasukkan ID yang benar, atau keluar dari proses penghapusan dengan menginputkan "T".


<img width="1038" height="422" alt="image" src="https://github.com/user-attachments/assets/5f670a08-9cab-4713-8535-fb659566e937" />

> Jika ID diinputkan dalam bentuk huruf (contoh: mengetik "satu" alih-alih angka 1), maka sistem tidak akan menerima input tersebut dan akan menampilkan pesan "Harus angka! Silakan input ulang:".
>
> Pesan ini berfungsi sebagai validasi agar ID hanya bisa diinputkan dalam bentuk angka sesuai dengan tabel catatan yang tersedia.

- Pada saat pengguna memilih menu Hapus Catatan Keuangan, sistem meminta ID catatan yang ingin dihapus. Jika pengguna langsung menekan Enter tanpa mengisi ID, maka input dianggap kosong dan sistem menampilkan pesan “Penghapusan dibatalkan”.
  
  <img width="444" height="367" alt="image" src="https://github.com/user-attachments/assets/7bca2a3e-5ec8-446c-b28d-bd68c647b384" />


#### 5. Menu Ringkasan Saldo

<img width="686" height="474" alt="image" src="https://github.com/user-attachments/assets/2e60355e-8fe5-4cf1-b81b-7f5106fc4a0c" />


> Ketika menginputkan angka 5 pada menu utama, sistem akan menampilkan menu Ringkasan Saldo. Pada menu ini ditampilkan rekapitulasi keuangan yang berisi total pemasukan, total pengeluaran, serta saldo akhir yang merupakan selisih dari keduanya. Informasi ini membantu menampilkan kondisi keuangan terkini secara lebih jelas dan ringkas. Setelah ringkasan saldo ditampilkan, sistem akan meminta untuk mengetik angka 0 agar dapat kembali ke menu utama.

<img width="701" height="225" alt="image" src="https://github.com/user-attachments/assets/1080d1c1-cb4b-46b8-a54b-c792eded2da2" />

> Ketika menambahkan catatan pengeluaran dengan jumlah yang melebihi pemasukan, lalu membuka menu Ringkasan Saldo, sistem akan tetap menampilkan total pemasukan, total pengeluaran, dan saldo akhir. Karena nilai pengeluaran lebih besar dibandingkan pemasukan, saldo ditampilkan dalam kondisi negatif. Selain itu, sistem juga memberikan catatan berupa peringatan: “Pengeluaran lebih besar dari pemasukan. Harap bijak mengatur keuangan.” Setelah itu, sistem meminta untuk mengetik angka 0 agar dapat kembali ke menu utama.

#### 6. Menu Filter dan Search Catatan

<img width="628" height="514" alt="image" src="https://github.com/user-attachments/assets/655b7415-3cac-417f-8ba4-846db2ef18c7" />


> Ketika menginputkan angka 6 pada menu utama, sistem akan menampilkan Menu Filter dan Search. Pada menu ini tersedia beberapa pilihan filter dan search (berdasarkan keterangan), untuk pilihan filter yaitu ada filter per jenis transaksi (pemasukan atau pengeluaran), filter per kategori, dan filter per metode pembayaran. Selain itu, juga tersedia opsi untuk kembali ke menu sebelumnya. Melalui menu ini, catatan keuangan dapat disaring sesuai kriteria tertentu agar informasi yang ditampilkan lebih fokus dan mudah dipahami.

a. Filter per Jenis (Pemasukan/Pengeluaran) 

  <img width="685" height="294" alt="image" src="https://github.com/user-attachments/assets/0a5138b5-f668-47ae-9423-3923062de9c9" />

  > Setelah memilih opsi 1. Filter per Jenis (Pemasukan/Pengeluaran) pada menu filter catatan, sistem akan menampilkan tampilan baru bertuliskan Filter berdasarkan Jenis. Pada tahap ini, sistem meminta input jenis transaksi yang ingin difilter, apakah termasuk pemasukan atau pengeluaran. Input tersebut akan digunakan untuk menampilkan daftar catatan keuangan sesuai jenis yang dipilih sehingga data lebih terfokus.

- Pemasukan
  
  <img width="1013" height="255" alt="image" src="https://github.com/user-attachments/assets/24f57eb7-3956-43ff-90e5-759c3ebb0ca7" />
  
  > Setelah memilih jenis transaksi Pemasukan, sistem akan menampilkan daftar catatan keuangan yang hanya berisi transaksi dengan jenis tersebut. Tabel yang ditampilkan memuat detail berupa ID, tanggal, jenis, kategori, metode, jumlah, serta keterangan dari setiap transaksi pemasukan. Dari hasil filter terlihat bahwa hanya transaksi dengan kategori gaji maupun tabungan yang masuk dalam daftar. Setelah selesai melihat data, dapat diketik angka 0 untuk kembali ke menu sebelumnya.

- Pengeluaran
  
  <img width="1024" height="308" alt="image" src="https://github.com/user-attachments/assets/4175bc72-9c95-4eec-944e-321486b2d114" />

  > Setelah memilih jenis transaksi Pengeluaran, sistem menampilkan daftar catatan keuangan yang hanya berisi transaksi dengan jenis pengeluaran. Tabel yang ditampilkan berisi detail ID, tanggal, jenis, kategori, metode, jumlah, serta keterangan dari setiap transaksi. Dari hasil filter terlihat bahwa data pengeluaran meliputi kebutuhan sehari-hari seperti makan, transportasi, hiburan, belanja, serta tagihan. Dengan tampilan ini, semua transaksi pengeluaran dapat diamati secara lebih jelas tanpa bercampur dengan pemasukan. Setelah selesai, cukup mengetik angka 0 untuk kembali ke menu sebelumnya.

- Selain pilihan pemasukan dan pengeluaran
  
  <img width="673" height="118" alt="image" src="https://github.com/user-attachments/assets/acb5f4f7-8f5a-42ed-bffe-0fa9d19d8970" />

  > Jika pada filter jenis transaksi dimasukkan selain pilihan Pemasukan atau Pengeluaran, misalnya kata pendapatan, maka sistem akan menampilkan pesan“ Pilihan tidak valid. Pilihan yang valid: Pemasukan/Pengeluaran”. Setelah itu, sistem secara otomatis akan meminta input ulang yang benar yaitu "Pemasukan/Pengeluaran".

- Pada filter berdasarkan jenis, jika mengosongkan inputan "Masukan Jenis (Pemasukan/Pengeluaran). Maka akan muncul pesan peringatan yaitu "Tidak boleh kosong. Coba lagi", dan akan diminta untuk menginputkan ulang jenis yang ingin di filter.

  <img width="681" height="127" alt="image" src="https://github.com/user-attachments/assets/b52560ec-c886-46aa-932d-445b791e5251" />


b. Filter per Kategori  

  <img width="716" height="288" alt="image" src="https://github.com/user-attachments/assets/f9e842f5-eea3-434f-9940-27be111e86d7" />


  > Ketika memilih opsi Filter per Kategori pada menu filter catatan, sistem akan menampilkan pilihan untuk memasukkan kategori transaksi. Kategori yang tersedia antara lain gaji, makan, transportasi, hiburan, belanja, tabungan, dan tagihan. Setelah kategori dimasukkan, sistem akan menampilkan catatan transaksi yang sesuai dengan kategori tersebut dalam bentuk tabel, sehingga lebih mudah untuk melihat pengeluaran atau pemasukan berdasarkan kategori tertentu.

- Kategori gaji
  
  <img width="1019" height="210" alt="image" src="https://github.com/user-attachments/assets/4dc47c9e-072a-41cd-92a9-4240bb77cce5" />

  > Ketika memilih kategori gaji, sistem akan menampilkan daftar transaksi yang termasuk dalam kategori tersebut. Pada tampilan terlihat catatan pemasukan pada tanggal 1 September 2025 dengan metode transfer sebesar Rp 3.000.000 yang tercatat sebagai Gaji Bulan September. Setelah data ditampilkan, tersedia perintah untuk mengetik angka 0 agar bisa kembali ke menu sebelumnya.

- Kategori makan
  
  <img width="1008" height="214" alt="image" src="https://github.com/user-attachments/assets/7dae145d-325a-4fab-a905-65ef1f65300b" />

  > Ketika memilih kategori makan, sistem akan menampilkan data transaksi yang sesuai dengan kategori tersebut. Pada hasil filter terlihat satu catatan pengeluaran pada tanggal 2 September 2025 dengan metode pembayaran cash sebesar Rp 25.000, yang tercatat sebagai Beli Makan Siang. Setelah data ditampilkan, sistem memberikan opsi untuk mengetik angka 0 agar dapat kembali ke menu sebelumnya.
  
- Kategori transportasi
  
  <img width="1003" height="215" alt="image" src="https://github.com/user-attachments/assets/e1533edb-284f-426f-a00b-fb69bce4c928" />
  
  > Ketika memilih kategori transportasi, sistem akan menampilkan data transaksi yang sesuai dengan kategori tersebut. Pada hasil filter terlihat satu catatan pengeluaran pada tanggal 3 September 2025 dengan metode pembayaran cash sebesar Rp 10.000, yang tercatat sebagai Ongkos Transportasi. Setelah data ditampilkan, sistem akan meminta untuk mengetik angka 0 agar dapat kembali ke menu sebelumnya.

- Kategori hiburan
  
  <img width="1009" height="214" alt="image" src="https://github.com/user-attachments/assets/03ce37e8-0027-421b-9be9-3e5c7dbab591" />

  > Ketika memilih kategori hiburan, sistem akan menampilkan transaksi yang tercatat dalam kategori tersebut. Pada hasil filter terlihat satu catatan pengeluaran pada tanggal 4 September 2025 dengan metode pembayaran E-Wallet sebesar Rp 50.000, yang digunakan untuk kegiatan nonton bioskop. Setelah informasi ditampilkan, sistem memberikan opsi untuk mengetik angka 0 agar dapat kembali ke menu sebelumnya.

- Kategori belanja
  
  <img width="1005" height="216" alt="image" src="https://github.com/user-attachments/assets/4fa0a197-ffb1-4d67-a579-6d45e3353329" />

  > Ketika memilih kategori belanja, sistem akan menampilkan catatan transaksi yang termasuk dalam kategori tersebut. Pada hasil filter terlihat satu transaksi pengeluaran yang terjadi pada tanggal 5 September 2025 dengan metode pembayaran transfer sebesar Rp 200.000, yang digunakan untuk membeli pakaian. Setelah data ini ditampilkan, sistem memberikan opsi untuk mengetik angka 0 agar dapat kembali ke menu sebelumnya.

- Kategori tabungan
  
  <img width="1029" height="238" alt="image" src="https://github.com/user-attachments/assets/c7e691ba-19bb-48f4-b4f5-e80d056e9a96" />

  > Ketika memilih kategori tabungan, sistem akan menampilkan daftar transaksi yang berkaitan dengan tabungan. Dari hasil filter terlihat ada dua transaksi pemasukan. Transaksi pertama terjadi pada tanggal 6 September 2025 sebesar Rp 500.000 dengan metode transfer, yang dicatat sebagai kegiatan menabung rutin. Transaksi kedua terjadi pada tanggal 9 September 2025 sebesar Rp 300.000 dengan metode transfer, yang dicatat sebagai isi saldo tabungan. Setelah data ditampilkan, sistem menunggu input angka 0 untuk kembali ke menu sebelumnya.

- Kategori tagihan
  
  <img width="1006" height="238" alt="image" src="https://github.com/user-attachments/assets/69386296-20ab-436e-bf40-626b39e72146" />

  > Ketika memilih kategori tagihan, sistem menampilkan dua transaksi pengeluaran. Transaksi pertama tercatat pada tanggal 7 September 2025 sebesar Rp 150.000 dengan metode E-Wallet, digunakan untuk membayar listrik. Transaksi kedua terjadi pada tanggal 8 September 2025 sebesar Rp 100.000 dengan metode transfer, digunakan untuk membayar air. Setelah daftar transaksi tagihan ditampilkan, sistem menunggu input angka 0 untuk kembali ke menu sebelumnya.

- Selain yang ada di pilihan kategori
  
  <img width="806" height="128" alt="image" src="https://github.com/user-attachments/assets/e1f5e12e-96f9-4907-a163-0068a9c9cc50" />

  > Ketika memasukkan kategori yang tidak tersedia dalam daftar pilihan, misalnya sedekah, sistem akan menampilkan pesan "Pilihan tidak valid. Pilihan yang valid: Gaji/Makan/Transportasi/Hiburan/Belanja/Tabungan/Tagihan". Dengan begitu, hanya kategori yang memang tercatat dalam sistem seperti gaji, makan, transportasi, hiburan, belanja, tabungan, atau tagihan yang dapat difilter. Setelah itu, tampilan akan kembali meminta untuk menginputkan kategori sesuai kategori yang ada.

- Pada filter kategori, jika mengosongkan inputan "Masukkan Kategori (gaji, makan, transportasi, hiburan, belanja, tabungan, tagihan):", maka akan muncul pesan peringatan yaitu "Tidak boleh kosong. Coba lagi", dan akan diminta untuk menginputkan ulang kategori yang ingin di filter.

  <img width="728" height="121" alt="image" src="https://github.com/user-attachments/assets/16f8cb25-9561-4952-8fc5-41fe7bfa542d" />

c. Filter per Metode Pembayaran 

   <img width="678" height="293" alt="image" src="https://github.com/user-attachments/assets/62430ead-a506-4378-a6c2-53ff27f83d65" />


  > Ketika memilih menu Filter per Metode Pembayaran, sistem akan menampilkan opsi untuk memasukkan metode pembayaran, yaitu Cash, E-Wallet, atau Transfer.

- Cash
  
  <img width="1025" height="233" alt="image" src="https://github.com/user-attachments/assets/3f97f153-3452-4f0a-bb29-b3541e66cb98" />

  > Ketika memilih metode pembayaran Cash, sistem akan menampilkan daftar transaksi yang menggunakan metode pembayaran tersebut. Pada tampilan terlihat dua catatan pengeluaran, yaitu transaksi makan dengan nominal Rp 25.000 dan transaksi transportasi dengan nominal Rp 10.000. Setelah data ditampilkan, tersedia perintah untuk mengetik angka 0 agar bisa kembali ke menu sebelumnya.

- Transfer
  
  <img width="1037" height="295" alt="image" src="https://github.com/user-attachments/assets/444926c9-c446-4f7b-9cb1-efbca08994ae" />

  > Ketika memilih metode pembayaran Transfer, sistem akan menampilkan daftar transaksi yang menggunakan metode tersebut. Pada tampilan terlihat beberapa catatan, di antaranya pemasukan gaji sebesar Rp 3.000.000, pengeluaran belanja sebesar Rp 200.000, pemasukan tabungan sebesar Rp 500.000, pembayaran tagihan air sebesar Rp 100.000, serta pemasukan tabungan sebesar Rp 300.000. Seluruh transaksi ditampilkan dalam bentuk tabel agar lebih jelas, dan setelah itu tersedia perintah untuk mengetik angka 0 agar bisa kembali ke menu sebelumnya.

- E-Wallet
  
  <img width="1015" height="242" alt="image" src="https://github.com/user-attachments/assets/4ab75684-8f54-4050-be4d-5fc08afee3d3" />

  > Ketika memilih metode pembayaran E-Wallet, sistem akan menampilkan daftar transaksi yang dilakukan menggunakan dompet digital. Pada tabel terlihat dua catatan pengeluaran, yaitu sebesar Rp 50.000 untuk hiburan menonton bioskop dan Rp 150.000 untuk pembayaran tagihan listrik. Seluruh data ditampilkan dengan format tabel agar mudah dibaca, dan setelah selesai tersedia instruksi untuk mengetik angka 0 agar kembali ke menu sebelumnya.

- Selain yang ada di pilihan metode pembayaran
  
 <img width="675" height="114" alt="image" src="https://github.com/user-attachments/assets/02fbf1c0-e75e-452b-8695-04aa5240e6e7" />


  > Ketika pada menu filter dimasukkan metode pembayaran yang tidak tersedia, misalnya “Kartu debit”, sistem akan langsung menampilkan pesan bahwa "Pilihan tidak valid. Pilihan yang valid: Cash/E-Wallet/Transfer". Setelah itu, sistem akan menampilkan untuk meminta ulang input metode pembayaran yang tersedia.

- Pada filter metode pembayaran, jika mengosongkan inputan "Masukkan Metode (Cash/E-Wallet/Transfer):", maka akan muncul pesan peringatan yaitu "Tidak boleh kosong. Coba lagi", dan akan diminta untuk menginputkan ulang metode pembayaran yang ingin di filter.

<img width="682" height="121" alt="image" src="https://github.com/user-attachments/assets/eb0676d8-a796-44a0-b25a-4f152e42dfbe" />

d. Search (cari di keterangan)  

<img width="682" height="292" alt="image" src="https://github.com/user-attachments/assets/7d890f9c-d9b7-4afd-99ff-ff973ff32bd4" />

> Pada menu Filter/Search dipilih opsi 4. Search (cari di keterangan). Sistem menampilkan header SEARCH KETERANGAN dan meminta input “Kata kunci:” untuk memulai pencarian pada kolom keterangan transaksi.

<img width="999" height="230" alt="image" src="https://github.com/user-attachments/assets/fe6fb5a0-4fcf-4811-89cb-5510f59989a6" />

> Input kata kunci: “makan”. Sistem melakukan pencarian case-insensitive pada kolom keterangan, lalu menampilkan tabel hasil yang cocok (ID, Tanggal, Jenis, Kategori, Metode, Jumlah, Keterangan). Tampil dua catatan transaksi yang mengandung kata “makan”. Di bagian bawah tabel terdapat prompt “-> Ketik 0 untuk kembali” untuk kembali ke menu.

<img width="689" height="148" alt="image" src="https://github.com/user-attachments/assets/68f52940-d063-447c-9886-387cbf9902d4" />

> Input kata kunci: “bayar utang”. Sistem tidak menemukan catatan transaksi dengan keterangan yang memuat frasa tersebut, sehingga muncul pesan “Tidak ada data dengan hasil pencarian.” dan tetap menampilkan opsi “-> Ketik 0 untuk kembali” ke menu sebelumnya.

<img width="685" height="127" alt="image" src="https://github.com/user-attachments/assets/e826ca27-510f-4694-9c69-1bee409eb77e" />

> Saat masuk ke menu SEARCH KETERANGAN, tombol Enter ditekan tanpa mengisi kata kunci. Sistem mendeteksi input kosong lalu menampilkan pesan “Tidak boleh kosong. Coba lagi”. Setelah itu, sistem kembali meminta input “-> Kata kunci:” hingga nilai yang dimasukkan valid.

e. Kembali

  <img width="642" height="522" alt="image" src="https://github.com/user-attachments/assets/92fa30e3-292b-49f6-8ac1-c01bf6863bed" />

  > Ketika pada menu filter dipilih opsi nomor 5, sistem akan mengembalikan tampilan ke menu utama. Dengan begitu, proses penyaringan catatan dapat dihentikan sementara dan navigasi diarahkan kembali ke pilihan utama aplikasi, seperti menambah catatan keuangan, melihat daftar catatan, mengubah, menghapus, hingga ringkasan saldo. Fitur ini berfungsi sebagai jalan pintas agar tidak perlu menutup aplikasi saat ingin berpindah dari menu filter dan search ke menu utama.

f. Jika menginputkan selain menu 1-5

  <img width="629" height="450" alt="image" src="https://github.com/user-attachments/assets/516b43f7-3075-4e1d-93b8-e86c7f80a4c4" />

  > Apabila pada menu filter dimasukkan angka di luar pilihan 1 sampai 5, sistem akan langsung menampilkan pesan “Pilihan tidak valid”. Setelah itu, menu filter catatan ditampilkan kembali sehingga dapat memilih opsi yang benar sesuai dengan daftar yang tersedia. Hal ini memastikan agar hanya input yang sesuai dengan menu yang bisa diproses oleh sistem.

g. Jika menginputkan menu pakai huruf bukan angka

  <img width="627" height="223" alt="image" src="https://github.com/user-attachments/assets/0da41826-f2a1-4983-b749-a9f45bef5db1" />

  > Apabila pada menu filter dimasukkan huruf alih-alih angka, sistem akan langsung menolak input tersebut dengan menampilkan pesan “Harus angka! Silakan input ulang”. Dengan begitu, hanya input berupa angka yang valid sesuai pilihan menu 1 sampai 4 yang bisa diterima. Mekanisme ini dibuat untuk memastikan agar sistem tetap berjalan sesuai alur yang benar dan menghindari kesalahan input.

h. Jika mengosongkan input pada menu

<img width="642" height="221" alt="image" src="https://github.com/user-attachments/assets/cd658bc2-873a-428e-8b33-469f9fa152e4" />

Maka akan muncul pesan "Harus angka! Silakan input ulang:".


#### 7. Menu Set Batas Pengeluaran

<img width="697" height="420" alt="image" src="https://github.com/user-attachments/assets/9c7eaf12-58ae-4787-91b2-1298c2fa5819" />

> Ketika menginputkan angka 7 pada menu utama, sistem akan menampilkan menu Set Batas Pengeluaran Bulanan. Pada menu ini, ditunjukkan terlebih dahulu batas pengeluaran saat ini. Jika batas belum pernah ditentukan, maka statusnya akan ditampilkan sebagai “tidak diaktifkan”. Selanjutnya, diminta untuk memasukkan batas baru sesuai kebutuhan, atau mengetik angka 0 apabila ingin menonaktifkan fitur batas pengeluaran.

<img width="715" height="195" alt="image" src="https://github.com/user-attachments/assets/529ef75f-34ed-42e2-8f88-1a625e7e4991" />

> Setelah memasukkan batas pengeluaran baru, sistem akan menampilkan informasi yang lebih detail. Batas pengeluaran ditetapkan sesuai angka yang dimasukkan, misalnya Rp 1.000.000. Kemudian, sistem menampilkan total pengeluaran saat ini, yaitu Rp 535.000. Dari data tersebut, dihitung sisa ruang anggaran sebesar Rp 465.000. Informasi ini membantu dalam memantau sejauh mana pengeluaran mendekati batas yang sudah ditentukan. Setelah itu, dapat mengetik angka 0 untuk kembali ke menu utama.

<img width="733" height="218" alt="image" src="https://github.com/user-attachments/assets/5cc2fd79-04b4-4ba8-bd90-8cb28cff1bc8" />

> Ketika batas pengeluaran baru ditetapkan sebesar Rp 1.000.000, sistem langsung membandingkannya dengan total pengeluaran yang sudah tercatat. Dari hasil perhitungan, total pengeluaran mencapai Rp 4.035.000, yang berarti jauh melebihi batas yang telah ditentukan. Akibatnya, sisa ruang anggaran menjadi negatif, yaitu Rp -3.035.000. Sistem kemudian memberikan peringatan dengan jelas berupa pesan: “Pengeluaran sudah melebihi batas !!!”. Hal ini berfungsi sebagai pengingat agar lebih berhati-hati dalam mengatur keuangan. Setelah informasi ini ditampilkan, dapat mengetik angka 0 untuk kembali ke menu utama.

<img width="706" height="162" alt="image" src="https://github.com/user-attachments/assets/f7adb9fd-b96a-4b6f-8d75-068e41b4ae9e" />

> Ketika batas pengeluaran diatur dengan nilai 0, sistem akan secara otomatis menonaktifkan fitur pembatasan pengeluaran bulanan. Setelah itu, ditampilkan pesan konfirmasi berupa “Batas pengeluaran bulanan dinonaktifkan” sebagai tanda bahwa pengaturan sebelumnya tidak lagi berlaku. Untuk kembali ke menu utama, cukup mengetik angka 0 sesuai instruksi yang diberikan sistem.

<img width="688" height="150" alt="image" src="https://github.com/user-attachments/assets/04b689b2-6cb4-4ff9-be2d-d9f1fe62f9a1" />

> Ketika mengosongkan input "Masukkan batas baru (ketik 0 untuk menonaktifkan):", makan akan muncul pesan "Tidak boleh kosong. Coba lagi", sehingga hanya boleh mengisi batas pengeluaran terbaru atau ketik 0 untuk menonaktifkan.


#### 8. Menu Keluar

<img width="454" height="401" alt="image" src="https://github.com/user-attachments/assets/d0652801-2e8f-47f5-9db6-a739c1f7b7ce" />

> Ketika menginputkan angka 8 pada menu utama, sistem akan langsung menutup aplikasi Pocket Guard. Sebelum keluar, ditampilkan pesan ucapan terima kasih berupa “Terima kasih telah menggunakan POCKET GUARD” serta doa agar keuangan selalu aman dan terjaga. Dengan begitu, aplikasi benar-benar mengakhiri jalannya program setelah perintah keluar dipilih.

#### 9. Jika Menginputkan Menu Selain Menu 1-8, Menginputkan Menu Pakai Huruf Bukan Angka, dan Mengkosongkan inputan pada saat input menu 1-8

<img width="430" height="702" alt="image" src="https://github.com/user-attachments/assets/640fee0c-2940-4da6-8931-8cde3526e169" />

> Ketika menginputkan angka di luar rentang 1 sampai 8 pada menu utama, sistem akan menampilkan pesan “Pilihan tidak valid. Silakan coba lagi!!!” lalu mengembalikan tampilan ke menu utama agar dapat memilih ulang menu yang benar.

<img width="431" height="326" alt="image" src="https://github.com/user-attachments/assets/5e558d4d-c4b3-4581-b535-eaf94c632bc6" />


> Selain itu, jika input yang dimasukkan berupa huruf atau teks alih-alih angka, sistem akan menolak dengan menampilkan pesan “Harus angka! Silakan input ulang:” kemudian meminta masukan baru sampai format yang dimasukkan benar berupa angka dalam rentang 1–8.

<img width="404" height="325" alt="image" src="https://github.com/user-attachments/assets/325cdbbe-ea57-43c5-a232-41ac93870e5a" />

> Jika input yang dimasukkan kosong atau bukan angka, sistem akan menolak dengan menampilkan pesan “Harus angka! Silakan input ulang:”, lalu meminta pengguna untuk memasukkan kembali pilihan menu dalam bentuk angka 1–8.


