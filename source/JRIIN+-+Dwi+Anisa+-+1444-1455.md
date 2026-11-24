

### **JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 

# **Rancang Bangun Sistem Informasi Penerimaan Murid Baru (SPMB) Berbasis Serverless Menggunakan Google Apps Script dengan Model Waterfall pada SDN Kampung Bambu 1 Kabupaten Tangerang** 

**Dwi Anisa**<sup>**1**</sup> **, Muhamad Nur Faizal**<sup>**2**</sup> **, Maulana Ardiansyah**<sup>**3**</sup> **, Nola Paulina Hasibuan**<sup>**4**</sup> 

1,2,3,4 Fakultas Ilmu Komputer, Program Studi Teknik Informatika, Universitas Pamulang, Kota Tangerang Selatan, Indonesia 

Email:<sup>1</sup> <u>dwianisa4567@gmail.com,</u><sup>2</sup> <u>mnrfzl33@gmail.com,</u><sup>3</sup> <u>Maulanaunpam2012@gmail.com,</u> 

4noelapaulina7@gmail.com 

(* : coressponding author) 

**Abstark** − SDN Kampung Bambu 1 telah mulai menggunakan Sistem Penerimaan Murid Baru (SPMB) berbasis internet yang terhubung dengan situs resmi sekolah. Namun, karena dioperasikan pada server yang sama, sistem ini sering mengalami penurunan performa bahkan bisa mengalami downtime ketika jumlah pengunjung meningkat selama periode pendaftaran. Hal ini menyebabkan calon siswa dan orang tua kesulitan dalam menyelesaikan proses pendaftaran, sedangkan staf administrasi kesulitan dalam memonitor data pendaftar yang masuk. Penelitian ini bertujuan untuk merancang dan membangun SPMB berbasis web yang terpisah dari situs resmi sekolah dengan memanfaatkan pendekatan tanpa server menggunakan Google Apps Script, yang dihubungkan dengan Google Forms sebagai antarmuka pendaftaran serta Google Sheets sebagai basis data. Model pengembangan yang digunakan ialah model Waterfall, yang mencakup tahap analisis kebutuhan, desain sistem, pelaksanaan, dan pengujian. Hasil penelitian mengindikasikan bahwa sistem yang dibuat dapat menangani proses pendaftaran secara mandiri tanpa membebani server situs utama, sehingga layanan tetap dapat diakses dengan stabil meskipun banyak pengguna yang mengaksesnya bersamaan. Selain itu, sistem ini memberikan kemudahan akses bagi calon siswa dan orang tua serta membantu staf administrasi dalam mengelola data pendaftar dengan cara yang lebih terorganisir dan efisien. 

**Kata kunci:** Sistem Penerimaan Murid Baru, Google Apps Script, Tanpa Server, Model Waterfall, Situs Web. 

**Abstract** − _SDN Kampung Bambu 1 has introduced an online New Student Admission System (SPMB) linked to the school’s primary website. Nevertheless, since it operates on the same server, this system often suffers from reduced performance and may even experience outages during peak times when registration opens. Consequently, potential students and their families frequently encounter issues completing the registration, while administrative personnel struggle to monitor incoming data from applicants. This research seeks to create and implement a web-based SPMB that functions independently from the school's main site by utilizing a serverless approach through Google Apps Script, along with Google Forms for the registration interface and Google Sheets for data storage. The development process followed the Waterfall model, moving through the phases of requirements analysis, system design, implementation, and testing. The findings indicate that the newly created system can manage the registration process autonomously without overloading the main website’s server, ensuring consistent service quality even with numerous users accessing it at the same time. Moreover, this system offers greater accessibility for potential students and their families while also assisting administrative staff in organizing and managing applicant data in a more systematic and effective way._ 

**Keywords:** _New Student Admission System, Google Apps Script, Serverless, Waterfall Model, Website_ 

## **1. PENDAHULUAN** 

Kemajuan dalam teknologi informasi saat ini mendorong hampir semua lembaga, termasuk sekolah, untuk mulai menggunakan layanan digital dalam aktivitas mereka sehari-hari. Salah satu contohnya adalah keberadaan situs web sekolah yang fungsinya kini telah berevolusi, bukan hanya sebagai sumber informasi, tetapi juga sebagai alat untuk layanan administrasi, termasuk dalam Sistem Penerimaan Murid Baru (SPMB). Dengan adanya SPMB yang berbasis digital memungkinkan proses pendaftaran, pengolahan data, hingga penyampaian informasi kepada orang tua menjadi lebih cepat, terorganisir, dan dapat mengurangi kesalahan pencatatan yang sering terjadi pada sistem manual. Atmaja dan rekan-rekan menjelaskan bahwa perancangan sistem informasi PPDB berbasis web sejatinya ditujukan untuk mempercepat pendataan dan sekaligus meningkatkan akurasi pengolahan data (Apriana, 2022) Dengan kata lain, penerapan teknologi dalam proses 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1444 

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



administrasi penerimaan siswa kini bukan hanya sekadar tambahan, tetapi telah menjadi kebutuhan mendesak bagi sekolah-sekolah saat ini. 

SDN Kampung Bambu 1 termasuk salah satu sekolah yang telah mengimplementasikan SPMB berbasis web yang terhubung langsung dengan situs utama sekolah. Tindakan ini secara mendasar sangat membantu, karena calon siswa dan orang tua dapat mengakses informasi dan melakukan pendaftaran tanpa perlu datang langsung ke sekolah. Hal ini sejalan dengan temuan Nasser, Arifudin, Barlian, dan Sauri, yang menyatakan bahwa penerapan sistem penerimaan siswa baru yang berbasis web mampu memberikan kemudahan akses informasi serta menjadikan proses pendaftaran lebih transparan dan teratur, terutama ketika tatap muka langsung sulit dilakukan (Nasser et al., 2021). 

Namun, di balik kemudahan yang ada, terdapat masalah yang cukup mengganggu. SPMB yang sebelumnya berjalan pada server yang sama dengan situs utama sekolah ternyata tidak mampu menangani lonjakan trafik saat periode pendaftaran dibuka. Ketika ratusan pengguna mengakses sekaligus, beban server meningkat secara drastis hingga akhirnya berdampak pada penurunan performa, bahkan sering kali sistem mengalami gangguan total. Situasi ini sebenarnya dapat dimaklumi, mengingat semakin tingginya trafik yang masuk ke server, semakin besar pula kemungkinan terjadinya gangguan jika kapasitasnya terlampaui (Arief & Sugiarti, 2022). Akibatnya, banyak orang tua yang tidak dapat menyelesaikan proses pendaftaran, dan staf administrasi juga merasa kesulitan untuk memantau data pendaftar yang masuk. Keadaan ini jelas mengganggu kegiatan operasional sekolah, dan yang lebih disayangkan, berpotensi menurunkan kepercayaan masyarakat terhadap layanan digital yang telah dibangun oleh sekolah. 

Untuk mengatasi masalah ini, metode arsitektur tanpa server bisa menjadi pilihan yang layak untuk dipertimbangkan. Dengan cara kerja serverless, para pengembang tidak perlu lagi mengurus infrastruktur server secara langsung, yang membuat biaya lebih efisien dan skalabilitas lebih mudah diatur. Salah satu platform yang menawarkan pendekatan ini secara gratis adalah Google Apps Script, sebuah layanan berbasis cloud dari Google. Penelitian yang dilakukan oleh Andaman dan rekan-rekannya mengenai penggunaan Google Sites dan Google Apps Script menunjukkan bahwa platform ini mampu melakukan integrasi data secara otomatis tanpa memerlukan hosting pihak ketiga, sehingga sangat relevan untuk digunakan di lingkungan dengan keterbatasan infrastruktur teknologi, seperti kebanyakan sekolah (Andaman et al., 2025). Di samping itu, Google Apps Script juga terhubung dengan Google Workspace, termasuk Google Sheets sebagai tempat penyimpanan data dan Google Forms sebagai platform pengisian formulir, sehingga mempermudah pengembangan dan penggunaannya. 

Dalam merancang sistem ini, penulis memilih metode Waterfall sebagai pendekatan pengembangan, mengingat karakteristiknya yang berurutan, mulai dari analisis kebutuhan, perancangan, implementasi, pengujian, hingga pemeliharaan. Firdana, Rifaldy, Abdillah, dan Ilham (2025) dalam penelitian mereka juga menggarisbawahi bahwa pengelolaan data siswa yang masih dilakukan secara manual sering menimbulkan masalah, seperti lambatnya pelayanan, pengulangan data, hingga kesulitan dalam penyusunan laporan, sehingga diperlukan sistem yang lebih terstruktur dan terintegrasi. 

Berdasarkan permasalahan tersebut, penelitian ini bertujuan merancang dan membangun Sistem Informasi Penerimaan Murid Baru (SPMB) berbasis serverless menggunakan Google Apps Script dengan model Waterfall pada SDN Kampung Bambu 1 Kabupaten Tangerang. Sistem yang dikembangkan diharapkan mampu meningkatkan efisiensi pengelolaan data, mengatasi permasalahan lonjakan akses saat pendaftaran, serta memberikan layanan yang lebih stabil, transparan, dan mudah diakses oleh pengguna. 

## **2. METODE** 

#### **2.1 Metode pengumpulan Data** 

Untuk memperoleh data yang dibutuhkan dalam penelitian ini, dilakukan beberapa teknik pengumpulan data sebagai berikut: 

- **a. Observasi** 

Observasi dilakukan secara langsung di SDN Kampung Bambu 1 Kabupaten Tangerang untuk mengetahui proses Sistem Penerimaan Murid Baru (SPMB) yang sedang berjalan. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1445 

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



Melalui kegiatan ini, peneliti mengidentifikasi alur pendaftaran serta permasalahan yang terjadi pada sistem, yaitu penggunaan server yang sama dengan website utama sekolah sehingga berpotensi mengalami penurunan performa saat terjadi lonjakan akses. 

- **b. Wawancara** 

Wawancara dilakukan dengan Bapak Ahcmad Syaeful Rachman, S.Pd. selaku operator dan administrasi sekolah pada tanggal 07 April 2026. Kegiatan ini bertujuan untuk memperoleh informasi mengenai mekanisme pelaksanaan SPMB, kendala yang dihadapi selama proses pendaftaran, serta kebutuhan sistem yang diharapkan oleh pihak sekolah. 

- **c. Studi Pustaka** 

Studi pustaka dilakukan dengan mempelajari berbagai sumber referensi seperti buku, jurnal ilmiah, dokumentasi resmi Google Apps Script, serta penelitian terdahulu yang berkaitan dengan sistem informasi penerimaan murid baru, arsitektur _serverless_ , dan metode Waterfall. Studi pustaka digunakan sebagai landasan teori dalam perancangan dan pengembangan sistem. 

- **2.2 Metode Pengembangan Sistem** 

Metode pengembangan sistem yang digunakan dalam penelitian ini adalah metode Waterfall. Metode ini dipilih karena memiliki tahapan yang sistematis dan dilakukan secara berurutan sehingga memudahkan proses pengembangan sistem. Metode Waterfall merupakan model pengembangan perangkat lunak yang terdiri atas beberapa tahapan yang saling berkaitan (Putra & Dirgahayu, 2025). Adapun tahapan Waterfall yang diterapkan dalam penelitian ini meliputi: 

- a. Analisis Kebutuhan : Mengumpulkan informasi terkait Sistem Penerimaan Murid Baru (SPMB) yang ada saat ini, termasuk observasi dan wawancara dengan pihak sekolah. 

- b. Perancangan Sistem : Membuat rancangan sistem pendaftaran siswa baru yang terpisah dari situs resmi sekolah, termasuk pengembangan proses pendaftaran, skema basis data, serta antarmuka pengguna untuk calon peserta didik dan staf administrasi. 

- c. Implementasi : Membangun sistem pendaftaran berbasis website menggunakan Google Apps Script yang bersifat _serverless_ dan terintegrasi dengan layanan Google Workspace, sehingga layanan pendaftaran tidak lagi bergantung pada server website resmi sekolah dan tetap stabil meskipun terjadi lonjakan jumlah pengunjung pada masa pendaftaran. 

- d. Pengujian :  Pengujian dilakukan terhadap fungsionalitas website dan fitur from pendafttaran murid baru untuk memastikan kualitas sistem yang dirancang. 

## **3. ANALISA DAN PEMBAHASAN** 

#### **3.1 Tinjauan Pustaka** 

|**No**|**Nama Peneliti**|**Judul Penelitian**|**Metode**<br>**Penelitian**|**Hasil**|
|---|---|---|---|---|
|1|(Setiawan, Akas<br>Bagus;<br>Hermansyah,<br>Mas'ud, 2025)|Smart Reminder: Sistem<br>Pengingat Tugas Berbasis<br>ReactJS dan Google Apps<br>Script untuk Manajemen<br>Proyek Tim|Research and<br>Development<br>(R&D)|Mampu mengembangkan suatu sistem<br>pengingat tugas yang berbasiskan cloud<br>yang menggabungkan ReactJS dengan<br>Google Apps Script, di mana data secara<br>otomatis disimpan di Google Sheets dan<br>dijadwalkan di Google Calendar. Persentase<br>kepuasan pengguna mencapai 87%.|
|2|(Haryadina Putra<br>& Dirgahayu,<br>2025)|Google App Script Untuk<br>Pengembangan Sistem<br>Informasi Laboratorium|Research and<br>Development<br>(R&D)|Mampu menciptakan sistem informasi<br>laboratorium yang menggunakan Google<br>Apps Script, yang memudahkan<br>pengelolaan data dan administrasi secara<br>terpusat tanpa memerlukan server khusus.|
|3|(Apriana, 2022)|Penerapan Metode<br>Waterfall Pada Sistem<br>Informasi Akademik|Metode Waterfall|Tahap Waterfall yang terencana dengan<br>baik mampu mengurangi kesalahan dalam|



Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1446 



**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 

|**No**|**Nama Peneliti**|**Judul Penelitian**|**Metode**<br>**Penelitian**|**Hasil**|
|---|---|---|---|---|
|||Sekolah Menengah<br>Kejuruan||fungsi dan meningkatkan efektivitas<br>layanan pendidikan di sekolah.|
|4|(Ardhiansyah,<br>Maulana; Hidayat,<br>Fauzi, 2022)|Pengembangan Sistem<br>Informasi Pelayanan<br>Kesehatan Menggunakan<br>Model Waterfall (Studi<br>Kasus: Poliklinik<br>PUSDIKLAT)|Model Waterfall|Berhasil mengembangkan sistem pelayanan<br>kesehatan digital yang mempermudah<br>pengelolaan data pasien dan administrasi<br>Poliklinik PUSDIKLAT secara terstruktur.|
|5|(Purwarto, 2026;<br>Sufaidah &<br>Hidayat, 2025)|Pemanfaatan Google<br>Sheets dan Google Apps<br>Script Sebagai Database<br>Sistem Informasi Logistik<br>Terintegrasi|Deskriptif<br>kualitatif dengan<br>pendekatan<br>eksperimen<br>laboratorium<br>perangkat lunak|Google Sheets terbukti menjadi pilihan<br>yang baik sebagai sumber data alternatif<br>untuk aplikasi berskala kecil hingga<br>menengah, dengan arus data masuk-keluar<br>logistik yang konsisten berkat pemanfaatan<br>pengkodean Google Apps Script yang<br>optimal.|



#### **3.2 Analisis Sistem Berjalan** 

Hasil dari observasi dan wawancara di SDN Kampung Bambu 1 mengungkapkan bahwa tahapan untuk Penerimaan Peserta Didik Baru (PPDB) melibatkan para siswa yang mendaftar serta pihak pengelola sekolah. Pendaftar memiliki pilihan untuk mendaftar secara daring atau luring, lalu mencetak bukti pendaftaran untuk diserahkan ke sekolah dengan membawa dokumen yang diperlukan. Selanjutnya, pihak pengelola akan meninjau dan memvalidasi data sebelum memberikan sertifikat verifikasi kepada orang tua siswa. 

Informasi mengenai hasil penerimaan siswa baru disebarluaskan melalui grup WhatsApp. Calon siswa yang dinyatakan diterima wajib melakukan registrasi ulang dengan menyerahkan bukti pendaftaran yang sudah mereka cetak sebelumnya. Proses ini menunjukkan bahwa sistem telah memanfaatkan teknologi digital, meskipun belum sepenuhnya terintegrasi. 



<!-- Start of picture text -->
a<br><!-- End of picture text -->

**Gambar 1.** Analisis Sistem Berjalan 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1447 

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



<!-- Start of picture text -->
Tema niet<br><!-- End of picture text -->

#### **3.3 Perancangan Sistem Dengan UML** 

Perancangan sistem dilakukan untuk menjelaskan kebutuhan fungsional dan alur kerja dari Sistem Informasi Penerimaan Murid Baru (SPMB) sebelum tahap penerapannya. Tujuan dari tahap ini adalah agar setiap proses yang akan dibangun sesuai dengan kebutuhan pengguna dan dapat berjalan dengan baik. 

Dalam proses perancangan sistem, digunakan Unified Modeling Language (UML) sebagai alat untuk pemodelan. UML berfungsi untuk menunjukkan interaksi antara pengguna dan sistem, alur proses, urutan komunikasi antarobjek, serta struktur kelas yang mendasari pembuatan aplikasi. Diagram yang digunakan mencakup : Activity Diagram, Use Case Diagram, Sequence Diagram, dan Class Diagram. Masing-masing diagram memiliki peran yang berbeda sehingga dapat memberikan gambaran lengkap tentang desain sistem yang sedang dikembangkan. 

- a. Activity Diagram 

Sistem yang diusulkan merupakan platform pendaftaran siswa baru yang berbasis web, yang memisahkan antara proses bagi pendaftar dan admin sekolah melalui dua tampilan yang terpisah. Seluruh langkah pendaftaran dapat dilakukan secara daring tanpa harus datang ke sekolah, yang diharapkan dapat mengurangi kerumunan orang tua di sekolah dan sekaligus mempercepat proses verifikasi data oleh pihak administrasi. 



<!-- Start of picture text -->
Wiemiat Data ‘Seleksi Pendatar<br>(Preview jawaban dan Kesesuaian Data<br>‘Wemperbarui Status "Verifikasi, Tolak atau<br>wasuemens Oo 11 [Site esa<br>Menempacan Stat ‘Pembaruan Status: ‘MembukaTab Email<br><!-- End of picture text -->

**Gambar 2.** Activity Diagram 

- b. Use Case 

_Use Case Sistem_ Penerimaan Murid Baru (SPMB) di SDN Kampung Bambu 1 melibatkan dua peran, yaitu Pendaftar dan Admin. 

Peran Pendaftar dapat mengisi formulir SPMB secara online, meng-upload berkas yang diperlukan, dan memantau status pendaftaran mereka tanpa perlu menghubungi sekolah. Pendaftar juga akan menerima email yang berisi informasi tentang hasil seleksi dari Admin. Sementara itu, peran Admin memiliki tingkat akses yang lebih tinggi dibandingkan Pendaftar. Sebelum dapat memanfaatkan berbagai fitur, Admin wajib melakukan login terlebih dahulu dan memiliki kemampuan untuk mengganti kata sandi demi menjaga keamanan akun. Setelah berhasil masuk ke sistem, Admin dapat mengelola data pendaftar 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1448 



**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 

yang diterima, melakukan seleksi terhadap calon siswa baru, dan mengirimkan notifikasi email kepada Pendaftar terkait hasil seleksi. 



<!-- Start of picture text -->
_<br>/ Cok Status J<br>Pendaftar “ ‘Admin<br><!-- End of picture text -->

**Gambar 3.** Use Case 

- c. Sequence Diagram 

   - 1) Sequence Diagram formulir Pendaftaran 

      - _Sequence Diagram_ ini menggambarkan proses interaksi pendaftar ketika mengisi formulir secara daring. Calon siswa mengunggah dokumen yang diperlukan seperti Kartu Keluarga dan Akta Kelahiran. Sistem backend menangani file tersebut dan menguploadnya ke Google Drive lalu mengembalikan URL link. Setelah seluruh data berhasil dikirim, sistem secara otomatis menjalankan fungsi generateRegNumber untuk menghasilkan nomor registrasi yang unik. Informasi pendaftar disertai tautan file kemudian disimpan secara permanen di dalam database Google Sheets, dan calon pendaftar mendapatkan konfirmasi bahwa pendaftaran telah berhasil. 



<!-- Start of picture text -->
i © @e &<br><!-- End of picture text -->

**Gambar 4.** Sequence Diagram Formulir Pendaftaran 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1449 

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



- 2) Sequence Diagram Admin Sequence Diagram Login dan Ganti _Password_ Admin ini menggambarkan langkah autentikasi yang diperlukan untuk melindungi akses ke panel administrasi. Di awal proses, Admin mengetikkan kata sandi pada layar login. Informasi ini kemudian dikirim ke backend untuk verifikasi menggunakan fungsi loginAdmin yang membandingkan masukan dengan data yang ada di ScriptProperties. Apabila kata sandi sesuai, sistem memberikan pengembalian sukses dan Admin diarahkan ke dashboard. Dalam proses penggantian kata sandi, sistem memeriksa keabsahan kredensial lama sebelum mengganti kata sandi baru ke dalam penyimpanan sistem guna menjaga keamanan dan integritas data. 



<!-- Start of picture text -->
Rackendons ScriftPropaties<br>‘Adin i H H<br>| Prosesten | : H<br>| masuian password : H<br>: loginadminieasswore) | gettroperty H<br>H caowin.passwonoy «|<br>: oredPaseword<br>' <_ Succes: ue, token) H<br>1 tampikan dashboard 7 H<br>| Proses Ganti Password | i H<br>{tame a ganctcmingassword | :<br>H: (seen 1 (ADMIN,aetronany PASSWORD) — i|<br>‘assnow temas cuban] [= ]<br><!-- End of picture text -->

**Gambar 5.** Sequence Diagram Admin 

- d. Class Diagram 

   - _Class Diagram_ Sistem Informasi Penerimaan Siswa Baru (SPMB) terdiri dari delapan kelas. Kelas AdminAuth bertanggung jawab atas autentikasi untuk admin dan terhubung dengan AdminManager yang berfungsi dalam pengelolaan semua data pendaftar, termasuk pencarian, pembaruan status, dan ekspor data. Kelas EmailPDFService memiliki tugas untuk menciptakan dan mengirim dokumen PDF kepada pendaftar yang telah terverifikasi, sedangkan Database Handler berperan sebagai penghubung utama ke tempat penyimpanan data yang digunakan oleh kedua kelas sebelumnya. Kelas Pendaftar memuat semua atribut data calon siswa dan terhubung dengan kelas OrangTua untuk menyimpan informasi mengenai orang tua atau wali, serta kelas Berkas untuk menyimpan dokumen persyaratan yang telah diunggah. Kelas FileHandler bertanggung jawab dalam proses pengunggahan file ke Google Drive dan memberikan URL akses file untuk kelas Berkas. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1450 



<!-- Start of picture text -->
JURAAL RISET<br><!-- End of picture text -->

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



<!-- Start of picture text -->
2 getBegstationsyNoneginorteg)  Onject, 06_TEMPLATEIO | Song<br>Ty3 Sintpgatestaltssyntaregcsbreatist newStaus, cater) - Object 3$ FatcemainnnrDrGenerareror FromoocsTempiateystuaentomea)weciplanemall, studentoste,B10 parsiop) : wold<br>Tompatcan Suing<br>zd i<br><!-- End of picture text -->

**Gambar 6.** Class Diagram 

#### **3.4 Perancangan Basis Data** 

Perancangan basis data dilaksanakan untuk mengatur tata letak penyimpanan informasi yang digunakan oleh Sistem Informasi Penerimaan Murid Baru (SPMB). Dalam penelitian ini, desain basis data mengandalkan _Entity Relationship Diagram (ERD)_ untuk memvisualisasikan entitas, atribut, serta relasi di antara entitas tersebut, memungkinkan proses penyimpanan dan pengelolaan data dilakukan dengan cara yang sistematis. 

Struktur basis data terdiri dari empat entitas, yaitu Admin, Pendaftar, Orangtua, dan Berkas. Entitas Admin mendokumentasikan data pengguna yang memiliki akses terhadap sistem, termasuk id, username, dan password. Entitas Pendaftar berfungsi sebagai entitas utama yang menyimpan informasi calon peserta didik, dengan NoRegistrasi sebagai primary key, serta atribut tambahan seperti Timestamp, NIK, NISN, Nama Lengkap, Tempat Lahir, Tanggal Lahir, Jenis Kelamin, Agama, Asal Sekolah, Status, dan Catatan Admin. 

Agar mendukung data pendaftaran, digunakanlah entitas Orangtua yang menyimpan rincian nama serta informasi kontak orang tua atau wali, dan entitas Berkas yang menyimpan dokumen pendukung, seperti kartu keluarga, akta kelahiran, dan foto. Entitas Orangtua dan Berkas terhubung dengan entitas Pendaftar melalui atribut NoRegistrasi sebagai foreign key, sehingga setiap data orang tua dan dokumen bisa dihubungkan dengan data pendaftar yang relevan. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1451 



**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



**Gambar 7.** Entity Relationship Diagram (ERD) 

#### **3.5 Implementasi Sistem** 

Implementasi sistem merupakan tahap penerapan hasil perancangan ke dalam bentuk aplikasi yang dapat digunakan oleh pengguna. Pada sistem informasi SPMB berbasis web ini, implementasi dilakukan dengan menggunakan bahasa pemrograman web serta integrasi database untuk menyimpan data pendaftaran secara terstruktur. 



<!-- Start of picture text -->
Cpanel (sca ron (+<br>a a o<br>wn/dal yyy 5<br><!-- End of picture text -->

**Gambar 8.** Tampilan Pendaftaran Data Diri 

Halaman data pribadi digunakan untuk menampilkan formulir pengisian data calon peserta didik. Pada halaman ini, pengguna diminta untuk mengisi informasi dasar seperti nama lengkap, NIK, NISN, tempat lahir, tanggal lahir, jenis kelamin, agama, dan asal sekolah. Halaman ini merupakan tahap pertama dalam proses pendaftaran peserta didik baru. Setelah seluruh data diisi dengan benar, pengguna dapat melanjutkan ke tahap berikutnya dengan menekan tombol Selanjutnya. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1452 



<!-- Start of picture text -->
surnat riser<br><!-- End of picture text -->

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



<!-- Start of picture text -->
@ 1222scom (scusme (usom (40<br>Dashboard Admin atreve<br>742<br>||<br>—mn<br><!-- End of picture text -->

**Gambar 9.** Tampilan Admin 

Menampilkan daftar semua pendaftar beserta status pendaftarannya. Admin memiliki kemampuan untuk melakukan pencarian, penyaringan berdasarkan status dan usia, serta melakukan verifikasi, penolakan, atau reset status pendaftaran. Selain itu, halaman ini juga memberikan ringkasan jumlah pendaftar berdasarkan status (Total, Menunggu, Terverifikasi, dan Ditolak). 



<!-- Start of picture text -->
 : eaceeer (eam (ase<br>@ CekStatus Pendataran<br>7 4 2 1<br><!-- End of picture text -->

**Gambar 10.** Tampilan Cek Status 

Tampilan halaman untuk Memeriksa Status Pendaftaran ini dapat diakses oleh mereka yang mendaftar untuk mengikuti perkembangan status pendaftaran tanpa harus menghubungi sekolah secara langsung. Ada kolom pencarian yang memungkinkan pendaftar mencari informasi berdasarkan nama atau nomor pendaftaran, serta tombol Cari dan Tampilkan Semua untuk menampilkan semua data pendaftar. Di bagian atas hasil pencarian, terdapat empat kartu ringkasan yang menunjukkan jumlah Total Pendaftar, yang Menunggu, yang Terverifikasi, dan yang Ditolak secara keseluruhan. Setiap informasi pendaftar ditampilkan dalam bentuk kartu yang berisi rincian nama, nomor pendaftaran, tanggal lahir, usia, tanggal pendaftaran, serta status pendaftaran saat ini. Di bagian bawah halaman, terdapat tombol Kembali yang memungkinkan pengguna kembali ke halaman utama. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1453 



**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



<!-- Start of picture text -->
GD rE 8K rp 0 BoM (saa) (Cee )( ee<br>Pendaftaran Berhasil!<br>SPMB- 2026-004<br><!-- End of picture text -->

**Gambar 11.** Tampilan Halaman Berhasil 

Tampilan halaman yang muncul setelah pendaftar sukses mengirimkan formulir pendaftaran. Halaman ini menampilkan simbol centang hijau dengan tulisan "Pendaftaran Berhasil! " sebagai bukti bahwa data pendaftaran telah berhasil dikirim dan diterima oleh sistem. Di bawahnya, pendaftar akan menerima Nomor Registrasi secara otomatis, seperti contoh yang terlihat pada gambar yaitu SPMB-2026-004, yang perlu disimpan untuk memeriksa status pendaftaran. Ada dua tombol di bagian bawah halaman, yaitu Cek Status untuk memantau perkembangan status pendaftaran dan Daftar Baru jika ingin mendaftar untuk calon peserta didik yang lainnya 

#### **3.6 Pengujian Sistem** 

Pengujian sistem dilakukan menggunakan metode _Black Box_ Testing dengan menguji setiap fungsi utama berdasarkan masukan dan keluaran yang dihasilkan. Berdasarkan hasil pengujian, seluruh fitur sistem berjalan sesuai dengan kebutuhan pengguna dan memperoleh status valid, sehingga sistem layak digunakan untuk mendukung proses Sistem Penerimaan Murid Baru (SPMB). 

**Tabel 1.** Testing Black Box 

|**No**|**Fitur yang Diuji**|**Skenario**<br>**Pengujian **|**Hasil yang**<br>**Diharapkan **|**Hasil**|**Status**|
|---|---|---|---|---|---|
|1|Login Admin|Login valid/tidak<br>valid|Validasi akun<br>dan dashboard|Sesuai<br>harapan|Valid|
|2|Formulir<br>Pendaftaran|Data lengkap/tidak<br>lengkap|Data diproses<br>atau validasi<br>tampil|Sesuai<br>harapan|Valid|
|3|Upload Berkas|Upload sesuai/tidak<br>sesuai|File diterima<br>atau ditolak|Sesuai<br>harapan|Valid|
|4|Review Data|Menampilkan dan<br>mengubah data|Ringkasan dan<br>edit berfungsi|Sesuai<br>harapan|Valid|
|5|Dashboard Admin|Cari, filter,<br>verifikasi|Fitur berjalan<br>normal|Sesuai<br>harapan|Valid|
|6|Kirim Email|Kirim notifikasi|Email berhasil<br>dikirim|Sesuai<br>harapan|Valid|
|7|Generate PDF|Membuat PDF|PDF berhasil<br>dibuat|Sesuai<br>harapan|Valid|
|8|Cek Status|Cari berdasarkan<br>nomor/nama|Status<br>ditampilkan|Sesuai<br>harapan|Valid|



Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1454 

**JRIIN : Jurnal Riset Informatika dan Inovasi Volume 4, No. 5 Tahun 2026 ISSN 3025-0919 (media online) Hal 1444-1455** 



## **4. KESIMPULAN** 

Menggunakan teknologi serverless dengan Google Apps Script di SDN Kampung Bambu 1 Kabupaten Tangerang telah menghasilkan sejumlah penemuan signifikan. Sistem SPMB dapat dirancang secara terpisah dari situs utama sekolah menggunakan Google Apps Script sebagai backend, sehingga proses pendaftaran tidak lagi terikat pada server website resmi SDN Kampung Bambu 1. Metode ini juga berhasil menghilangkan masalah utama yang kerap terjadi setiap kali pendaftaran dibuka. Struktur serverless yang diterapkan terbukti efektif dalam menangani peningkatan jumlah trafik saat pendaftaran berlangsung. Sistem ini tetap berfungsi dengan baik ketika diakses oleh banyak pengguna secara bersamaan, dan pengujian fungsi menunjukkan tidak adanya penurunan performa atau masalah downtime meskipun jumlah akses meningkat meningkat. Selain itu, proses pendaftaran menjadi lebih mudah diakses oleh calon siswa dan orang tua, karena semua langkah, mulai dari pengisian formulir empat langkah (Data Pribadi, Orang Tua & Alamat, Unggah Berkas, serta Tinjau & Kirim), unggah berkas persyaratan, hingga pemberitahuan hasil seleksi melalui email, bisa dilakukan secara daring tanpa perlu ke sekolah. 

Dari perspektif administratif, sistem ini juga meningkatkan efisiensi kerja bagi pihak sekolah. Dashboard admin yang tersedia memungkinkan staf untuk mencari, memfilter, memverifikasi atau menolak status pendaftar baik secara individu maupun massal, serta mengekspor laporan data, yang mempercepat proses seleksi dan rekapitulasi data pendaftar. 

## **REFERENCES** 

- Andaman, A. R., Aziezah, N., & Yulianti, W. (2025). Implementation of Google Sites and Script Apps for integrated information system. _Melek IT: Information Informatics Journal, 11_ (2). 

Apriana, V. (2022). Penerapan metode waterfall pada sistem informasi akademik sekolah menengah kejuruan. _AKASIA (Artikel Ilmiah Sistem Informasi Akutansi), 2_ (1). 

- Arief, S. F., & Sugiarti, Y. (2022). Literature review: Analisis metode perancangan sistem informasi akademik berbasis web. _Jurnal Ilmiah Ilmu Komputer Fakultas Ilmu Komputer Universitas Al Asyariah Mandar_ . 

- Atmaja, A. S., Sidabalok, A. S., & Raihan, M. (2024). Perancangan sistem informasi penerimaan peserta didik baru (PPDB) berbasis web. _Jurnal Komputer Teknologi Informasi_ , 515–523. 

- Basten, I., & Ardhiansyah, M. (2022). Perancangan sistem informasi desa berbasis web menggunakan model waterfall (Studi kasus Desa Banjarsari Kabupaten Lebak). _Jurnal Sains, Teknologi, dan Masyarakat, 2_ (2), 147–156. 

- Firdana, I. Z., Rifaldy, R., Abdillah, R. F., & Ilham, F. (2025). Implementasi model waterfall dalam perancangan sistem informasi PPDB di Pondok Pesantren Bina Insan Mulia. _JRRIN: Jurnal Riset Informatika dan Inovasi, 3_ (4). 

- Hidayat, F., & Ardhiansyah, M. (2022). Pengembangan sistem informasi pelayanan kesehatan menggunakan model waterfall (Studi kasus: Poliklinik PUSDIKLAT). _Jurnal Sains, Teknologi, dan Masyarakat, 2_ (2). 

- Nasser, A. A., Arifudin, O., & Barlian, U. C. (2021). Sistem penerimaan siswa baru berbasis web dalam meningkatkan mutu siswa di era pandemi. _BIORMATIKA: Jurnal Ilmiah Fakultas Keguruan dan Ilmu Pendidikan, 7_ , 100–109. 

- Putra, B. A. F. H., & Dirgahayu, R. T. (2025). Google App Script untuk pengembangan sistem informasi laboratorium. _JATISI: Jurnal Teknik Informatika dan Sistem Informasi, 12_ (1), 59–75. 

- Setiawan, A. B., & Hermansyah, M. (2025). Smart Reminder: Sistem pengingat tugas berbasis ReactJS dan Google Apps Script untuk manajemen proyek tim. _Jurnal Media Informatika, 6_ (6), 2934–2943. 

Dwi Anisa | <u>https://jurnalmahasiswa.com/index.php/jriin</u> | Page 1455 

