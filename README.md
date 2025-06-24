# Analisis Mutu Air Sungai di Indonesia

## 📘 Latar Belakang Proyek
Air merupakan sumber daya alam yang sangat vital bagi kehidupan manusia, baik untuk kebutuhan domestik, pertanian, industri, hingga ekosistem alamiah. Namun, peningkatan aktivitas manusia seperti urbanisasi, industri, dan pertanian yang tidak terkontrol telah menyebabkan degradasi kualitas air, terutama pada badan-badan air seperti sungai.

Indonesia sebagai negara kepulauan memiliki banyak sungai yang tersebar di berbagai provinsi dan berperan penting sebagai sumber air utama bagi masyarakat. Meskipun demikian, pencemaran sungai masih menjadi permasalahan serius, terutama di daerah padat penduduk dan kawasan industri. Laporan dari berbagai lembaga lingkungan menunjukkan bahwa banyak sungai mengalami penurunan mutu air dari tahun ke tahun akibat limbah domestik, limbah industri, dan sedimentasi.

Dalam konteks ini, analisis data historis mutu air sungai menjadi sangat penting untuk:
1. Memantau tren pencemaran secara berkala,
2. Mengidentifikasi sungai-sungai yang mengalami penurunan kualitas secara signifikan,
3. Memberikan dasar bagi pengambilan keputusan berbasis data oleh pemerintah, LSM, dan masyarakat,
4. Meningkatkan kesadaran publik terhadap pentingnya menjaga kualitas air.

## 🧭 Tujuan Proyek
Proyek ini bertujuan untuk:
<li> Melakukan cleansing dan transformasi data mutu air sungai tahunan di Indonesia.
<li> Menyusun klasifikasi mutu air berdasarkan skor numerik dengan kategori Baik, Sedang, dan Buruk.
<li> Menyajikan visualisasi tren mutu air per provinsi dan per sungai dalam bentuk grafik garis.
<li> Membangun struktur data berbasis dictionary untuk kemudahan analisis dan plotting terstruktur.

## 🔎 Metodologi
### 🔹Sumber Data
Data berasal dari file `status_mutu_air.csv`[^1] yang memuat informasi nama provinsi, nama sungai, dan status mutu air dari tahun 2017 hingga 2022.

### 🔹Data Cleansing
<li> Mengisi nilai kosong (NaN) menggunakan forward-fill (ffill) dan backward-fill (bfill) secara horizontal (per baris).
<li> Menormalkan nilai kategori dengan menghapus spasi dan mengubah huruf ke lowercase agar seragam.

### 🔹Klasifikasi Mutu Air
Kategori mutu air seperti “Cemar Ringan”, “Cemar Sedang”, dan “Cemar Berat” dikonversi ke bentuk numerik:
<li> Baik: 0–10
<li> Sedang: 11–29
<li> Buruk: ≥30

### 🔹Struktur Data
1. Data diubah menjadi nested dictionary `mutu_dict` dengan struktur provinsi -> sungai -> list mutu per tahun.
2. Dictionary tambahan `sungai_dict` dibuat untuk analisis per sungai secara individual.

### 🔹Visualisasi
<li> Plot per provinsi menampilkan semua sungai dalam provinsi tersebut.

<li> Plot per sungai menampilkan tren mutu air tiap sungai dari tahun ke tahun.

<li> Background visual dibagi dalam tiga zona warna: hijau (baik), kuning (sedang), merah muda (buruk).

## 💡 Hasil
<li> Beberapa sungai menunjukkan tren penurunan mutu air yang konsisten dalam kurun waktu 2017–2022.
<li> Provinsi dengan jumlah sungai tercemar berat lebih banyak dapat menjadi target kebijakan prioritas untuk rehabilitasi lingkungan.
<li> Visualisasi memberikan gambaran yang intuitif dan mudah dibaca oleh pemangku kebijakan maupun masyarakat umum.

## 📄 Kesimpulan
Proyek ini menunjukkan bahwa data mutu air sungai dapat diolah dan divisualisasikan secara efektif untuk:
<li> Mengidentifikasi permasalahan lingkungan secara geografis,
<li> Mendorong kolaborasi lintas sektor dalam menjaga kualitas air,
<li> Dan meningkatkan transparansi informasi lingkungan kepada publik.
Dengan integrasi analitik lanjutan seperti clustering atau prediksi tren, proyek ini dapat dikembangkan lebih lanjut menjadi sistem peringatan dini (early warning system) atau dashboard pemantauan mutu air sungai nasional.

---
[^1]: My reference.