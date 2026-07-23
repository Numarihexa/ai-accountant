# AI Accountant Accounting Rules

**Version:** 1.0 (Draft)  
**Status:** Draft  
**Owner:** Rizky  
**Reviewer:** ChatGPT  
**Last Updated:** 20 Juli 2026

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh aturan akuntansi (**Accounting Rules**) yang menjadi dasar pengambilan keputusan AI Accountant.

Reasoning Engine hanya boleh menghasilkan jurnal berdasarkan aturan yang didefinisikan pada dokumen ini beserta dokumen pendukung yang telah berstatus **Approved**.

Accounting Rules memisahkan **logika akuntansi** dari **logika reasoning**, sehingga setiap keputusan dapat dijelaskan, diaudit, diperbarui, dan divalidasi secara independen.

Dokumen ini menjadi referensi utama bagi:

- Reasoning Engine
- Journal Engine
- COA Mapping
- Validation Engine
- Reporting Engine
- Audit Engine

---

# 2. Objectives

Accounting Rules bertujuan untuk:

- Menjamin konsistensi pencatatan transaksi.
- Mengurangi kemungkinan halusinasi AI.
- Menjadi dasar seluruh proses penjurnalan.
- Memastikan setiap keputusan memiliki dasar akuntansi yang jelas.
- Memastikan laporan keuangan mengikuti prinsip akuntansi yang berlaku.
- Mendukung Explainable AI (XAI) sehingga setiap jurnal dapat dijelaskan.
- Mempermudah proses audit dan pengembangan sistem di masa depan.
- Memungkinkan pembaruan aturan tanpa mengubah Reasoning Engine.

---

# 3. Accounting Principles

Dalam setiap transaksi, AI Accountant wajib mengikuti prinsip-prinsip akuntansi berikut.

1. Substance Over Form
2. Going Concern
3. Accrual Basis
4. Historical Cost
5. Matching Principle
6. Consistency
7. Prudence
8. Materiality
9. Faithful Representation

Apabila terdapat konflik antar prinsip atau informasi yang tersedia belum memadai, AI wajib meminta klarifikasi kepada pengguna sebelum melanjutkan proses pencatatan.

---

## 3.1 PSAK-Oriented Best Practice

Accounting Rules dirancang agar selaras dengan praktik akuntansi di Indonesia.

Pada versi awal, AI mengacu pada:

- PSAK yang berlaku
- Kebijakan akuntansi perusahaan
- Company Memory
- Chart of Accounts (COA)
- Accounting Knowledge Framework

AI tidak diperbolehkan menggunakan interpretasi yang bertentangan dengan kebijakan perusahaan ataupun PSAK yang berlaku.

---

## 3.2 Rule Design Principles

Seluruh aturan dalam dokumen ini harus memenuhi karakteristik berikut.

- Konsisten
- Deterministik
- Explainable
- Auditable
- Modular
- Versioned
- Dapat diuji (Testable)

Dengan prinsip tersebut, setiap keputusan AI dapat direproduksi dan diverifikasi kembali.

---

# 4. Rule Evaluation Pipeline

Setiap transaksi harus diproses melalui pipeline berikut.

```text
User Message
      │
      ▼
Intent Detection
      │
      ▼
Entity Extraction
      │
      ▼
Context Validation
      │
      ▼
Company Memory
      │
      ▼
Accounting Rules
      │
      ▼
Rule Evaluation
      │
      ▼
COA Mapping
      │
      ▼
Journal Validation
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

Accounting Rules tidak boleh dilewati.

Apabila salah satu tahapan gagal divalidasi, proses harus dihentikan dan AI wajib meminta klarifikasi kepada pengguna.

---

## 4.1 Rule Evaluation Stages

Setiap rule dievaluasi melalui tahapan berikut.

1. Rule Trigger
2. Rule Preconditions
3. Rule Evaluation
4. Rule Output
5. Validation
6. Explainability
7. Audit Logging

Rule hanya boleh dieksekusi apabila seluruh tahapan berhasil dilewati.

---

## 4.2 Rule Metadata

Setiap aturan harus memiliki metadata sebagai berikut.

| Field | Keterangan |
|--------|------------|
| Rule ID | Identitas unik rule |
| Rule Name | Nama aturan |
| Category | Kelompok rule |
| Version | Versi rule |
| Status | Draft / Review / Approved / Active |
| Effective Date | Tanggal mulai berlaku |
| Owner | Penanggung jawab |
| Reviewer | Reviewer |
| Last Updated | Tanggal perubahan terakhir |

Metadata digunakan oleh Rule Engine untuk memastikan hanya aturan yang valid yang digunakan.

---

# 5. Rule Priority

Apabila terdapat konflik antar aturan, AI harus menggunakan prioritas berikut.

1. User Confirmation
2. Company Accounting Policy
3. Company Memory
4. Accounting Rules
5. PSAK
6. COA Standard
7. General Accounting Knowledge

Prioritas yang lebih tinggi selalu mengesampingkan prioritas di bawahnya.

---

## 5.1 Rule Conflict Resolution

Apabila dua aturan menghasilkan keputusan yang berbeda, AI harus melakukan langkah berikut.

```text
Conflict Detected
        │
        ▼
Check User Confirmation
        │
        ▼
Check Company Policy
        │
        ▼
Check Company Memory
        │
        ▼
Check Accounting Rules
        │
        ▼
Conflict Resolved?
     │
 ┌───┴────┐
 │        │
Yes      No
 │        │
 ▼        ▼
Continue Clarification
```

AI tidak boleh memilih salah satu aturan secara acak.

---

## 5.2 Rule Dependency

Accounting Rules bergantung pada dokumen berikut.

- Company Memory Framework
- Accounting Knowledge Framework
- Chart of Accounts (COA)
- Reasoning Engine
- Intent Catalog
- Entity Catalog
- Company Accounting Policy
- PSAK

Apabila salah satu dependency belum tersedia atau belum tervalidasi, AI wajib meminta klarifikasi sebelum melanjutkan proses.

---

## 5.3 Rule Execution Principles

Sebelum suatu rule dijalankan, AI wajib memastikan bahwa:

- Rule berstatus **Active**.
- Rule sesuai dengan Company Policy.
- Rule kompatibel dengan versi Knowledge Framework.
- Rule memiliki seluruh informasi yang diperlukan.
- Rule tidak bertentangan dengan hasil konfirmasi pengguna.

Apabila salah satu syarat tidak terpenuhi, rule tidak boleh dijalankan.

---

### Validation Checklist

Sebelum memasuki Rule Categories, AI harus memastikan:

- ✓ Intent telah dikenali.
- ✓ Entity telah diekstraksi.
- ✓ Context telah tervalidasi.
- ✓ Company Memory tersedia.
- ✓ Accounting Rule tersedia.
- ✓ Tidak ada konflik kebijakan.
- ✓ Confidence memenuhi ambang minimal.

Seluruh checklist harus terpenuhi sebelum proses evaluasi aturan dilanjutkan.

---

=== END OF PART 1A ===

# 6. Rule Categories

Accounting Rules dikelompokkan ke dalam beberapa kategori berdasarkan siklus akuntansi dan jenis transaksi.

Setiap kategori memiliki kumpulan rule yang dapat dikembangkan secara independen tanpa memengaruhi kategori lainnya.

Kategori utama meliputi:

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

Pada versi berikutnya kategori dapat diperluas, misalnya:

- Tax Rules
- Payroll Rules
- Foreign Exchange Rules
- Leasing Rules
- Manufacturing Rules
- Construction Contract Rules
- Financial Instrument Rules

---

## 6.1 Rule Structure

Seluruh rule dalam dokumen ini mengikuti struktur standar berikut.

| Field | Description |
|---------|-------------|
| Rule ID | Identitas unik rule |
| Rule Name | Nama rule |
| Category | Kelompok rule |
| Trigger | Kondisi yang memicu rule |
| Preconditions | Syarat sebelum rule dijalankan |
| Rule Logic | Logika akuntansi |
| Output | Hasil rule |
| Validation | Pemeriksaan setelah rule |
| Explainability | Penjelasan kepada pengguna |
| Auditability | Informasi yang dicatat pada audit log |

Dengan struktur tersebut setiap rule dapat diimplementasikan langsung ke Rule Engine.

---

# 7. Asset Rules

AI mencatat suatu transaksi sebagai aset apabila seluruh kondisi berikut terpenuhi.

- Perusahaan mengendalikan aset tersebut.
- Memberikan manfaat ekonomi di masa depan.
- Nilai dapat diukur secara andal.
- Kepemilikan atau hak penggunaan telah diperoleh.

Apabila salah satu syarat tidak terpenuhi, transaksi tidak boleh dicatat sebagai aset.

---

## 7.1 Asset Recognition Decision Tree

```text
Apakah perusahaan mengendalikan aset?

            │
      ┌─────┴─────┐
      │           │
     Ya         Tidak
      │           │
      ▼           ▼
Manfaat ekonomi?  Bukan Aset
      │
 ┌────┴─────┐
 │          │
Ya        Tidak
 │          │
 ▼          ▼
Nilai dapat  Klarifikasi
diukur?
 │
 ┌────┴─────┐
 │          │
Ya        Tidak
 │          │
 ▼          ▼
Catat      Klarifikasi
Sebagai
Aset
```

---

## 7.2 Rule Specification

**Rule ID**

AR-AST-001

**Rule Name**

Asset Recognition

**Trigger**

Pengguna mencatat pembelian aset.

**Preconditions**

- Nilai diketahui.
- Tujuan penggunaan diketahui.
- Kepemilikan telah diperoleh.

**Output**

- Asset Classification
- COA Recommendation
- Journal Proposal

---

## 7.3 Validation Checklist

Sebelum aset dicatat AI harus memastikan:

- ✓ Nilai transaksi tersedia.
- ✓ Jenis aset diketahui.
- ✓ Digunakan untuk operasional.
- ✓ Tidak merupakan persediaan.
- ✓ Tidak merupakan beban.

---

# 8. Liability Rules

Liabilitas diakui apabila memenuhi seluruh kondisi berikut.

- Terdapat kewajiban saat ini.
- Berasal dari transaksi masa lalu.
- Penyelesaian kewajiban akan mengurangi sumber daya ekonomi perusahaan.
- Nilainya dapat diukur secara andal.

AI tidak boleh mengakui liabilitas yang belum memiliki dasar transaksi.

---

## 8.1 Rule Specification

**Rule ID**

AR-LIA-001

**Rule Name**

Liability Recognition

**Trigger**

Terjadi transaksi yang menimbulkan kewajiban.

**Preconditions**

- Terdapat pihak kreditur.
- Nilai diketahui.
- Kewajiban telah timbul.

**Output**

- Liability Classification
- Journal Recommendation

---

## 8.2 Validation Checklist

- ✓ Kewajiban telah terjadi.
- ✓ Nominal diketahui.
- ✓ Jatuh tempo tersedia (bila ada).
- ✓ Tidak termasuk ekuitas.

---

# 9. Revenue Rules

Pendapatan hanya boleh diakui apabila:

- Hak memperoleh pendapatan telah timbul.
- Barang atau jasa telah diserahkan sesuai kebijakan perusahaan.
- Nilai transaksi dapat diukur.
- Besar kemungkinan manfaat ekonomi akan diterima.

AI tidak boleh mengakui pendapatan berdasarkan perkiraan semata.

---

## 9.1 Rule Specification

**Rule ID**

AR-REV-001

**Rule Name**

Revenue Recognition

**Trigger**

Penjualan barang atau jasa.

**Preconditions**

- Customer diketahui.
- Nilai diketahui.
- Barang/jasa telah memenuhi syarat pengakuan.

**Output**

- Revenue Classification
- Journal Recommendation

---

## 9.2 Revenue Decision Tree

```text
Barang/Jasa telah diserahkan?

          │
    ┌─────┴─────┐
    │           │
   Ya        Belum
    │           │
    ▼           ▼
Hak Pendapatan?  Tunda Pengakuan
    │
 ┌──┴────┐
 │       │
Ya      Tidak
 │       │
 ▼       ▼
Akui    Klarifikasi
Revenue
```

---

# 10. Expense Rules

Beban diakui apabila:

- Manfaat ekonomi telah dikonsumsi.
- Berkaitan dengan aktivitas operasional perusahaan.
- Memenuhi prinsip matching apabila relevan.
- Nilai transaksi dapat diukur.

AI tidak boleh mengakui beban yang seharusnya dikapitalisasi menjadi aset.

---

## 10.1 Rule Specification

**Rule ID**

AR-EXP-001

**Rule Name**

Expense Recognition

**Trigger**

Pengeluaran perusahaan.

**Preconditions**

- Nominal diketahui.
- Tujuan penggunaan diketahui.

**Output**

- Expense Classification
- COA Recommendation
- Journal Recommendation

---

## 10.2 Validation Checklist

- ✓ Bukan aset.
- ✓ Bukan investasi.
- ✓ Bukan pembayaran utang.
- ✓ Berkaitan dengan operasional.

---

=== END OF PART 1B ===

# 11. Capital vs Expense Decision

Setiap transaksi pembelian harus dievaluasi untuk menentukan apakah dicatat sebagai **Aset (Capital Expenditure)** atau **Beban (Operating Expense)**.

Keputusan ini harus mengikuti kebijakan perusahaan, Accounting Rules, dan Company Memory.

AI tidak boleh menentukan klasifikasi hanya berdasarkan nama barang.

---

## 11.1 Decision Criteria

Suatu pembelian diklasifikasikan sebagai **Capital Expenditure** apabila memenuhi sebagian besar kriteria berikut.

- Memberikan manfaat ekonomi lebih dari satu periode.
- Digunakan untuk operasional perusahaan.
- Memenuhi batas kapitalisasi perusahaan.
- Menambah nilai aset.
- Memperpanjang umur manfaat aset.

Apabila tidak memenuhi kriteria tersebut maka transaksi dicatat sebagai beban.

---

## 11.2 Decision Tree

```text
Pembelian

      │
      ▼

Manfaat > 1 Tahun?

      │
 ┌────┴────┐
 │         │
Ya        Tidak
 │         │
 ▼         ▼

Melebihi Nilai
Kapitalisasi?

 │
 ┌────┴────┐
 │         │
Ya        Tidak
 │         │
 ▼         ▼

Asset    Expense
```

---

## 11.3 Rule Specification

| Field | Value |
|---------|------|
| Rule ID | AR-CAP-001 |
| Rule Name | Capitalization Decision |
| Category | Asset Rules |
| Trigger | Purchase Transaction |
| Output | Asset / Expense Classification |

---

## 11.4 Validation Checklist

AI harus memastikan:

- ✓ Nilai transaksi diketahui.
- ✓ Umur manfaat diketahui.
- ✓ Tujuan penggunaan diketahui.
- ✓ Kebijakan kapitalisasi tersedia.

---

# 12. Inventory Rules

Persediaan diakui apabila barang:

- dimiliki untuk dijual;
- digunakan dalam proses produksi;
- digunakan sebagai bahan baku.

AI harus mengikuti metode penilaian persediaan yang tersimpan pada Company Memory.

---

## 12.1 Inventory Valuation

Metode yang didukung.

- FIFO
- Weighted Average
- FEFO (apabila relevan)
- Specific Identification (future version)

AI tidak boleh mengganti metode tanpa konfirmasi pengguna.

---

## 12.2 Rule Specification

| Field | Value |
|---------|------|
| Rule ID | AR-INV-001 |
| Rule Name | Inventory Recognition |
| Category | Inventory Rules |
| Trigger | Inventory Transaction |
| Output | Inventory Classification |

---

## 12.3 Validation Checklist

- ✓ Barang merupakan persediaan.
- ✓ Nilai diketahui.
- ✓ Metode penilaian tersedia.
- ✓ Gudang diketahui (jika ada).

---

# 13. Fixed Asset Rules

Suatu aset dikategorikan sebagai aset tetap apabila:

- digunakan untuk operasional perusahaan;
- memiliki manfaat ekonomi lebih dari satu periode;
- memenuhi nilai kapitalisasi perusahaan;
- bukan untuk dijual kembali.

---

## 13.1 Fixed Asset Categories

Contoh kategori.

- Tanah
- Bangunan
- Kendaraan
- Mesin
- Peralatan
- Komputer
- Inventaris Kantor

Kategori dapat dikembangkan sesuai COA perusahaan.

---

## 13.2 Rule Specification

| Field | Value |
|---------|------|
| Rule ID | AR-FA-001 |
| Rule Name | Fixed Asset Recognition |
| Category | Fixed Asset Rules |
| Trigger | Asset Purchase |
| Output | Fixed Asset Classification |

---

## 13.3 Validation Checklist

AI memastikan:

- ✓ Bukan persediaan.
- ✓ Umur manfaat > 1 tahun.
- ✓ Digunakan untuk operasional.
- ✓ Nilai memenuhi batas kapitalisasi.

---

# 14. Depreciation Rules

Penyusutan dilakukan berdasarkan kebijakan perusahaan.

Reasoning Engine tidak diperbolehkan menentukan metode penyusutan sendiri.

---

## 14.1 Supported Methods

Versi pertama mendukung.

- Garis Lurus (Straight Line)
- Saldo Menurun (Declining Balance)
- Unit Produksi (Unit of Production)

---

## 14.2 Rule Specification

| Field | Value |
|---------|------|
| Rule ID | AR-DEP-001 |
| Rule Name | Depreciation |
| Category | Depreciation Rules |
| Trigger | End of Accounting Period |
| Output | Depreciation Journal |

---

## 14.3 Validation Checklist

AI memastikan.

- ✓ Metode penyusutan tersedia.
- ✓ Umur manfaat tersedia.
- ✓ Nilai residu tersedia (jika digunakan).
- ✓ Aset masih aktif.

---

# 15. Journal Rules

Setiap jurnal yang dihasilkan AI Accountant wajib memenuhi standar validasi sebelum disimpan.

Journal Engine tidak boleh menyimpan jurnal yang gagal divalidasi.

---

## 15.1 Mandatory Rules

Seluruh jurnal wajib memenuhi:

- Debit = Kredit
- COA valid
- Accounting Period valid
- Mata uang valid
- Tidak terjadi duplikasi transaksi
- Referensi transaksi tersedia
- Rule telah dievaluasi
- Confidence memenuhi batas minimum

---

## 15.2 Journal Validation Pipeline

```text
Journal Proposal
        │
        ▼
COA Validation
        │
        ▼
Balance Validation
        │
        ▼
Duplicate Check
        │
        ▼
Accounting Period
        │
        ▼
Policy Validation
        │
        ▼
Confidence Evaluation
        │
        ▼
Journal Approved
```

---

## 15.3 Journal Metadata

Setiap jurnal minimal memiliki metadata berikut.

| Field | Description |
|---------|------------|
| Journal ID | Identitas jurnal |
| Transaction ID | Referensi transaksi |
| Rule ID | Rule yang digunakan |
| COA Version | Versi COA |
| Rule Version | Versi Rule |
| Confidence | Nilai confidence |
| Created At | Timestamp |
| Created By | AI Accountant |
| Status | Draft / Approved / Posted |

---

## 15.4 Explainability

AI wajib mampu menjelaskan.

- Mengapa jurnal dibuat.
- Rule yang digunakan.
- Alasan memilih akun.
- Dampak terhadap laporan keuangan.
- Pengaruh terhadap saldo akun.

---

## 15.5 Auditability

Setiap jurnal harus dapat diaudit.

Minimal menyimpan:

- Rule ID
- Rule Version
- Company Policy Version
- COA Version
- Confidence Score
- User Confirmation
- Input Transaction
- Generated Journal
- Timestamp

Audit Log tidak boleh diubah setelah jurnal diposting.

---

## 15.6 Validation Checklist

Sebelum jurnal diposting AI memastikan.

- ✓ Rule Active
- ✓ Company Policy sesuai
- ✓ Company Memory tersedia
- ✓ COA valid
- ✓ Debit = Kredit
- ✓ Tidak duplikat
- ✓ Accounting Period terbuka
- ✓ Confidence ≥ Threshold
- ✓ Journal telah dijelaskan kepada pengguna apabila diperlukan

---

=== END OF PART 1C ===

# 16. COA Mapping Rules

Seluruh transaksi harus dipetakan ke akun **Chart of Accounts (COA)** sebelum jurnal dibuat.

COA Mapping bertujuan untuk memastikan bahwa setiap transaksi menggunakan akun yang konsisten sesuai kebijakan perusahaan.

Apabila Company Memory memiliki COA khusus, AI wajib menggunakan COA tersebut dan mengabaikan COA bawaan.

---

## 16.1 Objectives

COA Mapping bertujuan untuk:

- Menjamin konsistensi akun.
- Mengurangi kesalahan klasifikasi.
- Mendukung Explainable AI.
- Menjaga kesesuaian dengan Company Policy.
- Mempermudah audit.

---

## 16.2 Mapping Priority

Urutan prioritas pemetaan akun.

1. User Confirmation
2. Company COA
3. Company Accounting Policy
4. Accounting Rules
5. Standard COA
6. Accounting Knowledge Framework

---

## 16.3 Mapping Example

| Transaction | Debit | Credit |
|-------------|-------|--------|
| Penjualan Tunai | Kas | Pendapatan |
| Penjualan Kredit | Piutang | Pendapatan |
| Pembelian ATK Tunai | Beban ATK | Kas |
| Pembelian Laptop | Aset Tetap | Kas |
| Setoran Modal | Kas | Modal |
| Pembayaran Utang | Utang Dagang | Kas |

---

## 16.4 Validation Checklist

AI wajib memastikan:

- ✓ COA tersedia.
- ✓ Akun aktif.
- ✓ Tidak menggunakan akun deprecated.
- ✓ Sesuai Company Policy.
- ✓ Sesuai Rule.

---

# 17. Validation Rules

Sebelum jurnal dibuat, seluruh transaksi wajib melalui proses validasi.

---

## 17.1 Validation Pipeline

```text
Intent
     │
     ▼
Entity Validation
     │
     ▼
Context Validation
     │
     ▼
Company Memory
     │
     ▼
Accounting Rule
     │
     ▼
COA Validation
     │
     ▼
Journal Validation
     │
     ▼
Approved
```

---

## 17.2 Validation Checklist

AI harus memastikan:

- ✓ Intent valid
- ✓ Entity lengkap
- ✓ Company Memory tersedia
- ✓ Company Policy tersedia
- ✓ Rule Active
- ✓ COA valid
- ✓ Accounting Period terbuka
- ✓ Debit = Kredit
- ✓ Tidak duplikat
- ✓ Confidence memenuhi batas minimum

---

# 18. Clarification Rules

AI wajib meminta klarifikasi apabila informasi yang tersedia belum cukup untuk menghasilkan jurnal yang dapat dipertanggungjawabkan.

AI tidak boleh membuat asumsi.

---

## 18.1 Clarification Trigger

Contoh kondisi.

- Metode pembayaran tidak diketahui.
- Customer belum diketahui.
- Supplier belum diketahui.
- Tujuan transaksi belum jelas.
- Nilai transaksi belum lengkap.
- Tanggal transaksi belum diketahui.
- Dua akun memiliki probabilitas yang sama.
- Company Policy belum tersedia.

---

## 18.2 Clarification Outcome

Setiap klarifikasi menghasilkan salah satu status berikut.

- NEED_CONFIRMATION
- NEED_INFORMATION
- MANUAL_REVIEW

---

# 19. Exception Handling

Apabila transaksi tidak dapat diproses menggunakan Rule yang tersedia, AI harus menjalankan mekanisme Exception Handling.

---

## 19.1 Exception Categories

- Missing Entity
- Invalid Policy
- Unknown Transaction
- Rule Conflict
- Invalid COA
- Closed Accounting Period
- Duplicate Transaction

---

## 19.2 Exception Decision Tree

```text
Exception

      │
      ▼

Rule Exists?

      │
 ┌────┴────┐
 │         │
Yes       No
 │         │
 ▼         ▼

Execute   Manual Review

```

---

## 19.3 Exception Outcome

- PASS
- WARNING
- NEED_CONFIRMATION
- MANUAL_REVIEW
- FAIL

---

# 20. Explainability Rules

Seluruh keputusan AI harus dapat dijelaskan kepada pengguna.

Explainability merupakan bagian wajib dari setiap Rule.

---

## 20.1 Explainability Output

AI minimal mampu menjelaskan.

- Rule yang digunakan.
- Mengapa rule dipilih.
- Mengapa akun dipilih.
- Mengapa jurnal dibuat.
- Dampak jurnal terhadap laporan keuangan.

---

## 20.2 Decision Reason

Setiap keputusan harus memiliki alasan.

Contoh.

```
Decision

Expense

Reason

ATK digunakan untuk operasional.

Tidak memenuhi syarat kapitalisasi.

Manfaat kurang dari satu periode.
```

---

# 21. Rule Confidence

Setiap Rule menghasilkan nilai confidence.

Confidence digunakan untuk menentukan apakah jurnal dapat diposting atau harus diklarifikasi.

---

| Confidence | Action |
|------------|--------|
|95–100%|Proceed|
|80–94%|Proceed with Explanation|
|60–79%|Need Confirmation|
|<60%|Stop Processing|

---

## 21.1 Confidence Source

Confidence dihitung dari beberapa sumber.

- Intent Detection
- Entity Extraction
- Company Memory
- Accounting Rule
- Conversation Context

AI wajib mampu menjelaskan sumber confidence tersebut.

---

# 22. Rule Logging

Seluruh proses evaluasi Rule wajib dicatat.

---

## 22.1 Minimum Log

- Timestamp
- Rule ID
- Rule Version
- Transaction ID
- Input
- Output
- Journal
- Confidence
- User Confirmation

---

## 22.2 Audit Log

Audit Log bersifat immutable.

Tidak boleh diubah setelah jurnal diposting.

---

# 23. Rule Versioning

Setiap Rule memiliki identitas yang unik.

---

## Rule Metadata

| Field | Description |
|--------|-------------|
| Rule ID | Unique Identifier |
| Rule Name | Rule Name |
| Version | Rule Version |
| Status | Draft / Review / Active |
| Effective Date | Effective Date |
| Owner | Rule Owner |
| Reviewer | Reviewer |
| Change History | Revision History |

Reasoning Engine hanya boleh menggunakan Rule berstatus **Active**.

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

## 24.1 Rule Governance

Perubahan Rule harus melalui proses.

Draft

↓

Review

↓

Approval

↓

Deployment

↓

Monitoring

↓

Version Update

---

# 25. Rule Dependency

Accounting Rules memiliki dependency terhadap beberapa modul.

```text
Intent Catalog
        │
        ▼
Entity Extraction
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
Journal Engine
```

---

## 25.1 Dependency Validation

Sebelum Rule dijalankan.

- ✓ Dependency tersedia.
- ✓ Dependency compatible.
- ✓ Version compatible.

---

# 26. Rule Boundaries

AI tidak boleh:

- Mengarang Rule.
- Menggunakan Rule Deprecated.
- Mengubah Company Policy.
- Mengubah Company Memory tanpa izin.
- Menggunakan COA yang tidak aktif.
- Membuat jurnal ketika Rule gagal divalidasi.

---

## 26.1 Rule Scope

Versi pertama mendukung.

- UMKM Dagang
- UMKM Jasa
- UMKM Retail

Versi berikutnya.

- Manufaktur
- Konstruksi
- Hospitality
- Healthcare

---

## 26.2 Rule Constraints

Rule pada versi ini tidak digunakan untuk.

- Payroll
- Leasing
- Konsolidasi
- Foreign Currency
- Derivatif
- Financial Instrument

---

# 27. Example Rule

## Rule ID

AR-REV-001

---

### Rule Name

Revenue Recognition

---

### Trigger

Penjualan Barang

---

### Preconditions

- Barang telah diserahkan.
- Customer diketahui.
- Nilai diketahui.

---

### Output

Journal Recommendation

---

### Journal

Debit Kas / Piutang

Kredit Pendapatan

---

### Explainability

Pendapatan diakui karena hak perusahaan atas pendapatan telah timbul setelah barang diserahkan.

---

### Auditability

Rule Version

COA Version

Timestamp

Confidence

User Confirmation

---

# 28. Rule Relationship

```text
Conversation
      │
      ▼
Intent
      │
      ▼
Entity
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

Framework akan dikembangkan menjadi modul.

- Revenue Recognition
- Expense Recognition
- Inventory
- Fixed Asset
- Depreciation
- Tax
- Payroll
- Leasing
- Manufacturing
- Construction
- Budgeting
- Forecasting
- KPI Monitoring
- Fraud Detection
- Audit Assistance

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
Entity Catalog
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

Accounting Rules merupakan pusat logika akuntansi yang digunakan oleh seluruh komponen AI Accountant.

---

# Decision Log

## D-008

### Decision

Seluruh jurnal AI Accountant harus dihasilkan berdasarkan Accounting Rules yang telah tervalidasi.

### Rationale

Pemisahan antara Reasoning Engine dan Accounting Rules memastikan logika bisnis dapat diaudit, diperbarui, dan dijelaskan tanpa mengubah arsitektur inti AI.

### Impact

- Explainable AI
- Deterministic Rule Engine
- Modular Architecture
- Audit Ready
- Enterprise Ready

### Status

Draft
