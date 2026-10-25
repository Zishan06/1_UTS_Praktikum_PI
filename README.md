# Multi-Dataset Information Retrieval System Berbasis CLI

## Deskripsi Proyek

Multi-Dataset Information Retrieval System merupakan sistem pencarian informasi berbasis *Command-Line Interface* (CLI) yang dikembangkan menggunakan Python. Sistem ini digunakan untuk mencari dokumen teks dari lima sumber dataset, yaitu ETD-USK, ETD-UGM, Kompas, Tempo, dan Mojok.

Sistem menerapkan *text preprocessing*, representasi dokumen menggunakan *Bag-of-Words* (BoW), pembentukan indeks dengan Whoosh, serta pemeringkatan hasil pencarian menggunakan *cosine similarity*.

Proyek ini dibuat untuk memenuhi tugas Ujian Tengah Semester Praktikum Penelusuran Informasi.

## Anggota Kelompok

**Kelompok 3**

1. **M. Rayan Zishan** — 2408107010063
2. **Muhammad Sulthan Shadiq** — 2408107010104

## Fitur Utama

- Membaca dokumen teks dari lima sumber dataset.
- Melakukan preprocessing teks.
- Membuat indeks dokumen menggunakan Whoosh.
- Merepresentasikan dokumen menggunakan Bag-of-Words.
- Melakukan pencarian berdasarkan query pengguna.
- Mengurutkan hasil pencarian menggunakan cosine similarity.
- Menampilkan hingga lima hasil pencarian teratas.

## Dataset

Sistem menggunakan lima sumber dataset berikut:

| Dataset | Deskripsi |
|---|---|
| `etd-usk` | Tesis dan disertasi Universitas Syiah Kuala |
| `etd-ugm` | Tesis dan disertasi Universitas Gadjah Mada |
| `kompas` | Artikel berita Kompas |
| `tempo` | Artikel berita dan opini Tempo |
| `mojok` | Artikel populer Mojok |

## Teknologi yang Digunakan

- **Python** — bahasa pemrograman utama.
- **Whoosh** — membangun indeks dokumen.
- **scikit-learn** — representasi Bag-of-Words dan perhitungan cosine similarity.
- **Regular Expression (`re`)** — membersihkan teks.
- **OS (`os`)** — mengelola direktori dan berkas.

## Tahapan Pemrosesan

### 1. Text Preprocessing

Preprocessing dilakukan untuk menyiapkan teks sebelum proses pencarian, meliputi:

- **Case Folding:** mengubah teks menjadi huruf kecil.
- **Tokenization:** memecah teks menjadi kata-kata.
- **Stopword Removal:** menghapus kata umum berdasarkan daftar stopword.

### 2. Indexing

Dokumen yang telah diproses dimasukkan ke dalam indeks menggunakan Whoosh. Informasi dokumen disimpan agar dapat digunakan dalam proses pencarian.

### 3. Representasi Dokumen

CountVectorizer digunakan untuk mengubah dokumen menjadi vektor berdasarkan frekuensi kata dengan pendekatan Bag-of-Words.

### 4. Pencarian dan Ranking

Pengguna memasukkan query pencarian. Sistem memproses query tersebut, menghitung cosine similarity terhadap dokumen, lalu mengurutkan hasil berdasarkan skor kemiripan tertinggi.

## Struktur Direktori

Struktur direktori proyek secara umum adalah sebagai berikut:

```text
1_UTS_Praktikum_PI/
├── 1_UTS_Praktikum_PI.ipynb
├── UTS_PRAK_PI.ipynb
├── UTS_Prak_PI.pdf
├── README.md
└── dataset/
    ├── etd-usk/
    ├── etd-ugm/
    ├── kompas/
    ├── tempo/
    └── mojok/
```

*Catatan: Struktur di atas merupakan gambaran umum. Sesuaikan nama berkas jika berbeda dengan isi repository final.*

## Instalasi Library

Instal library yang diperlukan dengan menjalankan perintah berikut:

```bash
pip install whoosh scikit-learn pandas
```

Jika pengambilan dataset dilakukan melalui web scraping, library tambahan seperti `requests` dan `beautifulsoup4` mungkin diperlukan.

## Cara Menjalankan

1. Buka notebook proyek menggunakan Google Colab atau Jupyter Notebook.
2. Pastikan dataset tersedia pada direktori yang sesuai dengan konfigurasi program.
3. Jalankan sel instalasi dan import library.
4. Jalankan sel preprocessing dan indexing.
5. Jalankan sel pembentukan representasi dokumen dan fungsi pencarian.
6. Jalankan fungsi menu utama untuk menggunakan sistem.
7. Pilih menu pencarian dan masukkan query yang ingin dicari.

Contoh query:

```text
teknologi informasi
```

Sistem kemudian menampilkan dokumen yang sesuai beserta skor cosine similarity.

## Hasil Pengujian

Pengujian dilakukan menggunakan query `teknologi informasi`.

Berdasarkan hasil pengujian di Google Colab:

- Jumlah dokumen yang dilaporkan terindeks: **235 dokumen**.
- Sistem berhasil menjalankan proses pencarian.
- Hasil pencarian diurutkan berdasarkan skor cosine similarity.
- Skor tertinggi yang terlihat pada pengujian: sekitar **0,1781**.

Hasil tersebut menunjukkan bahwa mekanisme dasar indexing, pencarian, dan pemeringkatan dokumen telah berjalan.

## Batasan Sistem

- Kualitas hasil pencarian bergantung pada isi dan keragaman dokumen.
- Preprocessing menggunakan daftar stopword yang ditentukan dalam program.
- Representasi Bag-of-Words berfokus pada frekuensi kata dan tidak memahami makna kata secara mendalam.
- Hasil pencarian dipengaruhi oleh kesesuaian kata antara query dan dokumen.

## Kesimpulan

Multi-Dataset Information Retrieval System berbasis CLI menerapkan tahapan dasar pencarian informasi, mulai dari preprocessing teks, indexing dengan Whoosh, representasi Bag-of-Words, hingga pemeringkatan menggunakan cosine similarity. Sistem ini dirancang untuk membantu pengguna menemukan dokumen relevan dari lima sumber dataset melalui query sederhana.

---

**Program Studi Informatika**  
**Departemen Informatika**  
**Fakultas Matematika dan Ilmu Pengetahuan Alam**  
**Universitas Syiah Kuala — 2026**
