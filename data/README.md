# Data — Sumber Dataset

Semua dataset di folder ini adalah dataset asli yang disediakan/dipakai course
(Data Science Foundations Specialization, University of London, Coursera).
Tidak ada data buatan. Ditambahkan ke repo 24 Oktober 2026 supaya materi
Course 6 dan capstone Course 7 bisa dijalankan ulang secara mandiri.

## 1. Bike Sharing Dataset — capstone Course 7 "Predicting Bicycle Rental"

| File | Baris data | Kolom | Ukuran |
|---|---|---|---|
| `bike-sharing/day.csv` | 731 | 16 | 57.569 byte |
| `bike-sharing/hour.csv` | 17.379 | 17 | 1.156.736 byte |

- Sumber: UCI Machine Learning Repository, "Bike Sharing Dataset"
  (Capital Bikeshare, Washington D.C., 2011–2012).
  Halaman dataset: https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset
  File unduhan: https://archive.ics.uci.edu/static/public/275/bike+sharing+dataset.zip
- Kolom `day.csv`: instant, dteday, season, yr, mnth, holiday, weekday,
  workingday, weathersit, temp, atemp, hum, windspeed, casual, registered, cnt.
  Rentang tanggal 2011-01-01 s.d. 2012-12-31.
- Yang dipakai deck capstone (`Portofolio-Capstone-Bicycle-Rental.pptx`):
  `day.csv` saja, dibaca dengan `pd.read_csv("day.csv")`; kolom `dteday`
  diubah menjadi `date` (datetime), target `cnt`, fitur utama `atemp`,
  pengelompokan `weathersit`. File `hour.csv` adalah versi per jam dari
  paket UCI yang sama (kolom tambahan `hr`), disertakan agar paket
  datasetnya utuh; tidak dipakai deck.
- Verifikasi silang terhadap angka di deck (dihitung ulang dari file ini):
  rata-rata `cnt` untuk weathersit 1 = 4.876,79 (deck: 4.876);
  weathersit 2 = 4.035,86 (deck: 4.035);
  korelasi `cnt` vs `atemp` = 0,631 (deck: r = 0,63). Cocok.

## 2. Banknote Authentication — project Course 6 "Statistics and Clustering in Python"

| File | Baris data | Kolom | Ukuran |
|---|---|---|---|
| `banknote/banknote.txt` | 1.372 | 5 (tanpa header) | 46.400 byte |

- Sumber: UCI Machine Learning Repository, "Banknote Authentication".
  Halaman dataset: https://archive.ics.uci.edu/dataset/267/banknote+authentication
  File unduhan: https://archive.ics.uci.edu/static/public/267/banknote+authentication.zip
- Nama file asli dari UCI adalah `data_banknote_authentication.txt`;
  di repo ini disimpan sebagai `banknote.txt` persis seperti nama yang
  dimuat kode di laporan EDA (`eda/course6-banknote-eda-report.md`):

  ```python
  df = pd.read_csv('banknote.txt', header=None,
                   names=['variance', 'skewness', 'curtosis', 'entropy', 'class'])
  ```

  Isi file tidak diubah sama sekali, hanya namanya disesuaikan dengan kode.
- Isi: 4 fitur hasil transformasi wavelet citra uang kertas (variance,
  skewness, curtosis, entropy) + label `class` (0 = asli, 762 baris;
  1 = palsu, 610 baris).
- Verifikasi silang terhadap laporan EDA: mean variance 0,43; skewness 1,92;
  curtosis 1,40; entropy -1,19; simpangan baku 2,84 / 5,87 / 4,31 / 2,10;
  rentang skewness -13,77 s.d. 12,95. Semua cocok dengan laporan.

## Catatan path

- Kode di laporan Course 6 memuat `banknote.txt` dari folder kerjanya;
  di repo file itu ada di `data/banknote/banknote.txt`.
- Kode di deck Course 7 memuat `day.csv` dari folder kerjanya;
  di repo file itu ada di `data/bike-sharing/day.csv`.
- Notebook `notebooks/DataScienceEcosystem.ipynb` (Course 3) tidak memuat
  dataset apa pun (hanya ringkasan tools dan ekspresi aritmetika), jadi
  tidak ada file data untuk notebook itu.
