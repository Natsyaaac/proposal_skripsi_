RANCANG BANGUN SISTEM INFORMASI PENERIMAAN MURID BARU (SPMB) DAN PENGELOLAAN DATA PESERTA DIDIK BARU BERBASIS WEBSITE MENGGUNAKAN METODE WATERFALL PADA 
MIS MIFTAHUL HUDA




SKRIPSI
















OLEH
FAIZ ILYAS ZULKARNAEN
NPM 23430082





PROGRAM STUDI ILMU KOMPUTER FAKULTAS ILMU KOMPUTER UNIVERSITAS MUHAMMADIYAH METRO 2026























	










DAFTAR ISI

 BAB I 
PENDAHULUAN
A	Latar Belakang Masalah
Rancang bangun terdiri dari dua pekerjaan yang berurutan, yaitu merancang dan membangun. Merancang berarti menyusun gambaran sistem sebelum ada kode program, sedangkan membangun berarti menerjemahkan gambaran itu menjadi sistem yang berjalan. Dalam penelitian ini, rancang bangun berlaku pada sistem informasi penerimaan murid baru (SPMB) dan pengelolaan data peserta didik, yaitu sistem yang mengatur alur pendaftaran calon murid, pengisian formulir, unggah berkas, verifikasi kelengkapan, pembentukan data peserta didik baru dan usulan pembagian kelas. Peneliti merancang struktur basis data, alur sistem, dan tampilan halaman, lalu membangun rancangan itu menjadi website dengan Next.js, Supabase, dan Vercel.
Wahyu pertama yang diterima Nabi Muhammad SAW dibuka dengan perintah membaca:  
ٱقْرَأْ بِٱسْمِ رَبِّكَ ٱلَّذِى خَلَقَ ﴿١﴾ خَلَقَ ٱلْإِنسَٰنَ مِنْ عَلَقٍ ﴿٢﴾ ٱقْرَأْ وَرَبُّكَ ٱلْأَكْرَمُ ﴿٣﴾ ٱلَّذِى عَلَّمَ بِٱلْقَلَمِ ﴿٤﴾
عَلَّمَ ٱلْإِنسَٰنَ مَا لَمْ يَعْلَمْ ﴿٥﴾
(Q.S. Al-‘Alaq: 1-5)
Artinya: “Bacalah dengan (menyebut) nama Tuhanmu yang menciptakan! ﴿١﴾ Dia menciptakan manusia dari segumpal darah. ﴿٢﴾Bacalah! Tuhanmulah Yang Mahamulia, ﴿٣﴾yang mengajar (manusia) dengan pena. ﴿٤﴾Dia mengajarkan manusia apa yang tidak diketahuinya. ﴿٥﴾”

Madrasah ibtidaiyah menjalankan perintah belajar itu bagi anak usia sekolah dasar, dan anak masuk madrasah melalui penerimaan murid baru. Enam tahun belajar anak di madrasah dimulai dari pendaftaran itu. Sekolah mencatat setiap calon murid yang mendaftar, dan catatan tersebut menjadi data peserta didik yang sekolah kelola selama anak belajar di sana. Penelitian ini membahas cara sekolah mencatat pendaftar dan mengelola data mereka setelah diterima. 
MIS Miftahul Huda, madrasah ibtidaiyah swasta, berada di Desa Tunggul Pawenang, Kecamatan Adiluwih, Kabupaten Pringsewu, Lampung. Menurut A. Syahidi selaku panitia pendaftaran (20 November 2026), sekolah menerima 60 pendaftar pada penerimaan 2026-2027. Pendaftar masuk lewat dua jalur, 15 pendaftar mengisi formulir pada halaman pendaftaran di blog sekolah, sedangkan 45 pendaftar datang langsung ke sekolah. Pengamatan peneliti menunjukkan bahwa halaman pendaftaran di blog memuat daftar persyaratan dan formulir data calon siswa serta orang tua atau wali. Menurut A. Syahidi (20 November 2026), data dari formulir itu masuk ke server madrasah, dan panitia dapat mengunduh atau menyalinnya ke Excel. Setelah pendaftar mengirim formulir, blog menampilkan ucapan selamat dan bukti pendaftaran yang dapat dicetak. Halaman itu tidak menyediakan formulir untuk mengunggah berkas, sehingga 15 pendaftar jalur blog tetap menyerahkan berkasnya langsung ke sekolah.
Jalur langsung menjadi pilihan 45 dari 60 pendaftar. Mereka datang ke sekolah untuk meminta formulir dan mengumpulkan berkas, sehingga sebagian besar pendaftar masih mendaftar dengan cara manual. Orang tua memilih cara ini karena pengumpulan berkas dan pengisian data siswa dan orang tua siswa selesai dalam sekali datang. Semua pendaftar, baik dari blog maupun yang datang langsung, menyerahkan berkas fisik ke sekolah, fotokopi ijazah, kartu keluarga, akta kelahiran, KTP orang tua atau wali, dan kartu lain seperti PKH, KIS, dan KKS. Panitia memindai berkas itu lalu mengarsipkannya. Pengumpulan berkas menjadi hambatan utama bagi panitia, orang tua atau wali kadang lupa membawa berkas atau beralasan berkasnya tertinggal, sehingga penginputan data peserta terhambat, dan sebagian fotokopi yang masuk tidak jelas atau buram. 
Setelah berkas terarsip, panitia memasukkan data pendaftar ke Excel. Akibatnya, data pendaftar tersebar di tiga tempat, blog, berkas fisik, Excel. Panitia memindahkannya dengan mengunduh atau menyalin data dari blog ke Excel, dan dengan menginput data dari berkas fisik ke Excel. Sekolah membagi murid ke dalam kelas setelah data pendaftar masuk. Pembagian itu mengelompokkan murid berdasarkan asal TK/RA dan jenis kelamin, agar jumlah murid dan komposisi laki-laki dan perempuan merata antarkelas, dengan batas 30 murid per kelas. Pada penerimaan 2026-2027, sekolah membagi 60 murid ke dalam 2 kelas.
Pengamatan dan wawancara menunjukkan empat kelemahan pada pendaftaran yang berjalan di MIS Miftahul Huda. Pertama, halaman pendaftaran di blog tidak menyediakan unggah berkas, sehingga pendaftaran daring belum tuntas dan pendaftar tetap harus ke sekolah. Kedua, 45 dari 60 pendaftar mendaftar dengan cara manual dan datang ke sekolah untuk mengambil formulir. Ketiga, kelengkapan berkas bergantung pada orang tua yang membawa fotokopi fisik, dan sebagian fotokopi yang masuk tidak jelas. Keempat, data pendaftar tersebar di tiga tempat dan panitia memindahkannya ke Excel, sedangkan sekolah belum memiliki sistem informasi penerimaan murid baru dan pengelolaan data peserta didik baru yang terintegrasi. Kelemahan itu berdampak pada panitia dan orang tua. Penginputan data peserta terhambat ketika orang tua atau wali tidak membawa berkas, dan panitia memindahkan data dari dua sumber ke satu file Excel. Orang tua harus datang ke sekolah untuk menyerahkan berkas, termasuk orang tua dari 15 pendaftar yang sudah mengisi formulir di blog.
Sistem informasi penerimaan murid baru dan pengelolaan data peserta didik baru berbasis website menyatukan pendaftaran dari kedua jalur dalam satu sistem, sehingga panitia mencatat semua pendaftar di satu tempat. Orang tua mengisi formulir dan mengunggah berkas dari rumah, sedangkan admin mencatat pendaftar yang datang ke sekolah ke sistem yang sama. Admin memeriksa kelengkapan berkas di satu dashboard, dan orang tua mendapat informasi melalui pesan WhatsApp. Sistem menyimpan data pendaftar yang sudah diverifikasi di basis data dan menampilkannya di website informasi peserta didik baru, dan admin dapat mengekspornya ke Excel atau CSV. Sistem juga menyusun usulan pembagian kelas berdasarkan asal TK/RA dan jenis kelamin dengan maksimal 30 murid per kelas. Admin dapat memindahkan murid antarkelas bila usulan itu perlu diubah.
Berdasarkan situasi tersebut, peneliti mengangkat penelitian berjudul “Rancang Bangun Sistem Informasi Penerimaan Murid Baru (SPMB) dan Pengelolaan Data Peserta Didik Baru Berbasis Website Menggunakan Metode Waterfall Pada MIS Miftahul Huda”. 
B	Perumusan Masalah
Bagaimana merancang dan membangun sistem informasi penerimaan murid baru (SPMB) dan pengelolaan data peserta didik baru berbasis website pada MIS Miftahul Huda?
C	Pembatasan Masalah 
Batasan masalah dalam penelitian ini sebagai berikut:
1.	Sistem melayani calon murid baru MIS Miftahul Huda, baik dari TK/RA maupun yang belum bersekolah, dengan orang tua atau wali sebagai pendaftar dan panitia sebagai admin. Sistem tidak mencakup murid lama dan murid pindahan dari sekolah lain.
2.	Peneliti membangun sistem berbasis website dengan bahasa pemrograman TypeScript, Next.js sebagai framework, Supabase sebagai basis data, layanan autentikasi login, dan penyimpanan berkas, Vercel sebagai hosting, GitHub sebagai repositori kode dan penjadwal tugas otomatis melalui GitHub Actions, Visual Studio Code sebagai IDE, Playwright sebagai alat pengujian blackbox, dan WhatsApp API sebagai saluran notifikasi ke orang tua
3.	Pendaftaran berlangsung daring oleh orang tua dan luring melalui admin, yang memasukan data pendaftar ke sistem. Sistem mencakup login, pendaftaran daring, pendaftaran luring oleh admin, unggah berkas, verifikasi kelengkapan, notifikasi WhatsApp, status pendaftaran, pembentukan data peserta didik baru, ekspor data per kelas ke Excel atau CSV. Sistem Menyusun usulan pembagian kelas berdasarkan asal TK/RA dan jenis kelamin dengan maksimal 30 murid per kelas, dan admin dapat memindahkan murid antarkelas.
4.	Sistem tidak memuat pembayaran daftar ulang sekolah tidak memungutj biaya pendaftaran, tidak mengadakan daftar ulang, dan menerima semua pendaftar. Verifikasi admin hanya memeriksa kelengkapan berkas.
 
D	Tujuan Penelitian
Tujuan peneliti dalam penelitian ini adalah merancang dan membangun sistem informasi penerimaan murid baru (SPMB) dan pengelolaan data peserta didik baru berbasis website.
E	Kegunaan Penelitian 
1.	Bagi MIS Miftahul Huda, Penelitian ini diharapkan membantu panitia pendaftaran mengumpulkan data pendaftar dari pendaftaran daring maupun luring dalam satu sistem,  pembagian kelas, dan mengekspor data tersebut menjadi file CSV 
2.	Bagi orang tua calon murid, penelitian ini diharapkan memudahkan orang tua mengunggah berkas pendaftaran melalui website, memantau status pendaftaran, dan melihat hasil penerimaan
3.	Bagi peneliti, penelitian ini diharapkan membantu peneliti mengerti tahapan metode Waterfall, yaitu analisis, perancangan, implementasi, pengujian, dan pemeliharaan, melalui pembangunan sistem yang menjawab rumusan masalah
F	Metodologi Penelitian
1.	Jenis Penelitian 
Penelitian ini menerapkan jenis penelitian kualitatif deskriptif. Anggraenita dkk. (2026: 202)  menyatakan bahwa metode deskriptif digunakan untuk "menggambarkan kondisi nyata di lapangan secara sistematis dan faktual". Berdasarkan pendapat tersebut, penelitian kualitatif deskriptif menguraikan kondisi yang diteliti dalam bentuk penerimaan murid baru di MIS Miftahul Huda melalui pengamatan langsung dan wawancara dengan A. Syahidi, selaku panitia pendaftaran. Hasilnya menjadi dasar peneliti merumuskan kebutuhan sistem SPMB.
2.	Metode Penelitian 
Peneliti mengembangkan sistem dengan Software Development Life Cycle (SDLC) metode Waterfall. Pengembang sistem informasi biasa menggunakan metodologi Software Development Life Cycle (SDLC). Metodologi ini membagi pekerjaan ke dalam beberapa tahap, dimulai dari analisis kebutuhan, perancangan desain, implementasi, dan pengujian, lalu berakhir pada pemeliharaan sistem (Azis & Voutama, 2025:2074).  
Waterfall termasuk pendekatan linier atau sekuensial dalam SDLC. Pengembang masuk ke fase berikutnya hanya setelah fase yang sedang berjalan tuntas, dan aturan itu berlaku dari fase pertama sampai terakhir(Nopem dkk., 2026: 2558) . Peneliti memakai model ini untuk membangun sistem informasi penerimaan murid baru dan pengelolaan data peserta didik baru berbasis website pada MIS Miftahul Huda. Gambar 1 menunjukkan tahapan metode Waterfall yang peneliti terapkan.


	










Asyahadi ([2025]: [5])
 	
Tahapan pengembangan sistem dalam penelitian ini: 
a.	Analisis (Analysis) 
Peneliti mengidentifikasi kebutuhan sistem lewat pengamatan dan wawancara dengan A. Syahidi selaku panitia pendaftaran, tentang alur pendaftaran murid baru yang berjalan. Hasilnya berupa kebutuhan sistem: login, pendaftaran daring, pendaftaran luring oleh admin, unggah berkas, verifikasi kelengkapan, notifikasi WhatsApp, status pendaftaran, pembentukan data peserta didik baru, usulan pembagian kelas, ekspor data per kelas ke Excel atau CSV.
b.	Perancangan (Design)
Peneliti menyusun desain sistem berdasarkan hasil analisis, yaitu struktur basis data dan alur sistem Entity Relationship Diagram (ERD),  serta tampilan antarmuka dengan rancangan halaman (mockup). Desain ini memberi gambaran sistem yang akan dibangun sebelum peneliti menulis kode 
c.	Implementasi (Coding) 
Peneliti menerjemahkan hasil perancangan ke dalam kode program. Peneliti membangun antarmuka dan fitur sistem dengan Next.js, menyimpan data dan dokumen di Supabase, dan menayangkan website melalui Vercel. Hasil tahap ini adalah website SPMB yang berjalan dan memenuhi kebutuhan pada tahap analisis
d.	Pengujian (Testing)
Peneliti menguji seluruh fitur dengan black box testing, yaitu pengujian yang memeriksa fungsi sistem dari masukan dan keluaranya tampa melihat kode program, dengan Playwright sebagai alat pengujiannya. Peneliti menguji pendaftaran, unggah berkas, verifikasi kelengkapan, notifikasi WhatsApp, status pendaftaran, pembentukan data peserta didik baru, usulan pembagian kelas, ekspor data per kelas ke Excel atau CSV dan mencatat hasil tiap fitur sebagai sesuai atau tidak sesuai.
e.	Pemeliharaan (Maintenance) 
Pemeliharaan adalah tahap terakhir metode Waterfall, yang dikerjakan setelah sistem selesai diuji. Peneliti memperbaiki kesalahan yang muncul saat sistem dipakai dan menyesuaikan sistem bila kebutuhan sekolah berubah, misalnya perubahan persyaratan atau alur pendaftaran. Peneliti mencatat setiap perbaikan dan menguji ulang bagian yang diubah sebelum sistem dipakai Kembali
G	Teknik Pengumpulan Data 
1.	Studi Lapangan 
Studi lapangan (field research) ialah pengumpulan data yang dilakukan di lapangan dengan teknik seperti observasi, wawancara, dan dokumentasi (Ahmad & Laha, 2020:65). Dalam pelaksanaannya, teknik ini dilakukan dengan menggunakan beberapa pendekatan tertentu: 
a.	Observasi
Observasi merupakan salah satu metode pengumpulan data kualitatif, yaitu peneliti mengamati fenomena yang terjadi lalu mencatat apa yang ditemukan (Utami dkk., 2025: 134).  Dalam penelitian ini, peneliti melihat sistem pendaftaran yang sudah berjalan di MIS Miftahul Huda dan mencatat proses penginputan data siswa baru. 
b.	Wawancara 
Wawancara adalah setiap situasi percakapan antara dua orang, umumnya seorang pewawancara dan seorang yang diwawancarai, yang bertujuan saling memperoleh informasi (Yusuf, 2014, dalam Sari dkk., 2025: 540). Dalam penelitian ini, peneliti mewawancarai A. Syahidi selaku panitia pendaftaran untuk mendapatkan informasi tentang permasalahan dalam proses pendaftaran siswa di MIS Miftahul Huda 
c.	Dokumentasi
Dokumentasi adalah metode pengumpulan data dengan cara mendapatkan data tentang peristiwa yang sudah berlalu Penelitian yang dirujuk memakai formulir pendaftaran, dokumen persyaratan, serta dokumentasi kegiatan dan lokasi penelitian sebagai bahan pendukung analisis dan perancangan sistem (Haki & Afriyadi, 2026:119). Peneliti memakai dokumen yang dikumpulkan di MIS Miftahul Huda yaitu, file CSV data peserta didik tahun lalu untuk menganalisis dan merancang sistem pendaftaran siswa
2.	Studi Pustaka 
Studi pustaka dikerjakan lewat kegiatan mempelajari beragam sumber rujukan, misalnya buku dan jurnal ilmiah (Anisa dkk., 2026:1446) . Pada penelitian ini, peneliti juga mempelajari dokumentasi resmi Next.js, Supabase, dan Vercel, serta penelitian terdahulu tentang sistem informasi penerimaan murid baru berbasis website dan metode Waterfall.
Data yang diperoleh dari studi pustaka berupa teori tentang sistem informasi, penerimaan murid baru, Next.js sebagai kerangka kerja pemrograman, Supabase sebagai basis data, Vercel sebagai platform penayangan, metode pengembangan Waterfall, diagram aktivitas, dan bagan alir dokumen, mockup, ERD, flowchart, dan black box testing. 
H	Sistematika Penulisan 
Peneliti Menyusun skripsi ini dalam lima bab agar pembahasan tetap terarah dan tidak keluar dari permasalahan yang dibatasi. Susunannya sebagai berikut.
BAB I PENDAHULUAN
Bab I memuat latar belakang masalah, rumusan masalah, pembatasan masalah, tujuan penelitian, kegunaan penelitian, metodologi Penelitian, Teknik Pengumpulan Data dan sistematika penulisan 
BAB II TINJAUAN PUSTAKA
Bab II menguraikan konsep yang berkaitan dengan permasalahan penelitian dan termasuk dalam ruang lingkup sistem yang diusulkan, login, pendaftaran daring, pendaftaran luring oleh admin, unggah berkas, verifikasi kelengkapan, notifikasi WhatsApp, status pendaftaran, pembentukan data peserta didik baru, usulan pembagian kelas, ekspor data per kelas ke Excel atau CSV, website, TypeScript, Next.js, database Supabase, Vercel, WhatsApp API, GitHub, Visual Studio Code, metode pengembangan perangkat lunak Waterfall, serta Blackbox Testing dengan Playwright. Peneliti mengambil uraian ini dari jurnal, buku, dan informasi di situs web.
BAB III GAMBARAN UMUM ORGANISASI
Bab III menguraikan sejarah singkat, lokasi, dan struktur organisasi MIS Miftahul Huda, kemudian analisis sistem yang berjalan, kebutuhan sistem, dan analisis dokumen.
BAB IV HASIL PENELITIAN DAN PEMBAHASAN
Bab IV menjadi bab inti. Peneliti memaparkan perancangan sistem yang diusulkan, mulai dari aliran informasi, flowchart, ERD, mockup, Unified Modeling Language (UML), diagram aktivitas, dan bagan alir dokumen, lalu rancangan database, analisis kebutuhan sumber daya, serta rancangan input dan output. Pembahasan program yang diusulkan menutup bab ini.
BAB V SIMPULAN DAN SARAN
Bab V berisi simpulan dari hasil penelitian yang sudah dirancang dan dibangun, serta saran bagi peneliti dan pembaca agar penelitian berikutnya lebih baik.
DAFTAR LITERATUR
LAMPIRAN

 

 Daftar Pustaka
Abid Athananda Azis, & Apriade Voutama. (2025). Rancangan Sistem Monitoring Siswa Berbasis Web Dengan Metode Waterfall. Jurnal Informatika dan Teknik Elektro Terapan, 13(3). https://doi.org/10.23960/jitet.v13i3.6676
Ahmad, B., & Saleh, M. (2020). Penerapan Studi Lapangan Dalam Meningkatkan Kemampuan Analisis Masalah (Studi Kasus Pada Mahasiswa Sosiologi Iisip Yapis Biak).
Anggraenita, W., Hadiwijaya, R. Z., & Syahril Sidik, G. (2026). Analisis Peran Guru Dalam Meningkatkan Motivasi Belajar Siswa (Kualitatif Deskriptif Pada Kelas Iv Sd Dalam Pembelajaran Bahasa Indonesia).
Anisa, D., Faizal, M. N., Ardiansyah, M., & Hasibuan, N. P. (2026). Rancang Bangun Sistem Informasi Penerimaan Murid Baru (SPMB) Berbasis Serverless Menggunakan Google Apps Script dengan Model Waterfall pada SDN Kampung Bambu 1 Kabupaten Tangerang. JRIIN : Jurnal Riset Informatika dan Inovasi, 4(5). https://jurnalmahasiswa.com/index.php/jriin
Asyahadi, R. T. (2025). Rancang Bangun Sistem Informasi Website Rental Mobil Samboga dengan Framework Codeigniter.
Haki, R. T., & Afriyadi, H. (2026). Perancangan Sistem Informasi Penerimaan Peserta Didik Baru (PPDB) Berbasis Web di MIS Nurul Iman Pematang Gajah Muaro Jambi. 18(2), 114–128. https://doi.org/10.53564/carvay33
Nopem, S., Harpad, B., & Zakariyya Rasyad, R. (2026). Rancang Bangun Aplikasi Pengingat Saat Teduh Harian Berbasis Android Menggunakan Model Waterfall Design and Development of an Android-Based Daily Devotional Reminder Application Using the Waterfall Model. Media Online), 6(6), 2556–2566. https://doi.org/10.47065/bulletincsr.v6i6.1392
Sekar Sari, A., Aprisilia, N., Fitriani, Y., & Kata Kunci, A. (2025). Indonesian Research Journal on Education Teknik Pengumpulan Data dalam Penelitian Kualitatif: Observasi, Wawancara, dan Triangulasi. Dalam Indonesian Research Journal on Education (Vol. 5). https://irje.org/index.php/irje
Utami, T. H., Sa’diyah, H., Metode, F. M., Data, P., Demagogi, K., & Munawwarah, F. (2025). Metode Pengumpulan Data Kualitatif. 3(3). https://doi.org/10.61166/demagogi.v3i3.79
 
