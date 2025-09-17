# Analisis Pasar Airbnb Bangkok

## Gambaran Umum Proyek

Proyek ini menyajikan analisis komprehensif terhadap pasar Airbnb di
Bangkok, Thailand. Tujuannya adalah memberikan wawasan yang dapat
ditindaklanjuti oleh perusahaan manajemen properti maupun
investor/pengembang properti. Analisis dilakukan melalui eksplorasi data
(EDA) serta pengujian hipotesis statistik untuk mengungkap pola pasar
dan peluang bisnis.

## Tujuan Bisnis

### Pihak yang Berkepentingan:

1.  **Perusahaan Manajemen Properti** -- membutuhkan wawasan operasional
    untuk mengoptimalkan portofolio.\
2.  **Investor/Pengembang Properti** -- membutuhkan intelijen pasar
    untuk mendukung keputusan investasi strategis.

### Pertanyaan Penelitian Utama:

-   Karakteristik listing Airbnb seperti apa yang paling diminati?\
-   Bagaimana hubungan harga dengan lokasi dan tipe kamar?\
-   Apa perbedaan utama antara host profesional dan host kasual?\
-   Bagaimana ketersediaan unit mencerminkan permintaan pasar?\
-   Apa tren aktivitas terkini di pasar Airbnb Bangkok?

## Informasi Dataset

-   **Sumber**: Dataset Airbnb Bangkok\
-   **Jumlah Data**: Lebih dari 15.000 listing di 50 distrik\
-   **Fitur**: Harga, lokasi, tipe kamar, data host, ulasan, dan
    ketersediaan\
-   **Periode**: Snapshot kondisi pasar saat ini, dilengkapi dengan data
    historis ulasan

## Metodologi

### Analisis Statistik yang Digunakan:

-   **Eksplorasi Data (EDA)** -- untuk menemukan pola dan karakteristik
    pasar\
-   **Uji Hipotesis** -- untuk memvalidasi asumsi bisnis secara
    statistik\
-   **Analisis Korelasi** -- untuk mengidentifikasi hubungan
    antarvariabel\
-   **Uji ANOVA** -- untuk membandingkan harga berdasarkan tipe kamar\
-   **Uji T** -- untuk membandingkan performa host

### Tingkat Keyakinan: 95% (α = 0,05)

## Struktur Proyek

    Proyek Capstone Modul 2/
    ├── Airbnb_Bangkok_MGRS.ipynb                # Notebook analisis utama
    ├── Airbnb Listings Bangkok.csv              # Dataset mentah
    ├── Airbnb_Listings_Bangkok_cleaned.csv      # Dataset setelah pembersihan
    ├── Airbnb_Dictionary.pdf                    # Dokumentasi data
    ├── Chart_Generation_for_PPT.py              # Kode visualisasi untuk presentasi
    ├── Catatan_Presentasi_Airbnb_Bangkok.md     # Catatan pembicara presentasi
    ├── Chart_*.png                              # Grafik hasil visualisasi
    ├── Airbnb_Bangkok_PPT_Content.txt           # Draft isi presentasi
    └── README.md                                # Dokumentasi proyek

## Langkah Penggunaan

### Prasyarat:

``` python
pandas >= 1.3.0
numpy >= 1.21.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
scipy >= 1.7.0
plotly >= 5.0.0 (opsional)
```

### Instalasi:

``` bash
pip install pandas numpy matplotlib seaborn scipy plotly
```

### Cara Menjalankan Analisis:

1.  Unduh atau klon proyek ini.\
2.  Pastikan file dataset CSV tersedia pada direktori yang sama.\
3.  Buka file `Airbnb_Bangkok_MGRS.ipynb` menggunakan Jupyter Notebook
    atau Jupyter Lab.\
4.  Jalankan seluruh sel secara berurutan.

## Temuan Utama

### 1. Karakteristik Pasar dan Popularitas

-   **Tipe kamar paling populer**: Apartemen/rumah seutuhnya dan kamar
    hotel.\
-   **Distrik dengan ulasan tertinggi**:
    -   Khlong Toei: 41.279 ulasan\
    -   Vadhana: 37.415 ulasan\
    -   Sathon: 22.242 ulasan\
    -   Ratchathewi: 20.692 ulasan\
    -   Huai Khwang: lebih dari 18.000 ulasan

### 2. Informasi Harga

-   **Wilayah premium**: Lat Phrao (฿3.538), Pathum Wan (฿3.454), Nong
    Chok (฿3.279).\
-   **Wilayah dengan harga terjangkau**: Lak Si, Nong Khaem, Don Mueang,
    Phasi Charoen.\
-   **Hasil uji ANOVA** menunjukkan terdapat perbedaan harga yang
    signifikan antar tipe kamar (p \< 0,05).

### 3. Pola Performa Host

-   Host profesional memiliki tingkat aktivitas ulasan 2,3 kali lebih
    tinggi dibanding host kasual (0,62 vs 0,26 ulasan/bulan).\
-   Host profesional lebih fokus pada efisiensi operasional dibanding
    penetapan harga premium.\
-   Uji T membuktikan perbedaan ini signifikan secara statistik (p \<
    0,05).

### 4. Dinamika Permintaan dan Ketersediaan

-   Terdapat korelasi negatif yang cukup kuat (-0,38) antara
    ketersediaan unit dan jumlah ulasan.\
-   Distrik Huai Khwang dan Vadhana memperlihatkan permintaan tinggi
    (ketersediaan rendah dengan ulasan tinggi).\
-   Properti dengan ketersediaan \<100 hari/tahun menjadi indikator kuat
    adanya permintaan tinggi.

## Hasil Uji Statistik

  -----------------------------------------------------------------------------
  Hipotesis       Jenis Uji       Hasil        P-Value      Interpretasi
  --------------- --------------- ------------ ------------ -------------------
  H1: Terdapat    ANOVA           Signifikan   \< 0,05      Harga berbeda
  perbedaan harga                                           secara signifikan
  berdasarkan                                               antar tipe kamar
  tipe kamar                                                

  H2: Hubungan    Korelasi        Tidak        \> 0,05      Popularitas tidak
  antara                          signifikan                berkorelasi dengan
  popularitas dan                                           harga distrik
  harga                                                     

  H3: Aktivitas   Uji T           Signifikan   \< 0,05      Host profesional
  host                                                      lebih aktif
  profesional                                               dibanding host
  lebih tinggi                                              kasual

  H4: Hubungan    Korelasi        Signifikan   \< 0,05      Ketersediaan rendah
  ketersediaan                                              mencerminkan
  dengan                                                    permintaan tinggi
  permintaan                                                
  -----------------------------------------------------------------------------

## Rekomendasi Bisnis

### Untuk Perusahaan Manajemen Properti:

-   **Strategi Lokasi**: Prioritaskan ekspansi ke distrik Khlong Toei,
    Vadhana, dan Sathon.\
-   **Strategi Harga**: Terapkan harga dinamis sesuai pola permintaan di
    tiap distrik.
