# AI Accountant Intent Catalog

**Version:** 1.1 (Draft)
**Status:** Draft
**Owner:** Rizky
**Reviewer:** ChatGPT
**Last Updated:** 20 Juli 2026

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh intent yang dapat dikenali oleh AI Accountant.

Intent merupakan tujuan utama pengguna ketika berinteraksi dengan AI melalui WhatsApp.

Reasoning Engine tidak boleh memulai proses akuntansi sebelum Intent berhasil diidentifikasi.

---

# 2. Objectives

Intent Catalog bertujuan untuk:

- Menstandarkan pemahaman AI terhadap pesan pengguna.
- Menjadi jembatan antara Conversation Design dan Reasoning Engine.
- Mengurangi kesalahan interpretasi.
- Mendukung pengembangan AI secara modular.
- Memungkinkan penambahan kemampuan baru tanpa mengubah arsitektur utama.

---

# 3. Intent Detection Principles

AI harus:

1. Mengenali tujuan utama pengguna.
2. Tidak hanya mengandalkan kata kunci.
3. Memahami konteks percakapan.
4. Memanfaatkan Company Memory apabila diperlukan.
5. Meminta klarifikasi apabila terdapat lebih dari satu kemungkinan intent.

---

# 4. Intent Classification Pipeline

```text
User Message
      │
      ▼
Language Understanding
      │
      ▼
Intent Detection
      │
      ▼
Confidence Evaluation
      │
      ▼
Entity Extraction
      │
      ▼
Reasoning Engine
```

Intent selalu dikenali sebelum proses reasoning dimulai.

---

# 5. Intent Categories

## A. Transaction Recording

- Record Income
- Record Expense
- Record Purchase
- Record Sales
- Record Asset Purchase
- Record Inventory
- Record Loan
- Record Loan Payment
- Record Capital Injection
- Record Owner Withdrawal
- Record Depreciation
- Record Adjustment

---

## B. Financial Inquiry

- Check Cash Balance
- Check Bank Balance
- Check Profit
- Check Revenue
- Check Expenses
- Check Accounts Receivable
- Check Accounts Payable
- Check Inventory
- Check Asset Value
- Check Financial Position

---

## C. Financial Reports

- Generate Income Statement
- Generate Balance Sheet
- Generate Cash Flow
- Generate Trial Balance
- Generate General Ledger
- Generate Journal Report
- Generate Inventory Report

---

## D. Analysis

- Analyze Profit
- Analyze Expenses
- Analyze Cash Flow
- Analyze Sales
- Analyze Financial Health
- Analyze Business Performance

---

## E. Master Data Management

- Add Customer
- Update Customer
- Delete Customer
- Add Supplier
- Update Supplier
- Add Product
- Update Product
- Add Bank Account
- Update COA

---

## F. Company Settings

- Update Company Profile
- Update Accounting Policy
- Update Fiscal Year
- Update Inventory Method
- Update Depreciation Policy

---

## G. Knowledge Request

- Explain Accounting
- Explain Journal
- Explain Financial Statement
- Explain Tax
- Explain COA

---

## H. Conversation Control

- Greeting
- Help
- Cancel
- Confirm
- Reject
- Goodbye

---

# 6. Intent Registry

Setiap intent memiliki metadata yang menjadi acuan seluruh sistem.

| Field | Deskripsi |
|---------|----------|
| Intent ID | Identitas unik intent |
| Intent Name | Nama intent |
| Category | Kelompok intent |
| Description | Penjelasan intent |
| Required Entity | Entity minimal |
| Optional Entity | Entity tambahan |
| Need Confirmation | Ya/Tidak |
| Need Reasoning | Ya/Tidak |
| Update Company Memory | Ya/Tidak |
| Output Module | Modul tujuan |

Contoh:

| Field | Value |
|--------|------|
| Intent ID | INT-TRX-001 |
| Intent Name | Record Expense |
| Category | Transaction Recording |
| Required Entity | Nominal, Expense Type, Payment Method |
| Optional Entity | Supplier |
| Need Confirmation | No |
| Need Reasoning | Yes |
| Update Company Memory | No |
| Output | Journal Engine |

---

# 7. Required Entity Matrix

Setiap intent memiliki entity minimum yang berbeda.

| Intent | Required Entity |
|---------|----------------|
| Record Expense | Nominal, Expense Type, Payment Method |
| Record Sales | Customer, Nominal, Payment Method |
| Record Asset Purchase | Asset, Nominal, Payment Method |
| Record Loan | Lender, Nominal |
| Generate Profit | Accounting Period |
| Generate Cash Flow | Accounting Period |
| Check Cash Balance | Tidak ada |
| Analyze Profit | Accounting Period |

AI wajib meminta klarifikasi apabila Required Entity belum lengkap.

---

# 8. Intent Priority

1. Confirmation
2. Transaction Recording
3. Financial Report
4. Financial Inquiry
5. Analysis
6. Master Data
7. Knowledge Request
8. Conversation Control

---

# 9. Intent Confidence

| Confidence | Action |
|------------|--------|
|95–100%|Langsung diproses|
|80–94%|Diproses dengan penjelasan|
|60–79%|Meminta klarifikasi|
|<60%|Tidak boleh diproses|

---

# 10. Multi Intent Handling

Satu pesan dapat memiliki lebih dari satu intent.

AI harus:

1. Mengurutkan intent berdasarkan prioritas.
2. Menjalankan intent satu per satu.
3. Memastikan hasil intent sebelumnya telah selesai sebelum menjalankan intent berikutnya.

---

# 11. Intent Conflict Resolution

Apabila dua intent saling bertentangan, AI harus menggunakan aturan berikut.

Prioritas:

1. Confirmation
2. Cancel Transaction
3. Update Transaction
4. Record Transaction
5. Reporting

Contoh:

```
Batalkan transaksi kemarin,
lalu catat ulang.
```

↓

Confirmation

↓

Cancel Transaction

↓

Record Transaction

AI tidak boleh menjalankan dua intent yang saling bertentangan secara bersamaan.

---

# 12. Intent Lifecycle

Setiap intent memiliki siklus hidup berikut.

```text
Detected
      │
      ▼
Validated
      │
      ▼
Queued
      │
      ▼
Executed
      │
      ▼
Completed
      │
      ▼
Logged
```

Lifecycle ini memastikan seluruh aktivitas AI dapat diaudit.

---

# 13. Entity Extraction

Entity yang dapat diekstrak antara lain:

- Tanggal
- Nominal
- Customer
- Supplier
- Produk
- Bank
- COA
- Payment Method
- Tax
- Currency
- Location

Entity menjadi input utama bagi Reasoning Engine.

---

# 14. Intent Routing

```text
Transaction
        │
        ▼
Reasoning Engine

Financial Inquiry
        │
        ▼
Financial Query Engine

Reporting
        │
        ▼
Reporting Engine

Knowledge
        │
        ▼
Knowledge Engine

Master Data
        │
        ▼
Company Memory
```

---

# 15. Intent Ownership

Setiap intent memiliki modul utama yang bertanggung jawab.

| Intent | Owner Module |
|---------|-------------|
| Transaction Recording | Reasoning Engine |
| Financial Inquiry | Financial Query Engine |
| Reporting | Reporting Engine |
| Knowledge | Knowledge Engine |
| Company Settings | Company Memory |
| Master Data | Company Memory |

---

# 16. Intent Logging

Setiap intent yang diproses harus menghasilkan log.

Informasi minimal:

- Timestamp
- User ID
- Company ID
- Intent
- Confidence
- Entity
- Reasoning Result
- Output
- Execution Time
- Status

Log digunakan untuk audit dan debugging.

---

# 17. Intent Metrics

Kualitas Intent Engine diukur menggunakan:

- Intent Detection Accuracy
- Intent Success Rate
- Clarification Rate
- Average Response Time
- Misclassification Rate
- Fallback Rate

Metrics digunakan untuk mengevaluasi performa AI.

---

# 18. Intent Boundary Matrix

| Intent | Update Memory | Journal | Report | Confirmation |
|---------|---------------|---------|--------|--------------|
| Record Expense | No | Yes | Yes | No |
| Update COA | Yes | No | No | Yes |
| Delete Customer | Yes | No | No | Yes |
| Generate Profit | No | No | Yes | No |

---

# 19. Intent Boundaries

AI tidak boleh:

- Menebak intent apabila confidence rendah.
- Membuat jurnal sebelum intent dikenali.
- Mengubah Company Memory tanpa intent yang valid.
- Menjalankan intent yang saling bertentangan.

---

# 20. Future Intent Modules

Versi berikutnya akan mendukung:

- Tax Filing
- Payroll
- Budgeting
- Forecasting
- Business Advisory
- KPI Monitoring
- Fraud Detection
- Audit Assistance
- OCR Document Processing
- Voice Conversation

---

# 21. Relationship With Other Documents

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
Entity Extraction
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
Reasoning Engine
      │
      ▼
Journal Engine
      │
      ▼
Financial Statements
```

Intent Catalog merupakan gerbang utama seluruh proses AI Accountant.

---

# Decision Log

## D-007

**Keputusan**

Seluruh pesan pengguna harus melalui proses Intent Detection sebelum memasuki Reasoning Engine.

**Alasan**

Pemisahan proses pemahaman bahasa, identifikasi intent, dan reasoning meningkatkan akurasi, mengurangi kesalahan interpretasi, serta mempermudah pengembangan AI Accountant di masa depan.

**Dampak**

AI Accountant memiliki arsitektur yang modular, scalable, dapat diaudit, dan mampu menangani berbagai jenis permintaan pengguna melalui satu antarmuka WhatsApp tanpa mencampurkan logika percakapan dengan logika akuntansi.
