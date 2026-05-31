# Prediksi Kelulusan Mahasiswa & Deteksi Dini Kegagalan Menggunakan Pembelajaran Mesin

Repositori ini berisi proyek Ilmu Data yang berfokus pada prediksi hasil kelulusan mahasiswa dan memberikan deteksi dini risiko kegagalan akademik. Menggunakan data mahasiswa historis dari dua periode akademik yang berbeda, proyek ini mengimplementasikan pra-pemrosesan data, penyelarasan fitur, dan **Pengklasifikasi Random Forest** untuk membangun model prediktif.

## 📌 Gambaran Umum Proyek
Di pendidikan tinggi, mengidentifikasi mahasiswa yang berisiko gagal atau putus kuliah di awal perjalanan akademiknya sangat penting untuk intervensi tepat waktu. Proyek ini bertujuan untuk mengatasi tantangan ini dengan memanfaatkan data demografis dan kinerja akademik awal untuk mengklasifikasikan hasil mahasiswa.

Alur kerja analitis meliputi:
* Pengambilan dan pra-pemrosesan data dari kumpulan data periode akademik yang terpisah.
* Rekonsiliasi fitur (menangani fitur yang tidak selaras atau hilang antar periode).
* Analisis Data Eksplorasi (EDA) dan pemilihan fitur.
* Pengembangan dan evaluasi model menggunakan Random Forest.

## 📊 Deskripsi Dataset
Proyek ini menggunakan catatan siswa yang dibagi menjadi dua periode berbeda, yang memerlukan penyelarasan data yang cermat selama fase pra-pemrosesan:
1. **Data Periode 1 (`Data Periode 1`)**: Dataset historis dasar yang berisi demografi siswa dan metrik kinerja awal.
2. **Data Periode 2 (`Data Periode 2`)**: Catatan mahasiswa modern di mana fitur-fitur tertentu diubah namanya, dihilangkan, atau disusun secara berbeda dibandingkan dengan Periode 1.

**Fitur Utama yang Dieksplorasi:**
* Demografi Mahasiswa (Usia, Lokasi/Wilayah, Jenis Kelamin, dll.)
* Detail Pendaftaran Akademik (Program Studi, Jenis Penerimaan)
* Metrik Kinerja (IPK/IPK, Kredit yang Diselesaikan/SKS, Nilai Tugas)
* **Variabel Target:** Status Mahasiswa / Hasil Kelulusan (misalnya, Lulus vs. Berisiko/Gagal)

## 🛠️ Tumpukan Teknologi & Pustaka
* **Bahasa:** Python
* **Manipulasi Data:** `pandas`, `numpy`
* **Visualisasi Data:** `matplotlib`, `seaborn`
* **Pembelajaran Mesin:** `scikit-learn` (Pengklasifikasi Random Forest, train_test_split, classification_report)

## 🔄 Metodologi & Alur Kerja
### 1. Pembersihan & Penyelarasan Data
Karena fitur pada Periode 1 dan Periode 2 tidak sama persis, proses penyelarasan yang kuat dilakukan:
* Menghapus kolom yang tidak diperlukan dan mengidentifikasi fitur penting yang hilang di seluruh periode.
* Menstandarisasi nama kolom (mengganti nama fitur yang tidak cocok antar dataset).
* Menangani nilai yang hilang (imputasi) dan memastikan tipe data yang konsisten.

### 2. Analisis Data Eksplorasi (EDA)
* Menganalisis distribusi demografis siswa yang berhasil vs. siswa yang berisiko.
* Analisis korelasi untuk mengidentifikasi prediktor keberhasilan siswa yang paling signifikan.

### 3. Pelatihan & Evaluasi Model
* Menggabungkan dataset yang telah diselaraskan ke dalam dataframe master yang terpadu.
* Membagi data menjadi set pelatihan dan pengujian.
* Melatih **Pengklasifikasi Random Forest** untuk menangani hubungan non-linier yang kompleks dan interaksi fitur.
* Evaluasi menggunakan metrik Akurasi, Presisi, Recall, dan F1-Score untuk memastikan minimalnya false negative (tidak terlewatnya siswa yang berisiko).
