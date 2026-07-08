# Credit Risk Prediction — End-to-End ML Project

> **Status:** 🚧 Work in Progress — README ini akan terus diperbarui seiring progres project.

## Overview

Project ini membangun model prediksi **credit risk** (kemungkinan gagal bayar/*default*) menggunakan dataset pinjaman LendingClub (2007–2014), dengan cakupan **end-to-end**: mulai dari eksplorasi data, model development, hingga rencana deployment dan monitoring — bukan berhenti di notebook.

Project ini merupakan pengembangan lanjutan dari tugas Virtual Internship *Rakamin Academy x ID/X Partners*, dengan perbaikan signifikan pada sisi metodologi yang digunakan.
## Problem Statement

Ketika seorang calon nasabah mengajukan pinjaman, bank harus mengambil keputusan biner — **menyetujui atau menolak** — sebelum ada satupun perilaku pembayaran yang bisa diamati. Tantangan utamanya: tingkat kelayakan kredit (*creditworthiness*) seorang peminjam sebenarnya **tidak dapat diamati langsung** pada saat keputusan itu diambil. Bank yang terlalu konservatif kehilangan potensi pendapatan karena menolak peminjam yang sebenarnya layak. Bank yang terlalu longgar menanggung kerugian ketika peminjam gagal bayar.

Project ini membangun model machine learning yang mengestimasi **probability of default (PD)** seorang pemohon pinjaman **pada titik pengajuan (origination)** — hanya menggunakan informasi yang tersedia dari pemohon saat itu, tanpa bergantung pada variabel pasca-keputusan yang baru muncul setelah pinjaman berjalan.

Target variable bersifat biner (`bad_flag`):
- **0 (Good Loan):** peminjam membayar lancar, termasuk status `Current` dan `Fully Paid`
- **1 (Bad Loan):** peminjam menunjukkan indikasi gagal bayar signifikan, mencakup status `Charged Off`, `Default`, `Does not meet the credit policy. Status:Charged Off`, dan `Late (31-120 days)`

Definisi yang lebih luas ini dipilih (dibanding hanya membandingkan `Fully Paid` vs `Charged Off`) supaya lebih banyak sinyal keterlambatan pembayaran ikut tertangkap sebagai indikasi risiko, sejalan dengan tujuan bisnis bank untuk mendeteksi risiko sedini mungkin — bukan hanya kasus gagal bayar yang sudah final.

## Dataset

- **Sumber:** LendingClub Loan Data (2007–2014), `loan_data_2007_2014.csv`
- **Target variable:** `bad_flag` — biner (1 = bad loan: *Charged Off*, *Default*, *Late (31-120 days)*, dst; 0 = good loan)
- **Jumlah baris awal:** ±466,285 baris, 75 kolom

## Pipeline

```
Data Understanding
      ↓
     EDA 
      ↓
Feature Selection 
      ↓
Train-Test Split 
      ↓
   Encoding 
      ↓
    SMOTE 
      ↓
   Modeling 
      ↓
  Evaluation 
```

## Tech Stack

| Kategori | Tools |
|---|---|
| Data Processing & Modeling | Python, pandas, scikit-learn, imbalanced-learn |
| Experiment Tracking | MLflow + DagsHub |
| API Serving | FastAPI |
| Containerization | Docker |
| CI/CD | GitHub Actions |
| Monitoring | Evidently AI |

## Experiment Tracking

Seluruh eksperimen (parameter, metrik, model artifact) di-track menggunakan MLflow dan dapat dilihat di dashboard DagsHub:

🔗 **Dashboard akan ditambahkan di sini**


## Author

**Nazly Rafa Oktafian Nuzqu**
Information Systems Student — Universitas Telkom
