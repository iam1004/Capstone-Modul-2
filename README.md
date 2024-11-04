# Angel_Capstone2 - Supermarket Customers
## Overview
Dalam pasar ritel yang berkembang pesat, supermarket menghadapi tantangan yang signifikan. Dengan meningkatnya persaingan baik dari pengecer fisik maupun online, loyalitas pelanggan dipertaruhkan. Meskipun basis pelanggannya kuat, manajemen khawatir dengan penurunan angka penjualan pada kategori produk tertentu dan tanggapan kampanye yang tidak konsisten. 
## Pernyataan Masalah
Manajemen menyadari perlunya memanfaatkan data pelanggan secara lebih efektif untuk perkembangan supermarket kedepannya. Informasi ini akan membantu manajemen supermarket untuk memahami perilaku pembelanjaan, mengoptimalkan promosi, dan meningkatkan keterlibatan pelanggan.

Sebagai data analyst dari supermarket ini, kita akan mencoba menjawab pertanyaan berikut :
* **Bagaimana karakteristik / perilaku customer dan pola belanjanya?**
* **Apakah promosi dan kampanye sudah optimal?**
* **Bagaimana cara meningkatkan revenue?**
## Data
Untuk mengatasi masalah ini, supermarket telah mengumpulkan data pelanggan yang luas, termasuk demografi, riwayat pembelian, tanggapan promosi, dan preferensi saluran. 

Berikut adalah data yang diisi customer saat berbelanja di supermarket. Ada 29 column di dalam dataset Supermarket Customers, yaitu:

* ID: Customer's unique identifier
* Year_Birth: Customer's birth year
* Education: Customer's education level
* Marital_Status: Customer's marital status
* Income: Customer's yearly household income
* Kidhome: Number of children in customer's household
* Teenhome: Number of teenagers in customer's household
* Dt_Customer: Date of customer's enrollment with the company
* Recency: Number of days since customer's last purchase
* Complain: 1 if the customer complained in the last 2 years, 0 otherwise
* MntWines: Amount spent on wine in last 2 years
* MntFruits: Amount spent on fruits in last 2 years
* MntMeatProducts: Amount spent on meat in last 2 years
* MntFishProducts: Amount spent on fish in last 2 years
* MntSweetProducts: Amount spent on sweets in last 2 years
* MntGoldProds: Amount spent on gold in last 2 years
* NumDealsPurchases: Number of purchases made with a discount
* AcceptedCmp1: 1 if the customer accepted the offer in the 1st campaign, 0 otherwise
* AcceptedCmp2: 1 if the customer accepted the offer in the 2nd campaign, 0 otherwise
* AcceptedCmp3: 1 if the customer accepted the offer in the 3rd campaign, 0 otherwise
* AcceptedCmp4: 1 if the customer accepted the offer in the 4th campaign, 0 otherwise
* AcceptedCmp5: 1 if the customer accepted the offer in the 5th campaign, 0 otherwise
* Response: 1 if the customer accepted the offer in the last campaign, 0 otherwise
* NumWebPurchases: Number of purchases made through the company’s website
* NumCatalogPurchases: Number of purchases made using a catalog
* NumStorePurchases: Number of purchases made directly in stores
* NumWebVisitsMonth: Number of visits to the company’s website in the last month

Sebelum masuk ke dalam analisis, kita perlu mengenal dataset kita lebih jauh dalam tahapan *data understanding*. Dari proses ini, kita akan tahu anomali-anomali apa saja yang terdapat di dalam dataset kita dan perlu ditangani dalam tahapan *data cleaning*.

Secara umum, kita bisa melihat bahwa:
* dataset hr_analytics memiliki 29 kolom dan 2.240 baris.
* kolom `Income` memiliki data kosong.
* tidak ada data duplikat.
* kolom `ID` berisikan id unik untuk tiap customer, sehingga tidak relevan dalam analisis dan bisa dihapus saja.
* kolom `Z_CostContact` dan `Z_Revenue` memiliki mean, min, max dan kuartil yang sama, sehingga memiliki kemungkinan semua nilai sama. Mari kita cek lebih detil, jika iyah maka akan dihapus karena tidak berpengaruh dalam analisis.
* `Education` merupakan data kategorik ordinal, bisa dibuatkan kolom baru berdasarkan ranking kategorinya untuk memudahkan analisis.
* beberapa data memiliki outliers yang mungkin akan mempengaruhi analisis. Mari kita cek lebih detail.

Setelah mengetahui anomali-anomali apa saja yang terdapat di dalam dataset, kita akan masuk dalam tahapan *data cleaning*. Setiap penangan anomali yang ditangani, akan disertai dengan justifikasi langkah yang diambil, baik secara *domain knowledge* maupun secara statistik.
## Data Analysis
Setelah melalui tahap data cleaning, kita akan mulai melakukan analisis data untuk mencari tahu karakteristik customer dengan pembelian paling tinggi

Dari hasil analisis, kita dapat mengambil kesimpulan berikut tentang customer supermarket:
* Jumlah orang dalam rumah tangga tidak berpengaruh pada jumlah belanjaan.
* Faktor yang paling berpengaruh pada jumlah belanja adalah penghasilan.
* Wine merupakan segment dengan jumlah belanja paling banyak.
* Majoritas customer supermarket adalah orang yang sudah menikah, berpasangan atau berkeluarga.
* Sering atau jarang nya customer berbelanja tidak mempengaruhi jumlah belanja.
* Dari 2237 data yang terkumpulkan, hanya 20 (kurang dari 1%) komplain yang diterima.
* Promosi terakhir (last campaign) persentase diterima paling tinggi yaitu 15%.
* Pelanggan yang telah menerima tawaran sebelum nya cendrung menerima tawaran kedepannya.
* 46% customer berbelanja langsung di toko sedangkan hanya 32% belanja online dan 21% melalui katalog.
## Recommendation
Berdasarkan analisis yang telah dilakukan, berikut beberapa rekomendasi untuk supermarket:
* Fokus pada Promosi Produk Wine: Karena wine merupakan segment dengan jumlah belanja paling banyak, pertimbangkan untuk meningkatkan promosi, menawarkan diskon, atau menyelenggarakan acara tasting wine untuk menarik lebih banyak pelanggan.
* Kampanye Berdasarkan Penghasilan: Mengingat penghasilan berpengaruh besar terhadap jumlah belanja, kembangkan kampanye yang ditargetkan berdasarkan segmentasi penghasilan. Misalnya, tawarkan produk premium untuk segmen berpenghasilan tinggi dan produk dengan harga lebih terjangkau untuk segmen berpenghasilan rendah.
* Program Loyalitas untuk Pasangan: Karena mayoritas customer adalah orang yang sudah menikah atau berpasangan, buat program loyalitas atau penawaran khusus yang menarik bagi mereka, seperti diskon untuk pembelian bersama atau hadiah untuk pasangan.
* Menambahkan Produk untuk Keluarga: Mengingat sebagian besar customer adalah orang yang sudah berkeluarga, maka tambahkan produk yang sesuai untuk keluarga (contoh : beras 5kg atau 10kg, bukan hanya kemasan1kg) dan juga untuk anak-anak (susu formula, popok bayi, makanan ringan) untuk meningkatkan penjualan.
* Tawarkan Tawaran Berulang: Karena pelanggan yang telah menerima tawaran sebelumnya cenderung menerima tawaran selanjutnya, ciptakan siklus tawaran yang menarik dan relevan untuk mendorong pembelian berulang.
* Peningkatan Pengalaman Berbelanja di Toko: Mengingat lebih banyak pelanggan berbelanja langsung di toko, perbaiki pengalaman berbelanja di toko dengan menciptakan suasana yang nyaman, menawarkan layanan pelanggan yang baik, dan memanfaatkan promosi di lokasi.
Dengan menerapkan rekomendasi ini, supermarket dapat meningkatkan kepuasan pelanggan dan mendorong pertumbuhan penjualan.
