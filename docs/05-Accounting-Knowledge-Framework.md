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

```
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

# 8. Knowledge Dependencies

Reasoning Engine bergantung pada:

- Accounting Rules
- COA
- Company Memory
- Conversation Context
- Company Policies

Apabila salah satu informasi belum tersedia, AI wajib meminta klarifikasi kepada pengguna.

---

# 9. Knowledge Validation

Sebelum digunakan, knowledge harus memenuhi syarat berikut.

- Benar.
- Masih berlaku.
- Konsisten dengan knowledge lainnya.
- Tidak bertentangan dengan kebijakan perusahaan.

Knowledge yang belum tervalidasi tidak boleh digunakan sebagai dasar pencatatan.

---

# 10. Knowledge Updates

Knowledge dapat diperbarui apabila:

- Pengguna mengubah informasi.
- Kebijakan perusahaan berubah.
- COA berubah.
- Accounting Rules berubah.
- Regulasi berubah.

Seluruh perubahan harus memiliki riwayat (versioning).

---

# 11. Knowledge Governance

Seluruh knowledge harus memiliki:

- Owner
- Version
- Status
- Last Updated
- Change History

Knowledge yang belum berstatus **Approved** tidak boleh digunakan sebagai dasar Reasoning Engine.

---

# 12. Knowledge Boundaries

AI tidak boleh:

- Mengarang knowledge.
- Menggunakan asumsi sebagai fakta.
- Mengubah knowledge tanpa konfirmasi.
- Mengabaikan kebijakan perusahaan.
- Menggunakan informasi dari perusahaan lain.

---

# 13. Example

## User

> Perusahaan saya menggunakan metode FIFO.

↓

Layer Memory diperbarui:

Inventory Policy = FIFO

↓

Reasoning Engine membaca Memory

↓

Seluruh transaksi persediaan menggunakan metode FIFO.

↓

Laporan persediaan mengikuti FIFO.

---

# 14. Future Knowledge Modules

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

# 15. Relationship With Other Documents

Accounting Knowledge Framework menjadi penghubung antara seluruh dokumen arsitektur AI.

```
Vision
        │
Persona
        │
Conversation Design
        │
Accounting Knowledge Framework
        │
        ├── Accounting Rules
        ├── COA Master
        ├── Company Memory
        └── Context Management
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

Dokumen ini tidak berisi aturan pencatatan secara rinci, melainkan mendefinisikan sumber pengetahuan yang digunakan oleh Reasoning Engine.

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
