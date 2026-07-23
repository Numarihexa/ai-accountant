# AI Accountant Accounting Knowledge Framework

**Version:** 1.0 (Draft)
**Status:** Draft
**Owner:** Rizky
**Reviewer:** ChatGPT
**Last Updated:** 20 Juli 2026

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh pengetahuan yang dimiliki AI Accountant.

Reasoning Engine hanya boleh mengambil keputusan berdasarkan knowledge yang didefinisikan pada dokumen ini beserta dokumen pendukung lainnya.

---

# 2. Objectives

Accounting Knowledge Framework bertujuan untuk:

- Menjadi sumber pengetahuan utama AI.
- Menjamin konsistensi pengambilan keputusan.
- Mengurangi halusinasi AI.
- Memastikan seluruh reasoning memiliki dasar yang jelas.
- Mempermudah pengembangan kemampuan AI di masa depan.

---

# 3. Knowledge Principles

Seluruh pengetahuan AI harus:

- Akurat.
- Dapat diverifikasi.
- Konsisten.
- Mudah diperbarui.
- Memiliki sumber yang jelas.

AI tidak boleh menggunakan pengetahuan yang belum tervalidasi.

---

# 4. Three-Layer Knowledge Architecture

AI Accountant menggunakan tiga lapisan informasi sebelum mengambil keputusan.

```text
Knowledge
        │
Memory
        │
Context
        ▼
Reasoning Engine
        ▼
Decision
        ▼
Journal
```

Setiap lapisan memiliki fungsi yang berbeda dan saling melengkapi.

---

# 5. Knowledge Sources

Reasoning Engine memperoleh informasi dari tiga lapisan utama.

## Layer 1 — Knowledge

Merupakan pengetahuan umum yang berlaku untuk seluruh pengguna AI Accountant.

Contoh:

- Accounting Rules
- PSAK
- Chart of Accounts (COA) Standard
- Business Knowledge
- Financial Knowledge
- Industry Knowledge
- Internal Control Knowledge

Knowledge bersifat umum dan digunakan oleh seluruh perusahaan.

---

## Layer 2 — Memory

Merupakan informasi permanen yang dimiliki setiap perusahaan pengguna.

Contoh:

- Profil perusahaan
- Jenis usaha
- COA perusahaan
- Kebijakan akuntansi
- Metode penilaian persediaan
- Rekening bank
- Daftar supplier
- Daftar customer
- Daftar aset tetap
- Periode akuntansi
- Preferensi pengguna

Memory bersifat spesifik untuk setiap perusahaan dan akan terus diperbarui seiring penggunaan AI.

---

## Layer 3 — Context

Merupakan informasi sementara yang hanya berlaku selama percakapan berlangsung.

Contoh:

- Intent pengguna
- Transaksi yang sedang dibahas
- Informasi yang masih kurang
- Klarifikasi yang belum selesai
- Status reasoning
- Konfirmasi yang masih menunggu

Context akan diperbarui secara dinamis selama percakapan dan dapat dihapus setelah proses selesai.

---

# 6. Knowledge Hierarchy

Apabila terdapat konflik informasi, AI harus menggunakan urutan prioritas berikut.

1. Context yang telah dikonfirmasi pengguna.
2. Memory perusahaan.
3. Accounting Knowledge.
4. General Knowledge AI.

Knowledge dengan prioritas lebih tinggi selalu mengalahkan knowledge pada level di bawahnya.

---

# 7. Knowledge Categories

AI harus memiliki pengetahuan minimal mengenai:

## Business Knowledge

- Jenis usaha
- Model bisnis
- Produk
- Jasa
- Proses bisnis

---

## Accounting Knowledge

- Persamaan dasar akuntansi
- Debit dan Kredit
- Siklus akuntansi
- Jurnal
- Buku Besar
- Neraca Saldo
- Laporan Keuangan

---

## Financial Knowledge

- Pendapatan
- Beban
- Aset
- Liabilitas
- Ekuitas
- Arus Kas

---

## Tax Knowledge (Versi Berikutnya)

- PPN
- PPh
- e-Faktur
- Bukti Potong

---

## Company Knowledge

- Struktur organisasi
- Kebijakan perusahaan
- Periode akuntansi
- Struktur COA
- Rekening Bank
- Kebijakan penyusutan

---

# 7.1 Industry Knowledge

AI Accountant harus memahami karakteristik akuntansi pada berbagai jenis usaha.

Pengetahuan ini digunakan untuk membantu Reasoning Engine menentukan perlakuan akuntansi yang sesuai dengan konteks bisnis pengguna.

### UMKM Perdagangan

AI harus memahami:

- Persediaan
- Harga Pokok Penjualan (HPP)
- Supplier
- Customer
- Retur Penjualan
- Retur Pembelian

---

### UMKM Jasa

AI harus memahami:

- Pendapatan Jasa
- Work in Progress (WIP)
- Piutang Jasa
- Pendapatan Diterima di Muka

---

### UMKM Kuliner

AI harus memahami:

- Persediaan Bahan Baku
- Produksi Harian
- Waste / Penyusutan Bahan
- Food Cost
- Penjualan Tunai dan Non Tunai

---

### UMKM Kontraktor

AI harus memahami:

- Progress Proyek
- Termin Pembayaran
- Retensi
- Uang Muka Proyek
- Biaya Proyek

Jenis usaha menjadi salah satu konteks utama dalam proses reasoning karena transaksi yang sama dapat memiliki perlakuan akuntansi yang berbeda pada industri yang berbeda.

---

# 8. Knowledge Relationships

Knowledge tidak berdiri sendiri, tetapi saling berhubungan.

Contoh hubungan:

```text
Customer
      │
      ▼
Invoice
      │
      ▼
Piutang
      │
      ▼
Pembayaran
      │
      ▼
Kas
```

Reasoning Engine harus memahami hubungan antar knowledge sebelum mengambil keputusan.

---

# 9. Knowledge Retrieval

Sebelum melakukan reasoning, AI harus mengambil knowledge yang relevan.

Urutan pengambilan informasi:

1. Context
2. Company Memory
3. Accounting Rules
4. COA
5. Business Knowledge

AI tidak perlu mengambil seluruh knowledge apabila tidak relevan dengan transaksi yang sedang diproses.

Tujuan proses ini adalah meningkatkan efisiensi reasoning, mengurangi penggunaan token, dan mempercepat waktu respons.

---

# 10. Knowledge Dependencies

Reasoning Engine bergantung pada:

- Accounting Rules
- COA
- Company Memory
- Conversation Context
- Company Policies

Apabila salah satu informasi belum tersedia, AI wajib meminta klarifikasi kepada pengguna.

---

# 10.1 External Knowledge

Pada kondisi tertentu, AI Accountant dapat menggunakan sumber pengetahuan eksternal yang telah tervalidasi.

Contoh:

- PSAK terbaru
- Peraturan perpajakan
- Standar pelaporan keuangan
- Kebijakan regulator
- Pedoman resmi pemerintah

External Knowledge hanya digunakan sebagai referensi apabila:

- relevan dengan transaksi,
- telah diverifikasi,
- tidak bertentangan dengan kebijakan perusahaan.

AI tidak boleh menggunakan sumber eksternal yang belum tervalidasi sebagai dasar pengambilan keputusan.

---

# 11. Knowledge Validation

Sebelum digunakan, knowledge harus memenuhi syarat berikut.

- Benar.
- Masih berlaku.
- Konsisten dengan knowledge lainnya.
- Tidak bertentangan dengan kebijakan perusahaan.

Knowledge yang belum tervalidasi tidak boleh digunakan sebagai dasar pencatatan.

---

# 11.1 Conflict Resolution

Apabila ditemukan konflik antar sumber knowledge, AI harus menggunakan urutan prioritas berikut.

1. Informasi yang telah dikonfirmasi pengguna.
2. Kebijakan perusahaan.
3. Company Memory.
4. Accounting Rules.
5. PSAK atau regulasi yang berlaku.
6. General Knowledge AI.

Apabila konflik belum dapat diselesaikan, AI wajib meminta klarifikasi kepada pengguna sebelum melanjutkan proses reasoning.

---

# 12. Knowledge Confidence

Setiap knowledge memiliki tingkat kepercayaan.

| Confidence | Status |
|------------|--------|
| 95–100% | Sangat Terpercaya |
| 80–94% | Terpercaya |
| 60–79% | Perlu Verifikasi |
| <60% | Tidak Boleh Digunakan |

Reasoning Engine harus mempertimbangkan Knowledge Confidence sebelum mengambil keputusan.

---

# 13. Knowledge Updates

Knowledge dapat diperbarui apabila:

- Pengguna mengubah informasi.
- Kebijakan perusahaan berubah.
- COA berubah.
- Accounting Rules berubah.
- Regulasi berubah.

Seluruh perubahan harus memiliki riwayat (versioning).

---

# 14. Knowledge Governance

Seluruh knowledge harus memiliki:

- Owner
- Version
- Status
- Last Updated
- Change History

Knowledge yang belum berstatus **Approved** tidak boleh digunakan sebagai dasar Reasoning Engine.

---

# 15. Knowledge Lifecycle

Setiap knowledge memiliki siklus hidup berikut.

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

Hanya knowledge dengan status **Active** yang boleh digunakan oleh Reasoning Engine.

---

# 15.1 Memory Evolution

Company Memory berkembang secara bertahap seiring penggunaan AI.

Contoh:

Hari pertama:

```text
Supplier = Belum Ada
```

↓

Pengguna:

> Saya membeli barang dari PT Maju Jaya.

↓

Company Memory diperbarui:

```text
Supplier
- PT Maju Jaya
```

↓

Beberapa hari kemudian:

> Saya membeli lagi dari PT Maju Jaya.

↓

AI mengenali supplier tersebut tanpa perlu meminta informasi yang sama.

Dengan mekanisme ini, AI Accountant mampu belajar dari histori perusahaan tanpa mengubah prinsip akuntansi yang digunakan.

---

# 16. Knowledge Version Compatibility

Reasoning Engine harus memastikan seluruh knowledge yang digunakan berasal dari versi yang kompatibel.

Apabila ditemukan konflik versi, AI harus menggunakan versi yang telah ditetapkan sebagai **Active** oleh sistem.

---

# 17. Knowledge Boundaries

AI tidak boleh:

- Mengarang knowledge.
- Menggunakan asumsi sebagai fakta.
- Mengubah knowledge tanpa konfirmasi.
- Mengabaikan kebijakan perusahaan.
- Menggunakan informasi dari perusahaan lain.

---

# 18. Example

## User

> Perusahaan saya menggunakan metode FIFO.

↓

Layer Memory diperbarui.

```text
Inventory Policy = FIFO
```

↓

Reasoning Engine membaca Memory.

↓

Seluruh transaksi persediaan menggunakan metode FIFO.

↓

Laporan persediaan mengikuti metode FIFO.

---

# 19. Future Knowledge Modules

Framework ini akan berkembang menjadi beberapa modul khusus.

- Accounting Rules
- COA Master
- Business Knowledge
- Tax Knowledge
- Financial Analysis Knowledge
- Industry Knowledge
- Audit Knowledge
- Internal Control Knowledge
- Company Memory Framework
- Context Management

---

# 19.1 Knowledge Flow

Berikut merupakan alur penggunaan knowledge pada setiap transaksi.

```text
User
   │
   ▼
Conversation
   │
   ▼
Intent Detection
   │
   ▼
Conversation Context
   │
   ▼
Company Memory
   │
   ▼
Knowledge Retrieval
   │
   ▼
Accounting Rules
   │
   ▼
Reasoning Engine
   │
   ▼
Journal
   │
   ▼
Financial Statements
```

Flow ini memastikan bahwa setiap keputusan akuntansi selalu didasarkan pada informasi yang relevan, tervalidasi, dan sesuai konteks perusahaan.

---

# 20. Relationship With Other Documents

Accounting Knowledge Framework menjadi penghubung seluruh arsitektur AI.

```text
User
        │
        ▼
Conversation
        │
        ▼
Context
        │
        ▼
Company Memory
        │
        ▼
Accounting Knowledge
        │
        ▼
Accounting Rules
        │
        ▼
COA
        │
        ▼
Reasoning Engine
        │
        ▼
Journal
        │
        ▼
Ledger
        │
        ▼
Financial Statements
```

Dokumen ini tidak berisi aturan pencatatan secara rinci, melainkan mendefinisikan sumber pengetahuan yang digunakan oleh Reasoning Engine.

---

# AI Knowledge Philosophy

AI Accountant tidak menghafal seluruh informasi pada setiap saat.

Sebaliknya, AI hanya mengambil pengetahuan yang relevan dengan transaksi yang sedang diproses.

Setiap keputusan akuntansi merupakan hasil kombinasi dari:

- General Knowledge
- Company Memory
- Conversation Context
- Accounting Rules
- Reasoning Engine

Pendekatan ini memberikan beberapa keuntungan:

- Mengurangi halusinasi AI.
- Menghemat penggunaan token.
- Mempercepat proses reasoning.
- Memastikan keputusan dapat dijelaskan.
- Memungkinkan setiap perusahaan memiliki knowledge yang berbeda tanpa memengaruhi perusahaan lain.

Dengan filosofi ini, AI Accountant dapat memberikan keputusan yang konsisten, transparan, dapat diaudit, dan terus berkembang seiring bertambahnya informasi perusahaan.

---

# Decision Log

## D-005

**Keputusan**

Reasoning Engine hanya boleh menggunakan knowledge yang telah tervalidasi melalui tiga lapisan informasi: Knowledge, Memory, dan Context.

**Alasan**

Pemisahan ketiga lapisan tersebut menjaga konsistensi, mengurangi halusinasi AI, dan memungkinkan setiap perusahaan memiliki informasi yang spesifik tanpa memengaruhi perusahaan lain.

**Dampak**

AI Accountant memiliki arsitektur pengetahuan yang modular, mudah dikembangkan, serta mampu melayani banyak perusahaan dengan tetap mempertahankan kualitas reasoning yang konsisten.

**Status**

Draft
