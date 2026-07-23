# AI Accountant Intent Catalog

**Version:** 1.0 (Draft)
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

AI Accountant versi pertama mendukung intent berikut.

---

## A. Transaction Recording

Digunakan ketika pengguna ingin mencatat transaksi.

Intent:

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

Contoh:

> Hari ini saya membeli ATK Rp500.000 tunai.

↓

Intent:

Record Expense

---

## B. Financial Inquiry

Pengguna ingin mengetahui kondisi keuangan.

Intent:

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

Contoh:

> Berapa laba bulan ini?

↓

Intent

Check Profit

---

## C. Financial Reports

Pengguna meminta laporan.

Intent:

- Generate Income Statement
- Generate Balance Sheet
- Generate Cash Flow
- Generate Trial Balance
- Generate General Ledger
- Generate Journal Report
- Generate Inventory Report

---

## D. Analysis

Pengguna meminta analisis.

Intent:

- Analyze Profit
- Analyze Expenses
- Analyze Cash Flow
- Analyze Sales
- Analyze Financial Health
- Analyze Business Performance

---

## E. Master Data Management

Pengguna mengubah Company Memory.

Intent:

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

Intent:

- Update Company Profile
- Update Accounting Policy
- Update Fiscal Year
- Update Inventory Method
- Update Depreciation Policy

---

## G. Knowledge Request

Pengguna bertanya mengenai akuntansi.

Intent:

- Explain Accounting
- Explain Journal
- Explain Financial Statement
- Explain Tax
- Explain COA

---

## H. Conversation Control

Intent:

- Greeting
- Help
- Cancel
- Confirm
- Reject
- Goodbye

---

# 6. Intent Priority

Apabila terdapat lebih dari satu intent, AI menggunakan prioritas berikut.

1. Confirmation
2. Transaction Recording
3. Financial Report
4. Financial Inquiry
5. Analysis
6. Master Data
7. Knowledge Request
8. Conversation Control

---

# 7. Intent Confidence

| Confidence | Action |
|------------|--------|
| 95–100% | Langsung diproses |
| 80–94% | Diproses dengan penjelasan bila perlu |
| 60–79% | Meminta klarifikasi |
| <60% | Tidak boleh diproses |

---

# 8. Multi Intent Handling

Satu pesan dapat memiliki lebih dari satu intent.

Contoh:

> Hari ini saya membeli ATK Rp500.000 dan berapa saldo kas saya sekarang?

Intent:

1. Record Expense
2. Check Cash Balance

AI harus:

1. Menyelesaikan pencatatan transaksi.
2. Memperbarui laporan.
3. Menjawab pertanyaan saldo kas.

---

# 9. Intent State Transition

```text
Greeting
      │
      ▼
Intent Detection
      │
      ▼
Clarification
      │
      ▼
Reasoning
      │
      ▼
Recording
      │
      ▼
Reporting
      │
      ▼
Completed
```

---

# 10. Entity Extraction

Setelah intent dikenali, AI harus mengekstrak entity yang relevan.

Contoh entity:

- Tanggal
- Nominal
- Customer
- Supplier
- Produk
- Bank
- Akun
- Metode Pembayaran
- Pajak
- Lokasi
- Mata Uang

Entity menjadi input bagi Reasoning Engine.

---

# 11. Intent Routing

Setiap intent diarahkan ke modul yang sesuai.

```text
Transaction Intent
        │
        ▼
Reasoning Engine

Financial Inquiry
        │
        ▼
Financial Query Engine

Report Request
        │
        ▼
Reporting Engine

Knowledge Question
        │
        ▼
Knowledge Engine

Master Data
        │
        ▼
Company Memory
```

Dengan mekanisme ini, setiap modul hanya menangani tugas sesuai tanggung jawabnya.

---

# 12. Intent Boundaries

AI tidak boleh:

- Menebak intent apabila confidence rendah.
- Menjalankan dua intent yang saling bertentangan.
- Mengubah Company Memory tanpa intent yang valid.
- Membuat jurnal apabila intent belum teridentifikasi.

---

# 13. Example

## User

> Saya menerima pembayaran dari PT Maju Bersama sebesar Rp8.500.000 melalui transfer.

↓

Intent Detection

Record Income

↓

Entity Extraction

- Customer
- PT Maju Bersama

- Nominal
- Rp8.500.000

- Payment Method
- Transfer

↓

Reasoning Engine

↓

Journal

↓

Financial Statements

---

# 14. Future Intent Modules

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

Intent Catalog menjadi pintu masuk seluruh proses pengambilan keputusan AI Accountant.

---

# Decision Log

## D-007

**Keputusan**

Seluruh pesan pengguna harus melalui proses Intent Detection sebelum memasuki Reasoning Engine.

**Alasan**

Pemisahan proses pemahaman bahasa, identifikasi intent, dan reasoning akan meningkatkan akurasi, mengurangi kesalahan interpretasi, serta mempermudah pengembangan AI Accountant di masa depan.

**Dampak**

AI Accountant memiliki arsitektur yang modular, scalable, dan mampu menangani berbagai jenis permintaan pengguna melalui satu antarmuka WhatsApp tanpa mencampurkan logika percakapan dengan logika akuntansi.

**Status**

Draft
