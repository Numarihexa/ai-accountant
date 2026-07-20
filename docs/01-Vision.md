# AI Accountant Vision

**Version:** 1.0 (Draft)  
**Status:** Draft  
**Owner:** Rizky  
**Reviewer:** ChatGPT  
**Last Updated:** 20 Juli 2026

---

# 1. Product Vision

Membangun AI Accountant yang mampu bekerja sebagai akuntan profesional bagi UMKM Indonesia melalui WhatsApp, sehingga pemilik usaha dapat mencatat transaksi, memahami kondisi keuangan, dan mengambil keputusan bisnis tanpa harus memiliki latar belakang akuntansi.

---

# 2. Product Mission

1. Mengotomatisasi pembukuan UMKM.

2. Menjadi partner akuntansi yang selalu tersedia.

3. Membantu pemilik usaha mengambil keputusan.

4. Menjadi fondasi digitalisasi keuangan UMKM.

---

# 3. Target User

Target pengguna versi pertama adalah:

- UMKM Perdagangan
- UMKM Jasa
- UMKM Kuliner
- UMKM Retail
- UMKM Kontraktor Skala Kecil

---

# 4. Problem Statement

Banyak UMKM mengalami kesulitan karena:

- Tidak memahami akuntansi.
- Tidak memiliki akuntan.
- Tidak memiliki waktu mencatat transaksi.
- Tidak mengetahui kondisi laba maupun arus kas.
- Pembukuan sering terlambat atau tidak dilakukan sama sekali.

---

# 5. Solution

AI Accountant menyediakan layanan akuntansi melalui WhatsApp.

Pengguna cukup mengirim pesan seperti:

"Saya membeli bahan baku Rp2.500.000 secara transfer."

AI tidak langsung membuat jurnal.

AI akan:

1. Memahami konteks transaksi.

2. Memvalidasi informasi yang tersedia.

3. Mengajukan pertanyaan apabila data belum cukup.

4. Menentukan akun berdasarkan COA.

5. Membuat jurnal.

6. Memperbarui laporan.

7. Menjelaskan hasil kepada pengguna.

---

# 6. Product Principles

AI Accountant harus:

1. Mengutamakan ketepatan dibanding kecepatan.
2. Tidak mengarang transaksi maupun jurnal.
3. Selalu menjelaskan alasan pencatatan.
4. Meminta klarifikasi apabila informasi belum cukup.
5. Mengikuti prinsip akuntansi Indonesia.
6. Memberikan penjelasan yang mudah dipahami pemilik UMKM.

---

# 7. Non Goals (Versi 1)

Versi pertama belum mencakup:

- ERP
- Manajemen Gudang
- Purchase Order
- Human Resource
- Payroll Kompleks
- Manufacturing
- Multi Currency
- Konsolidasi Grup Perusahaan

---

# 8. Success Metrics

Versi pertama dianggap berhasil apabila AI mampu:

- 100 UMKM aktif.

- Akurasi klasifikasi transaksi ≥95%.

- 90% transaksi dapat diproses tanpa intervensi manusia.

- Laporan keuangan dapat dihasilkan secara otomatis.

- Kepuasan pengguna minimal 4,5/5.

---

# 9. MVP Features

Versi pertama memiliki kemampuan:

- Pencatatan transaksi melalui WhatsApp.
- Jurnal otomatis.
- Buku Besar.
- Neraca Saldo.
- Laporan Laba Rugi.
- Neraca.
- Arus Kas sederhana.
- Analisis sederhana.

---

# 10. Long-term Vision

Menjadi AI Accountant terpercaya bagi jutaan UMKM Indonesia yang mampu berperan sebagai Bookkeeper, Financial Analyst, Tax Assistant, dan Business Advisor melalui percakapan alami.

# 11. Core Philosophy

AI Accountant bukan software akuntansi.

AI Accountant adalah seorang akuntan digital.

Setiap keputusan yang diambil harus mengikuti cara berpikir seorang akuntan profesional.

AI harus memahami transaksi terlebih dahulu, kemudian melakukan pencatatan, melakukan validasi, dan terakhir menjelaskan hasilnya kepada pengguna.

Tujuan AI bukan sekadar menghasilkan jurnal, tetapi membantu pemilik usaha memahami kondisi keuangannya.
Ketika AI tidak yakin, AI harus bertanya.

# 12. Product Scope
Yang dilakukan AI

✓ Mencatat transaksi

✓ Membuat jurnal

✓ Menyusun laporan

✓ Menjawab pertanyaan keuangan

✓ Memberikan insight sederhana

──────────────

Yang tidak dilakukan AI

✗ Mengambil keputusan bisnis

✗ Menyetujui pembayaran

✗ Menandatangani laporan

✗ Mengubah transaksi tanpa izin

✗ Menghapus histori

# 13. AI Promise

Kami percaya bahwa setiap UMKM berhak memiliki akses kepada akuntan profesional.

AI Accountant hadir bukan untuk menggantikan manusia,
tetapi untuk membuat layanan akuntansi menjadi lebih mudah,
lebih cepat,
lebih terjangkau,
dan tetap dapat dipercaya.

---

# Decision Log

## D-001

Keputusan:
AI Accountant berinteraksi melalui WhatsApp sebagai antarmuka utama.

Alasan:
WhatsApp adalah aplikasi komunikasi yang paling umum digunakan oleh UMKM Indonesia.

Dampak:
Seluruh desain percakapan dan kemampuan AI harus dioptimalkan untuk komunikasi berbasis chat.

Status:
Approved
