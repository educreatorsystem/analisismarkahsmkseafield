# Sistem Analisis Markah SMK Seafield

## Cara publish di GitHub Pages

1. Ekstrak ZIP ini pada komputer.
2. Muat naik `index.html`, `.nojekyll` dan `README.md` ke bahagian utama repositori GitHub. Pastikan `index.html` berada terus dalam repositori, bukan di dalam subfolder.
3. Buka **Settings > Pages**. Pilih **Deploy from a branch**, branch **main** dan folder **/(root)**, kemudian tekan **Save**.
4. Selepas penerbitan selesai, buka pautan GitHub Pages yang dipaparkan.

## Log masuk

- Guru: pilih **Guru**, kemudian masukkan kata laluan `GuruSMK Seafield` untuk mengakses semua tab.
- Ibu bapa: pilih **Ibu Bapa**, kemudian masukkan nombor kad pengenalan anak yang wujud dalam Google Sheet. Tanda sempang dibenarkan.
- Ibu bapa boleh memilih pentaksiran, melihat slip anak dan mencetak atau menyimpan slip sebagai PDF.

## Konfigurasi

Nama sekolah, lencana, ID Google Sheet, URL Apps Script dan ketiga-tiga URL CSV telah ditetapkan mengikut maklumat yang diberikan. Tidak perlu menampal URL sekali lagi.

Gunakan deployment Apps Script sedia ada pada URL baharu yang diberikan. Tiada fail Apps Script baharu diperlukan untuk pertukaran konfigurasi ini. Deployment tersebut perlu menyokong permintaan `action=saveMarks` dan `payload` JSON seperti sistem asal. Semua CSV perlu tersedia sebagai CSV melalui Publish to web.

Sistem memerlukan capaian internet untuk membaca Google Sheet, menghantar markah serta memuatkan gaya dan fon luaran.

## Nota keselamatan

Log masuk dalam fail HTML ini mengawal paparan sahaja. CSV diterbitkan secara awam dan endpoint simpanan menggunakan kaedah asal. Perlindungan data sebenar memerlukan pengesahan dan kebenaran akses pada pelayan.
