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
  
