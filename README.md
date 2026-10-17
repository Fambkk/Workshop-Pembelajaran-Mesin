# Workshop-Pembelajaran-Mesin
Project Mata Kuliah Workshop Pembelajaran Mesin Universitas Negeri Malang

Repository ini berisi tugas mata kuliah **Workshop Pembelajaran Mesin**, Program Studi Teknologi Rekayasa Sistem Elektronika, Fakultas Vokasi, Universitas Negeri Malang.

## 👥 Kelompok 3

| Nama | NIM |
| --- | --- |
| Mohammad Zulfahmi Yahya | 230935604725 |
| Qismatur Rizqi Dwi Natasya | 230935604539 |
| Wildan Pristika Aufia | 230935605499 |

## 📌 UTS: Eksperimen Random Forest untuk Deteksi Perilaku Sakit Ayam

### Latar belakang
Pada peternakan dengan kandang berkepadatan tinggi, satu ayam yang sakit dapat menularkan penyakit ke seluruh kawanan. Pemantauan manual oleh peternak memakan waktu, bersifat subjektif, dan sulit dilakukan terus-menerus. Ayam yang sakit biasanya menunjukkan perubahan perilaku, seperti bergerak lebih sedikit, lebih lama diam, dan menjauh dari kawanan. Perilaku ini dapat diukur dan dimanfaatkan sebagai dasar deteksi dini.

### Tentang project
Project ini merupakan bagian dari rencana sistem deteksi perilaku sakit ayam berbasis **Edge AI** pada Raspberry Pi. Fokus UTS ini adalah tahap klasifikasinya: mengklasifikasikan ayam **sehat** dan **pasif (indikasi sakit)** menggunakan algoritma **Random Forest**. Karena akan dijalankan pada perangkat berdaya terbatas, model yang dicari harus akurat sekaligus ringan.

### Fitur yang digunakan
| Fitur | Keterangan |
| --- | --- |
| `total_distance` | Jarak tempuh total ayam. Nilai rendah mengindikasikan ayam lesu |
| `idle_duration` | Lamanya ayam diam. Nilai tinggi mengindikasikan ayam lesu |
| `isolation_index` | Jarak ayam dari kawanan. Nilai tinggi mengindikasikan ayam menyendiri |

### Tujuan
1. Membandingkan kinerja Random Forest pada berbagai jumlah pohon (`n_estimators`) dan kedalaman pohon (`max_depth`).
2. Mengamati operasi yang terjadi pada setiap pohon dan setiap level kedalaman.
3. Menyajikan perbandingan dalam bentuk tabel dan grafik.
4. Menentukan jumlah pohon dan kedalaman yang optimal.
5. Menyajikan *confusion matrix* dari model optimal.

### Metode singkat
- **Dataset:** data *dummy* yang dibangkitkan dari distribusi normal untuk dua kelas (sehat dan pasif), masing-masing 250 data.
- **Pembagian data:** 80% data latih dan 20% data uji.
- **Eksperimen:** 49 kombinasi `n_estimators` × `max_depth`.
- **Evaluasi:** *accuracy*, *precision*, *recall*, *F1-score*, dan 5-fold *cross-validation*.
- **Pemilihan model optimal:** berdasarkan F1 *cross-validation*, dengan memilih model yang paling sederhana jika hasilnya setara.

### 🛠️ Teknologi
Python, NumPy, pandas, scikit-learn, matplotlib, dan joblib.

### 📂 Isi repository
| File | Keterangan |
| --- | --- |
| `UTS.ipynb` | Kode lengkap eksperimen |

### ▶️ Cara menjalankan
```bash
pip install numpy pandas scikit-learn matplotlib joblib
jupyter notebook UTS.ipynb
```
