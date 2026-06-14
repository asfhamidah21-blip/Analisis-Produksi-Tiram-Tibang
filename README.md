#Penerapan Regresi Linier Berganda untuk Menganalisis Pengaruh Luas Areal *Mangrove* dan Suhu Perairan terhadap Produksi Tiram
*Studi Kasus: Desa Tibang, Banda Aceh*

##1. Problem Bisnis
Petani tiram di Desa Tibang mengalami fluktuasi produksi yang tidak stabil setiap musim. Hal ini menyulitkan perencanaan dan pendapatan. Penelitian ini bertujuan menganalisis sebarapa besar pengaruh luas areal mangrove dan suhu perairan terhadap produksi tiram, agar bisa dibuat rekomendasi berbasis data untuk menjaga stabilitas produksi

##2. Data & Cleaning 

  Data yang digunakan adalah data sekunder periode [2010-2022] dari Dinas Lingkungan Hidup, Kebersihan dan Keindahan Kota Banda Aceh (DLHK3) & catatan nelayan tiram.
- Variabel dependen (Y): Produksi tiram (ton/bulan)
- Variabel independen (X): Luas areal mangrove (hektar)
- Variabel independen (X2): Suhu perairan (°C)

  Proses cleaning yang dilakukan:
- Mengecek outlier menggunakan metode Interquartile Range(IQR) untuk variabel luas areal mangrove, suhu perairan dan produksi tiram
  Hasil menunjukkan:
- Luas areal: 0 outlier dari 45 data (0%)
- Suhu perairan: 1 outlier dari 45 data (2.2%), data tersebut tidak bisa dihapus untuk menjaga keutuhan dataset asli
- Produksi tiram: 0 outlier dari 45 data (0%)

##3. Analisis Regresi Linier Berganda
Model regresi linier berganda digunakan untuk melihat hubungan simultan antara luas mangrove dan suhu perairan terhadap produksi tiram.

Persamaan model:
**Produksi = β0 + β1(Luas Mangrove) + β2(Suhu Perairan) + ε**

Hasil utama:
- Nilai R-squared: 0.739 → artinya 73.9% variasi produksi tiram dapat dijelaskan oleh luas mangrove dan suhu perairan.
- Nilai p-value untuk Luas Mangrove: 0.00. maka berpengaruh signifikan.
- Nilai p-value untuk Suhu Perairan: 0.00.maka berpengaruh signifikan.

Analisis lengkap dengan kode dan uji asumsi klasik bisa dilihat di notebook:
[Link Notebook Colab/GitHub kamu]

##4. Visualisasi
Grafik hubungan antara variabel independen dan dependen:
![Scatterplot Luas Mangrove vs Produksi](link-gambar-1.png)
![Scatterplot Suhu Perairan vs Produksi](link-gambar-2.png)

Gambar-1 di atas menunjukkan tren positif antara luas mangrove dan produksi tiram.
Gambar-2 di atas menunjukkan tren negatif antara suhu perairan dan produksi tiram.

##5. Rekeomendasi Bisnis
Berdasarkan hasil analisis, berikut rekomendasi untuk petani dan pemerintah desa:
1. Jaga dan perluas areal mangrove: Hasil menunjukkan bahwa peningkatan luas mangrove berkorelasi positif dengan produksi tiram. Program reboisasi mangrove perlu diprioritaskan.
2. Monitoring suhu perairan: Suhu yang terlalu tinggi/tinggi berpengaruh negatif. Perlu sistem monitoring suhu untuk menentukan waktu panen yang optimal.
3. Perencanaan panen berbasis data: Gunakan model ini untuk memprediksi hasil panen 3-6 bulan ke depan berdasarkan kondisi lingkungan saat ini.

##6. Keterbatasan dan Validitas Model
Model ini memiliki beberapa keterbatasan:

Model regresi linier berganda mengasumsikan hubungan antara suhu perairan dan produksi tiram berbentuk garis lurus. 
Namun, berdasarkan wawancara dengan nelayan tiram Desa Tibang, suhu optimal untuk pertumbuhan daging tiram berada di rentang 27-30°C. 
Di luar rentang tersebut, produksi tetap ada namun hasil daging berkurang. 

Artinya hubungan yang sebenarnya bersifat non-linier, mirip bentuk kurva parabola. 
Karena keterbatasan model, efek penurunan produksi di suhu >30°C tidak tertangkap penuh oleh koefisien linier. 
Untuk pengembangan selanjutnya, disarankan menggunakan regresi polinomial atau segmentasi data berdasarkan rentang suhu optimal.
