# AI Accountant Accounting Rules

**Version:** 1.0 (Draft)
**Status:** Draft
**Owner:** Rizky
**Reviewer:** ChatGPT
**Last Updated:** 20 Juli 2026

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh aturan akuntansi yang digunakan oleh AI Accountant dalam mengambil keputusan.

Reasoning Engine hanya boleh membuat jurnal berdasarkan aturan yang terdapat pada dokumen ini dan dokumen pendukung yang telah berstatus **Approved**.

Accounting Rules merupakan sumber utama logika akuntansi AI Accountant.

---

# 2. Objectives

Accounting Rules bertujuan untuk:

- Menjamin konsistensi pencatatan.
- Mengurangi halusinasi AI.
- Menjadi dasar seluruh jurnal.
- Menjamin setiap keputusan dapat dijelaskan.
- Memastikan laporan keuangan sesuai prinsip akuntansi.

---

# 3. Accounting Principles

Dalam setiap transaksi AI harus mengikuti prinsip berikut.

1. Substance Over Form
2. Going Concern
3. Accrual Basis
4. Historical Cost
5. Matching Principle
6. Consistency
7. Prudence
8. Materiality
9. Faithful Representation

Apabila terdapat konflik, AI harus meminta klarifikasi.

---

# 4. Rule Evaluation Pipeline

```text
Transaction
      │
      ▼
Intent Detection
      │
      ▼
Entity Extraction
      │
      ▼
Company Memory
      │
      ▼
Accounting Rules
      │
      ▼
COA Mapping
      │
      ▼
Journal Validation
      │
      ▼
Journal Engine
```

AI tidak boleh melewati pipeline ini.

---

# 5. Rule Priority

Apabila terdapat konflik aturan, AI menggunakan urutan berikut.

1. User Confirmation
2. Company Accounting Policy
3. Accounting Rules
4. COA Standard
5. General Accounting Knowledge

Prioritas lebih tinggi selalu mengalahkan prioritas di bawahnya.

---

# 6. Rule Categories

Accounting Rules dibagi menjadi beberapa kelompok.

- Asset Rules
- Liability Rules
- Equity Rules
- Revenue Rules
- Expense Rules
- Inventory Rules
- Fixed Asset Rules
- Depreciation Rules
- Adjustment Rules
- Closing Rules

---

# 7. Asset Rules

AI mencatat sebagai aset apabila:

- dikendalikan perusahaan;
- memberikan manfaat ekonomi di masa depan;
- nilai dapat diukur secara andal.

Jika tidak memenuhi ketiga syarat tersebut, transaksi tidak boleh dicatat sebagai aset.

---

# 8. Liability Rules

Liabilitas diakui apabila:

- terdapat kewajiban saat ini;
- berasal dari transaksi masa lalu;
- penyelesaiannya mengurangi sumber daya perusahaan.

---

# 9. Revenue Rules

Pendapatan diakui apabila:

- hak memperoleh pendapatan telah timbul;
- transaksi telah terjadi;
- nilai dapat diukur.

AI tidak boleh mengakui pendapatan yang belum diperoleh.

---

# 10. Expense Rules

Beban diakui apabila:

- manfaat ekonomi telah dikonsumsi;
- berkaitan dengan pendapatan;
- telah terjadi kewajiban.

---

# 11. Capital vs Expense Decision

Apabila AI menerima transaksi pembelian, AI harus mengevaluasi:

```text
Apakah manfaat > 1 periode?

      │
 ┌────┴─────┐
 │          │
Ya        Tidak
 │          │
 ▼          ▼
Asset     Expense
```

Apabila belum yakin, AI wajib meminta klarifikasi.

---

# 12. Inventory Rules

Persediaan dicatat apabila:

- dimiliki untuk dijual;
- digunakan dalam proses produksi;
- digunakan sebagai bahan baku.

Metode penilaian mengikuti Company Memory.

Contoh:

FIFO

Average

FEFO (bila relevan)

---

# 13. Fixed Asset Rules

Aset tetap harus:

- digunakan untuk operasional;
- memiliki manfaat lebih dari satu periode;
- memenuhi nilai kapitalisasi perusahaan.

Apabila nilai kapitalisasi belum tersedia, AI harus menggunakan Company Memory atau meminta klarifikasi.

---

# 14. Depreciation Rules

Penyusutan mengikuti kebijakan perusahaan.

Contoh metode:

- Garis Lurus
- Saldo Menurun
- Unit Produksi

AI tidak boleh menentukan metode sendiri.

---

# 15. Journal Rules

Setiap jurnal wajib memenuhi:

- Debit = Kredit
- COA valid
- Periode benar
- Mata uang benar
- Tidak duplikat
- Referensi transaksi tersedia

---

# 16. COA Mapping Rules

Seluruh transaksi harus dipetakan ke akun COA.

Contoh:

| Jenis Transaksi | COA |
|-----------------|-----|
| Penjualan | Pendapatan |
| Pembelian ATK | Beban ATK |
| Pembelian Laptop | Aset Tetap |
| Setoran Modal | Modal Pemilik |

COA Mapping menggunakan COA perusahaan apabila tersedia.

---

# 17. Validation Rules

Sebelum jurnal dibuat AI harus memvalidasi:

✓ Entity lengkap

✓ Company Policy

✓ Accounting Rules

✓ COA

✓ Journal Balance

✓ Duplicate Detection

✓ Accounting Period

---

# 18. Clarification Rules

AI wajib bertanya apabila:

- metode pembayaran tidak diketahui;
- tujuan transaksi tidak jelas;
- terdapat dua kemungkinan akun;
- transaksi bertentangan dengan kebijakan perusahaan;
- nilai transaksi tidak lengkap.

AI tidak boleh membuat asumsi.

---

# 19. Exception Handling

Apabila ditemukan kondisi berikut:

- transaksi tidak lazim;
- transaksi melanggar aturan;
- kebijakan perusahaan tidak tersedia;
- confidence rendah;

AI harus menghentikan proses pencatatan dan meminta klarifikasi.

---

# 20. Explainability Rules

Setiap keputusan harus dapat dijelaskan.

AI wajib mampu menjelaskan:

- aturan yang digunakan;
- alasan memilih akun;
- alasan jurnal;
- dampak terhadap laporan keuangan.

---

# 21. Rule Confidence

| Confidence | Action |
|------------|--------|
|95–100%|Lanjut|
|80–94%|Lanjut dengan penjelasan|
|60–79%|Klarifikasi|
|<60%|Stop|

---

# 22. Rule Logging

Setiap keputusan harus menghasilkan log.

Minimal berisi:

- Timestamp
- Rule ID
- Rule Name
- Confidence
- Input
- Output
- Journal
- User Confirmation

---

# 23. Rule Versioning

Setiap aturan memiliki:

- Rule ID
- Version
- Effective Date
- Status
- Owner
- Reviewer
- Change History

Reasoning Engine hanya boleh menggunakan rule berstatus **Active**.

---

# 24. Rule Lifecycle

```text
Draft
      │
      ▼
Review
      │
      ▼
Approved
      │
      ▼
Active
      │
      ▼
Deprecated
      │
      ▼
Archived
```

---

# 25. Rule Dependency

Accounting Rules bergantung pada:

- Company Memory
- Accounting Knowledge Framework
- COA
- PSAK
- Company Policy
- Reasoning Engine

Apabila salah satu dependency tidak tersedia, AI harus meminta klarifikasi.

---

# 26. Rule Boundaries

AI tidak boleh:

- mengarang aturan;
- mengubah aturan tanpa persetujuan;
- menggunakan rule yang deprecated;
- mengabaikan Company Policy;
- mengabaikan konfirmasi pengguna.

---

# 27. Example Rule

## Rule ID

AR-REV-001

### Nama

Revenue Recognition

### Trigger

Penjualan Barang

### Condition

- Barang telah diserahkan
- Nilai diketahui
- Hak pendapatan telah timbul

### Journal

Debit Piutang/Kas

Kredit Pendapatan

### Explainability

Pendapatan diakui karena hak perusahaan atas pendapatan telah timbul setelah barang diserahkan kepada pelanggan.

---

# 28. Rule Relationship

```text
User
      │
      ▼
Conversation
      │
      ▼
Intent
      │
      ▼
Entity Extraction
      │
      ▼
Company Memory
      │
      ▼
Accounting Rules
      │
      ▼
COA Mapping
      │
      ▼
Reasoning Engine
      │
      ▼
Journal Engine
      │
      ▼
Ledger
      │
      ▼
Financial Statements
```

---

# 29. Future Rule Modules

Framework ini akan berkembang menjadi modul berikut.

- Revenue Recognition Rules
- Expense Recognition Rules
- Inventory Rules
- Fixed Asset Rules
- Depreciation Rules
- Tax Rules
- Foreign Currency Rules
- Leasing Rules
- Construction Contract Rules
- Manufacturing Rules
- Financial Instrument Rules
- Closing & Adjustment Rules

---

# 30. Relationship With Other Documents

```text
Vision
      │
      ▼
Persona
      │
      ▼
Conversation Design
      │
      ▼
Intent Catalog
      │
      ▼
Company Memory
      │
      ▼
Accounting Knowledge Framework
      │
      ▼
Accounting Rules
      │
      ▼
COA Master
      │
      ▼
Reasoning Engine
      │
      ▼
Journal Engine
      │
      ▼
Ledger
      │
      ▼
Financial Statements
```

Accounting Rules merupakan pusat logika akuntansi yang digunakan oleh Reasoning Engine.

---

# Decision Log

## D-008

### Keputusan

Seluruh jurnal AI Accountant harus dihasilkan berdasarkan Accounting Rules yang telah tervalidasi.

### Alasan

Pemisahan antara Reasoning Engine dan Accounting Rules memastikan bahwa logika berpikir AI terpisah dari aturan akuntansi, sehingga sistem menjadi lebih mudah diaudit, diperbarui, dan dikembangkan.

### Dampak

AI Accountant menghasilkan jurnal yang konsisten, transparan, dapat dijelaskan, dan mengikuti kebijakan akuntansi perusahaan tanpa bergantung pada asumsi model bahasa.

### Status

Draft
