# 🧹 Data Cleaning Project with Pandas

Proyek ini dibuat untuk membersihkan dan memproses data mentah menggunakan **Python (Pandas)**.  
Tujuannya adalah menyiapkan dataset yang siap digunakan untuk analisis lebih lanjut seperti visualisasi, machine learning, atau business insight.

---

## 📊 Dataset
- **Nama file:** `data_raw.csv`  
- **Sumber:** (isi sumber datanya, misalnya: Kaggle / internal / dummy data)
- **Jumlah data:** (misal: 500 baris, 10 kolom)

---

## 🧠 Tujuan Cleaning
Beberapa tahap utama yang dilakukan dalam proses data cleaning ini:
1. Menghapus **missing values (NaN)**  
2. Mengatasi **duplikasi data**
3. Mengubah **tipe data** ke format yang sesuai (misal `object → datetime`)
4. Menstandarkan **nama kolom**
5. Membersihkan **outlier** (nilai ekstrim)
6. Menyimpan hasil bersih ke file `data_cleaned.csv`

---

## ⚙️ Tools yang Digunakan
- 🐍 Python 3.x  
- 🧾 Pandas  
- 📉 NumPy  
- 📊 Matplotlib (opsional untuk eksplorasi data)

---

## 💻 Langkah-Langkah Cleaning (Contoh)
```python
import pandas as pd
import numpy as np

# 1️⃣ Baca data
df = pd.read_csv('data_raw.csv')

# 2️⃣ Cek info dasar
print(df.info())
print(df.describe())

# 3️⃣ Hapus data duplikat
df = df.drop_duplicates()

# 4️⃣ Tangani missing value
df = df.fillna(df.mean(numeric_only=True))

# 5️⃣ Ubah tipe data
df['tanggal'] = pd.to_datetime(df['tanggal'])

# 6️⃣ Standarkan nama kolom
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')

# 7️⃣ Simpan hasil bersih
df.to_csv('data_cleaned.csv', index=False)
