# AI Accountant Company Memory Framework

**Version:** 1.0 (Draft)
**Status:** Draft
**Owner:** Rizky
**Reviewer:** ChatGPT
**Last Updated:** 20 Juli 2026

---

# 1. Purpose

Dokumen ini mendefinisikan bagaimana AI Accountant menyimpan, mengambil, memperbarui, dan menggunakan informasi spesifik setiap perusahaan.

Company Memory memungkinkan AI bekerja seperti seorang akuntan yang mengenal bisnis pengguna, bukan sekadar menjawab berdasarkan percakapan saat ini.

Reasoning Engine hanya boleh menggunakan informasi perusahaan yang berasal dari Company Memory atau telah dikonfirmasi oleh pengguna.

---

# 2. Objectives

Company Memory bertujuan untuk:

- Menyimpan informasi perusahaan secara permanen.
- Menjaga konsistensi pencatatan.
- Mengurangi pertanyaan yang berulang.
- Mendukung reasoning yang lebih akurat.
- Menyesuaikan perilaku AI dengan karakteristik masing-masing perusahaan.

---

# 3. Memory Principles

Company Memory harus memenuhi prinsip berikut.

1. Akurat.
2. Dapat diverifikasi.
3. Dapat diperbarui.
4. Memiliki riwayat perubahan.
5. Bersifat spesifik untuk satu perusahaan.
6. Tidak dibagikan kepada perusahaan lain.
7. Dapat diaudit.
8. Konsisten dengan transaksi yang telah dikonfirmasi.

---

# 3.1 Memory Characteristics

Company Memory memiliki karakteristik berikut.

### Persistent

Informasi tetap tersedia meskipun percakapan telah berakhir.

### Company-specific

Setiap perusahaan memiliki Company Memory yang terpisah.

### Versioned

Seluruh perubahan memiliki riwayat versi.

### Explainable

AI harus dapat menjelaskan asal suatu informasi.

### Auditable

Seluruh perubahan dapat ditelusuri kembali.

### Secure

Memory hanya dapat diakses oleh perusahaan yang bersangkutan.

---

# 4. Memory Architecture

```text
Company
      │
      ▼
Company Memory
      │
      ├── Company Profile
      ├── Accounting Settings
      ├── Chart of Accounts
      ├── Customers
      ├── Suppliers
      ├── Products & Services
      ├── Fixed Assets
      ├── Inventory
      ├── Bank Accounts
      ├── Tax Settings
      ├── Accounting Policies
      ├── Historical Transactions
      └── User Preferences
              │
              ▼
      Reasoning Engine
```

Company Memory menjadi sumber utama informasi perusahaan sebelum AI mengambil keputusan.

---

# 5. Memory Categories

## 5.1 Company Profile

Disimpan:

- Nama perusahaan
- Jenis usaha
- Industri
- Tahun berdiri
- Mata uang
- Periode akuntansi
- Alamat
- NPWP (opsional)

---

## 5.2 Accounting Settings

Disimpan:

- Basis pencatatan
- Tahun buku
- Metode penyusutan
- Metode persediaan
- Default akun kas
- Default akun bank

---

## 5.3 Chart of Accounts

Disimpan:

- Daftar akun
- Kode akun
- Nama akun
- Status aktif
- Mapping akun

---

## 5.4 Customer Master

Disimpan:

- Nama customer
- Limit kredit
- Saldo piutang
- Riwayat pembayaran

---

## 5.5 Supplier Master

Disimpan:

- Nama supplier
- Saldo utang
- Riwayat transaksi

---

## 5.6 Products & Services

Disimpan:

- Nama produk
- SKU
- Harga jual
- Harga pokok
- Kategori
- Akun pendapatan
- Akun persediaan

---

## 5.7 Fixed Assets

Disimpan:

- Nama aset
- Nilai perolehan
- Tanggal pembelian
- Umur manfaat
- Nilai residu
- Akumulasi penyusutan

---

## 5.8 Inventory

Disimpan:

- Daftar barang
- Harga pokok
- Metode FIFO / Average
- Saldo stok

---

## 5.9 Bank Accounts

Disimpan:

- Nama bank
- Nomor rekening
- Mata uang
- Saldo

---

## 5.10 Tax Settings

Disimpan:

- Status PKP
- Tarif PPN
- Tarif PPh
- Preferensi perpajakan

---

## 5.11 User Preferences

Disimpan:

- Bahasa
- Format tanggal
- Format mata uang
- Tingkat detail penjelasan AI

---

## 5.12 Memory Metadata

Setiap informasi yang disimpan pada Company Memory harus memiliki metadata.

Minimal terdiri dari:

- Memory ID
- Entity Type
- Created At
- Updated At
- Created By
- Updated By
- Source
- Confidence Score
- Status
- Version

Metadata digunakan untuk mendukung audit trail, versioning, dan explainability.

---

# 6. Memory Lifecycle

```text
Create
   │
   ▼
Validate
   │
   ▼
Store
   │
   ▼
Retrieve
   │
   ▼
Update
   │
   ▼
Archive
```

AI tidak boleh menggunakan informasi yang belum melalui proses validasi.

---

# 7. Memory Update Rules

Memory hanya boleh diperbarui apabila:

- Pengguna memberikan informasi baru.
- Pengguna mengubah informasi sebelumnya.
- Perubahan berasal dari transaksi yang telah dikonfirmasi.
- Perubahan berasal dari administrator sistem.

Setiap perubahan harus memiliki:

- Timestamp
- Source
- User
- Version
- Confidence Score

---

# 8. Memory Retrieval Strategy

Sebelum melakukan reasoning, AI harus mengambil informasi dengan urutan berikut.

```text
Conversation Context
        │
        ▼
Company Memory
        │
        ▼
Accounting Knowledge
        │
        ▼
Reasoning Engine
```

Apabila informasi telah tersedia pada Company Memory dan masih valid, AI tidak perlu menanyakan kembali kepada pengguna.

---

# 8.1 Retrieval Principles

Reasoning Engine hanya mengambil memory yang relevan terhadap transaksi yang sedang diproses.

AI harus menghindari pengambilan seluruh Company Memory apabila tidak diperlukan.

Prioritas retrieval adalah:

1. Entity yang sedang dibahas.
2. Entity yang memiliki hubungan langsung.
3. Accounting Rules yang relevan.
4. Knowledge pendukung.

Tujuan proses ini adalah meningkatkan efisiensi reasoning, mengurangi penggunaan token, dan mempercepat waktu respons.

---

# 9. Memory Confidence

| Confidence | Status | Tindakan AI |
|------------|--------|-------------|
| 95–100% | Confirmed | Langsung digunakan |
| 80–94% | Reliable | Digunakan dengan penjelasan bila diperlukan |
| 60–79% | Needs Verification | Minta konfirmasi pengguna |
| <60% | Invalid | Tidak boleh digunakan |

---

# 9.1 Memory Source Priority

Apabila satu informasi berasal dari beberapa sumber, AI menggunakan prioritas berikut.

1. Konfirmasi langsung dari pengguna.
2. Data hasil transaksi yang telah dikonfirmasi.
3. Administrator sistem.
4. Import data perusahaan.
5. Inferensi AI.

Inferensi AI tidak boleh menggantikan informasi yang telah dikonfirmasi pengguna.

---

# 10. Memory Conflict Resolution

Apabila terjadi konflik informasi, AI menggunakan prioritas berikut.

1. Informasi terbaru yang telah dikonfirmasi pengguna.
2. Company Memory.
3. Accounting Knowledge Framework.
4. General Knowledge.

AI harus menjelaskan kepada pengguna apabila terjadi konflik yang memerlukan klarifikasi.

---

# 10.1 Memory Consistency Rules

Setiap perubahan Company Memory harus menjaga konsistensi seluruh Entity yang berkaitan.

Contoh:

Apabila Customer diubah, AI harus memastikan:

- Invoice tetap valid.
- Piutang tetap sesuai.
- Riwayat pembayaran tetap utuh.

AI tidak boleh menghasilkan perubahan yang menyebabkan inkonsistensi data.

---

# 11. Memory Privacy

Company Memory harus memenuhi prinsip berikut.

- Setiap perusahaan memiliki memory yang terisolasi.
- AI tidak boleh menggunakan data perusahaan lain.
- Data hanya digunakan untuk perusahaan yang bersangkutan.
- Seluruh perubahan memiliki audit trail.
- Seluruh akses memory harus dapat dilacak.

---

# 11.1 Multi-Tenant Isolation

AI Accountant dirancang untuk melayani banyak perusahaan.

Karena itu Company Memory harus memenuhi prinsip Multi-Tenant.

Setiap perusahaan memiliki:

- Company Memory sendiri.
- COA sendiri.
- Accounting Policy sendiri.
- Customer sendiri.
- Supplier sendiri.
- Riwayat transaksi sendiri.

Reasoning Engine tidak boleh mengakses memory perusahaan lain.

---

# 12. Example

## User

> Supplier utama saya sekarang adalah PT Maju Bersama.

↓

AI memperbarui Company Memory.

```text
Supplier Master
-------------------------
Nama        : PT Maju Bersama
Status      : Active
Confidence  : 100%
Source      : User Confirmation
Updated     : 20 Juli 2026
```

↓

Pada transaksi berikutnya:

> Saya membeli bahan baku dari supplier utama.

↓

AI langsung memahami bahwa supplier yang dimaksud adalah **PT Maju Bersama** tanpa perlu bertanya kembali.

---

# 13. Memory Entities

Company Memory menyimpan informasi dalam bentuk Business Entity.

Entity yang didukung pada versi pertama:

- Company
- User
- Customer
- Supplier
- Product
- Service
- Inventory Item
- Fixed Asset
- Bank Account
- Loan
- Invoice
- Bill
- Payment
- Journal Entry
- Tax Profile
- Accounting Policy

Setiap Entity memiliki:

- Entity ID
- Status
- Attributes
- Relationships
- Source
- Confidence Score
- Version
- Audit Trail

Reasoning Engine harus memahami hubungan antar Entity.

Contoh:

```text
Customer
     │
     ▼
Invoice
     │
     ▼
Accounts Receivable
     │
     ▼
Payment
     │
     ▼
Bank
```

Dengan pendekatan ini AI tidak hanya mengingat data, tetapi juga memahami hubungan antar objek bisnis.

---

# 14. Future Development

Company Memory akan dikembangkan untuk mendukung kemampuan berikut.

- Semantic Memory
- Episodic Memory
- Long-term Memory
- Preference Memory
- Learning Memory

Pengembangan tersebut memungkinkan AI Accountant semakin memahami karakteristik masing-masing perusahaan tanpa mengubah prinsip dasar akuntansi.

---

# 15. Relationship With Other Documents

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
Company Memory Framework
      │
      ▼
Accounting Knowledge Framework
      │
      ▼
Reasoning Engine
      │
      ▼
Accounting Rules
      │
      ▼
COA Master
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

Company Memory Framework menjadi penghubung antara percakapan pengguna dan proses reasoning.

---

# Decision Log

## D-006

**Keputusan**

Setiap perusahaan memiliki Company Memory yang terpisah dan menjadi sumber informasi utama bagi Reasoning Engine setelah Conversation Context.

**Alasan**

Pemisahan Company Memory memungkinkan AI Accountant mengingat karakteristik setiap perusahaan, mengurangi pertanyaan berulang, menjaga konsistensi pencatatan, dan mencegah pencampuran data antar pelanggan.

**Dampak**

AI Accountant mampu memberikan pengalaman layaknya seorang akuntan pribadi yang memahami bisnis setiap pengguna, sekaligus mendukung arsitektur multi-tenant untuk melayani banyak UMKM secara aman, konsisten, dan dapat diaudit.

**Status**

Draft
