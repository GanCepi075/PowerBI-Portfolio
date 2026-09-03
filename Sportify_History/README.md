Spotify Listening History Analysis

Analisis kebiasaan mendengarkan musik pribadi berdasarkan data histori streaming Spotify (2013–2024), menggunakan Python untuk data cleaning, exploratory data analysis (EDA), dan visualisasi.

Latar Belakang

Spotify menyediakan data mentah histori streaming penggunanya. Project ini bertujuan menggali pola-pola menarik dari data tersebut: artist favorit, waktu mendengarkan yang paling aktif, kebiasaan skip lagu, dan tren jangka panjang dari tahun ke tahun.

Dataset
Sumber: Personal Spotify Streaming History (diunduh dari Kaggle / permintaan data pribadi ke Spotify)
Jumlah data: 149.860 baris, 11 kolom
Kolom utama: ts (waktu streaming), track_name, artist_name, album_name, ms_played, platform, shuffle, skipped, reason_start, reason_end
Tools yang Digunakan
Python (pandas, numpy)
Matplotlib & Seaborn untuk visualisasi
Jupyter Notebook
Proses Analisis
1. Data Cleaning
Kolom ts dikonversi dari teks ke format datetime
Baris dengan missing value di reason_start dan reason_end (kurang dari 0.1% dari total data) di-drop karena jumlahnya sangat kecil
Kolom tambahan diekstrak dari ts: hour, day_name, month, year
Kolom minutes_played dibuat dari ms_played untuk mempermudah interpretasi
2. Exploratory Data Analysis

Analisis difokuskan untuk menjawab pertanyaan berikut:

Artist apa yang paling sering dan paling lama didengarkan?
Jam dan hari apa waktu mendengarkan musik paling aktif?
Seberapa sering lagu di-skip, dan apakah shuffle mempengaruhinya?
Bagaimana tren mendengarkan musik dari tahun ke tahun?
Insight Utama
The Beatles adalah artist paling sering diputar sekaligus paling lama total durasi mendengarkannya, menunjukkan preferensi yang konsisten.
Ditemukan perbedaan menarik antara "sering diputar" vs "lama didengarkan" — beberapa artist seperti Howard Shore (soundtrack film) masuk peringkat atas durasi meski jarang diputar, karena durasi lagunya yang panjang.
Waktu mendengarkan musik paling tinggi terjadi di sore-malam hari (jam 16:00–23:00), sementara paling rendah di siang hari (jam 09:00–14:00) — pola ini konsisten dengan jam aktivitas kerja/sekolah.
Jumat adalah hari dengan total waktu mendengarkan tertinggi, sementara akhir pekan (Sabtu-Minggu) justru terendah — berkebalikan dengan asumsi umum bahwa weekend lebih santai untuk mendengarkan musik.
Skip rate keseluruhan cukup rendah (5.18%), tapi meningkat menjadi 5.54% saat mode shuffle aktif dibanding 4.11% saat mode manual — menunjukkan lagu yang diputar secara acak sedikit lebih rentan di-skip.
Terjadi lonjakan signifikan pada waktu mendengarkan di tahun 2020–2021, kemungkinan berkaitan dengan pandemi COVID-19 dan meningkatnya waktu di rumah, diikuti penurunan bertahap di 2022–2024.
Rekomendasi Lanjutan

Analisis ini bisa dikembangkan lebih lanjut dengan:

Analisis sentimen atau genre berdasarkan API Spotify (audio features: energy, valence, tempo)
Prediksi kemungkinan skip menggunakan model machine learning sederhana
Perbandingan pola mendengarkan sebelum dan sesudah momen penting (pandemi, rilis album besar, dll)
