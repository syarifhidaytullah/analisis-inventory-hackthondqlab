# Draft Postingan LinkedIn (Siap Copy-Paste)

---

📊 **Inventory Replenishment & Warehouse Capacity Analysis — PT DQLab Distributor**

Sangat bersyukur dan bangga dapat meraih **Juara 1 Nasional (Rank #1 out of 335 Participants) dengan Score 100 • Honors** pada ajang **Excel Hackathon 2026** yang diselenggarakan oleh **DQLab** bersama **UjiKompetensi.com**! 🏆🎉

Tantangan dalam hackathon ini adalah memecahkan dilema klasik manajemen rantai pasok (*supply chain*):
👉 *"Bagaimana menjaga ketersediaan barang (service level) tanpa kehilangan kontrol atas kapasitas fisik gudang?"*

Melalui simulasi pergerakan inventaris multi-produk (5 SKU) sepanjang 12 bulan (168 transaksi order demand), saya menerapkan metodologi terstruktur **FROM DATA ➔ INSIGHT ➔ ACTION**:

🔹 **1. Demand Analysis:** Memodelkan tren musiman bulanan dengan formula bersyarat dinamis (`ROUNDUP` & `DATE`) tanpa konstanta hardcode.
🔹 **2. Rolling Demand 6 Hari:** Menghitung kebutuhan stok riil selama masa *lead time* (3 hari transit pengiriman toko + 3 hari pemesanan supplier) via `SUMIFS`.
🔹 **3. Sequential Replenishment Simulation:** Melacak pergerakan stok akumulatif (Inbound, Outbound, Sisa Stok) untuk memicu 64 transaksi *reorder point* kronologis.
🔹 **4. Warehouse Capacity Stress Test:** Memonitor rasio okupansi ruang gudang bersama (*shared warehouse space*) terhadap kuota simpan masing-masing SKU.

---

📌 **Key Quantitative Findings:**
• **Total Demand:** 219.178 unit (~219Rb unit)
• **Total Reorder Events:** 64 kali siklus pemesanan
• **Total Reorder Quantity:** 216.649 unit (~217Rb unit)
• **Peak Warehouse Capacity:** **122.82%** (Terjadi *overcapacity* kritis 22.82% di atas kapasitas batas aman 100%)

💡 **Interesting Business Insights:**
1. **Konsentrasi Pareto:** SKU PROD B & PROD D mendominasi lebih dari 58% total permintaan pasar. SKU PROD B menjadi kontributor volume terbesar (71.975 unit reorder).
2. **Divergensi Volume vs Frekuensi:** Quantity terbesar dan frekuensi pemesanan terbesar ternyata tidak berada pada SKU yang sama! SKU PROD A mencatatkan frekuensi tertinggi (16x reorder dalam batch kecil), sedangkan PROD B memesan dalam lot masif (9x reorder).
3. **Capacity Bottleneck:** Akumulasi reorder yang tiba bersamaan memicu lonjakan kapasitas gudang di atas 100% pada 10 dari 12 bulan, dengan titik kritis tertinggi pada April dan Juni (122.82%).

🚀 **Recommended Actions (Data-Driven Roadmap):**
1️⃣ **Prioritize High-Impact SKU:** Terapkan klasifikasi ABC dengan SLA khusus dan tracking lead time ketat untuk PROD B & D.
2️⃣ **Align Replenishment with Capacity:** Jadwalkan kedatangan PO secara bertahap (*staggered delivery*) guna menjaga okupansi di bawah 100% tanpa sewa gudang darurat.
3️⃣ **Dynamic Demand-Driven Planning:** Sesuaikan kuota order dengan tren penurunan musiman di Q3-Q4 (nadir Oktober di 14.7Rb unit).
4️⃣ **Periodic Parameter Audit:** Tinjau ambang Min (safety stock) & Max secara kuartalan mengikuti fluktuasi biaya simpan (*holding cost*) vs biaya pesan.

---

🛠️ **Spreadsheet Engineering & Architecture:**
Proyek ini dibangun dengan arsitektur **3-Tier Data Lineage (Demand – Helper – Warehouse)** dengan formula aktif dinamis dari baris pertama. Struktur OpenXML dikonfigurasi dengan `fullCalcOnLoad='0'` dan pre-calculated values `<v>`, menjamin file 100% autograder-ready dan kompatibel tanpa error/repair popup saat dibuka di Excel Mobile (Android/iOS).

Terima kasih sebesar-besarnya kepada tim **DQLab** (Ibu **Yovita Surianto**) dan **UjiKompetensi.com / Xeratic** (Bapak **Feris Thia**) atas tantangan studi kasus yang sangat komprehensif ini. 

Pencapaian ini menjadi batu loncatan berharga bagi saya untuk terus menghadirkan dampak nyata melalui rekayasa data dan *business intelligence*!

Dokumen portofolio lengkap (PDF carousel 8 slide) dapat dilihat pada slide di atas atau melalui portofolio web saya di: https://syarifhidayatullah.web.id

#DQLAB #UjiKompetensi #Hackathon #DataAnalytics #DataAnalyst #SupplyChain #InventoryManagement #Excel #SpreadsheetEngineering #BusinessAnalytics #Juara1 #Portfolio #CareerJourney #DataDriven
