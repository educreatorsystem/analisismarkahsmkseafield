# Sistem Analisis Markah SMK Seafield

## Cara publish di GitHub Pages

1. Ekstrak ZIP ini pada komputer.
2. Muat naik `index.html`, `.nojekyll` dan `README.md` ke bahagian utama repositori GitHub. Pastikan `index.html` berada terus dalam repositori, bukan di dalam subfolder.
3. Buka **Settings > Pages**. Pilih **Deploy from a branch**, branch **main** dan folder **/(root)**, kemudian tekan **Save**.
4. Selepas penerbitan selesai, buka pautan GitHub Pages yang dipaparkan.

## Log masuk

- Guru: pilih **Guru**, kemudian masukkan kata laluan `GuruSMK Seafield` untuk mengakses semua tab.
- Ibu bapa: pilih **Ibu Bapa**, kemudian masukkan emel DELIMa penuh anak seperti dalam rekod sekolah.
- Ibu bapa boleh memilih pentaksiran, melihat slip anak dan mencetak atau menyimpan slip sebagai PDF.

## Konfigurasi

Dalam tab senarai murid yang diterbitkan sebagai CSV, pastikan terdapat lajur **ID DELIMa** dan isi alamat emel penuh bagi setiap murid. Gunakan satu alamat emel bagi setiap murid supaya sistem dapat memilih slip yang betul.

Nama sekolah, lencana, ID Google Sheet, URL Apps Script dan ketiga-tiga URL CSV telah ditetapkan mengikut maklumat yang diberikan. Tidak perlu menampal URL sekali lagi.

Gunakan deployment Apps Script sedia ada pada URL baharu yang diberikan. Tiada fail Apps Script baharu diperlukan untuk pertukaran konfigurasi ini. Deployment tersebut perlu menyokong permintaan `action=saveMarks` dan `payload` JSON seperti sistem asal. Semua CSV perlu tersedia sebagai CSV melalui Publish to web.

Sistem memerlukan capaian internet untuk membaca Google Sheet, menghantar markah serta memuatkan gaya dan fon luaran.

## Analisis rekod markah daripada Google Sheet

Sistem mengambil rekod markah daripada CSV setiap kali pengguna log masuk. Apabila terdapat markah, paparan guru dibuka pada **Analisis Individu** dengan kelas dan pentaksiran yang mempunyai rekod. Tab **Prestasi MP**, **Kedudukan Murid** dan **Pelaporan (Slip)** menggunakan rekod yang sama. Log keluar dan log masuk semula untuk memuatkan perubahan pada Google Sheet.

Lajur **Kelas** dan **Tingkatan** digunakan bersama. Contohnya `EDISON` dengan tingkatan `5` dipadankan kepada `5 EDISON`. Rekod bagi murid, pentaksiran dan subjek yang sama dikira sekali. Jika cap masa boleh dibaca, rekod terbaharu digunakan. Jika cap masa tidak dapat dibandingkan, baris terakhir yang sepadan digunakan.

## Slip peperiksaan

Slip menggunakan jadual Bil., Mata Pelajaran, Markah dan Gred. Ringkasan selepas jadual memaparkan bilangan subjek, pecahan gred, gred purata, jumlah markah, keputusan dan peratus. Dalam cetakan A4, setiap murid bermula pada muka surat baharu.

Lajur pilihan pada tab senarai murid ialah **NO KAD PENGENALAN**, **JANTINA**, **NAMA GURU KELAS** dan **ULASAN GURU KELAS**. Nama guru kelas, jantina dan No. KP dipaparkan sebagai sengkang jika kosong. Untuk tajuk sesi, isi lajur pilihan **SESI AKADEMIK** pada tab pentaksiran dan subjek, menggunakan nilai seperti `2025/2026`. Ulasan automatik dipaparkan jika tiada ulasan guru kelas yang direkodkan.

## Nota keselamatan

Log masuk dalam fail HTML ini mengawal paparan sahaja. CSV diterbitkan secara awam dan endpoint simpanan menggunakan kaedah asal. Perlindungan data sebenar memerlukan pengesahan dan kebenaran akses pada pelayan.
