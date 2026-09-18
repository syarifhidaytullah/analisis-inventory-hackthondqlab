# Juara 1 DQLab Excel Hackathon — Inventory Replenishment & Capacity Planning

Repository ini mendokumentasikan berkas penyelesaian studi kasus **Hackathon Excel September 2026 (EXCEL-DQLAB-HACK02)** yang diselenggarakan oleh **DQLab.id** bersama **UjiKompetensi.com**.

🏆 **Pencapaian: Juara 1 Nasional**

---

## 📌 Ringkasan Proyek & Studi Kasus
Simulasi manajemen rantai pasok (*supply chain management*) dan perencanaan pengisian kembali persediaan (*inventory replenishment*) distributor multi-produk (**PT DQLab Distributor Sehari-hari**) untuk 5 SKU produk sepanjang 12 bulan (Januari – Desember 2026).

### 🎯 Tujuan Utama:
1. **Proyeksi Permintaan 12 Bulan (168 Baris):** Mengekspansi order bulanan dengan logika tanggal konsisten dan kalkulasi persentase kenaikan/penurunan kuantitas order bersyarat (`ROUNDUP`).
2. **Kalkulasi Rolling Demand 6 Hari:** Menghitung total kebutuhan barang selama lead time siklus (3 hari pengantaran toko + 3 hari pemesanan supplier) menggunakan `SUMIFS` dinamis.
3. **Penetapan Ambang Min & Max Inventory:** Menentukan batas bawah pemicu pemesanan dan target stok ideal dengan formula agregasi bersyarat `MINIFS` dan `MAXIFS`.
4. **Simulasi Reorder Point & Replenishment (64 Event):** Melacak pergerakan stok akumulatif (Inbound, Outbound, Current Stock) serta memicu reorder secara sekuensial kronologis menggunakan relasional `INDEX-MATCH`.
5. **Monitoring Utilisasi Kapasitas Gudang Bersama (*Shared Space*):** Menghitung rasio keterisian ruang gudang gabungan untuk 5 SKU terhadap kapasitas masing-masing produk dengan ketelitian pembulatan 2 desimal.

---

## 🛠️ Prinsip Rekayasa Spreadsheet
- **Arsitektur Modular 3 Lapis (*Data-Helper-Summary*):** Pemisahan tegas antara data input (`Demand Projection`), parameter gudang (`Capacity`), mesin kalkulasi stok (`Helper`), dan ringkasan eksekutif (`Warehouse`) agar alur data transparan dan bebas kesalahan sel tertimpa.
- **Formula Aktif Dinamis Bebas Hardcode:** Menggunakan kombinasi formula standar modern (`INDEX`, `MATCH`, `SUMIFS`, `DATE`, `ROUNDUP`, `MINIFS`, `MAXIFS`) tanpa konstanta statis pada sel perhitungan.
- **Integritas OpenXML & Autograder Ready:** Mempertahankan konfigurasi `fullCalcOnLoad='0'` dan menginjeksi pre-calculated value (`<v>`) sehingga file langsung terbaca valid di autograder headless Linux maupun aplikasi Excel Mobile (Android & iOS).

---

## 📂 Struktur Berkas Repository

```
├── INVENTORY-DQLAB-092026.xlsx                        # Workbook Excel utama penyelesaian lomba
├── JAWABAN-EXCEL-HACK02.xlsx                          # Salinan berkas submit jawaban
├── Laporan-Penyelesaian-Lomba-Excel.pdf               # Laporan komprehensif metodologi & verifikasi formula
├── Bedah-Rumus-Klasik-vs-Modern.pdf                   # Analisis komparasi formula klasik vs modern
└── Hackathon September 2026 – Inventory Replenishment.pdf # Panduan dan soal resmi hackathon
```

---

## 📊 Ringkasan Hasil & Ground Truth

| Parameter | Hasil Analisis | Validasi Kunci Jawaban |
| :--- | :--- | :--- |
| **Total Periode Demand** | 12 Bulan (168 Transaksi) | ✅ Cocok 100% |
| **Total Event Reorder** | 64 Transaksi Reorder | ✅ Cocok 100% |
| **Utilisasi Stok Awal (01-Jan-2026)** | 1.21 (Overcapacity 21%) | ✅ Cocok 100% |
| **Utilisasi Reorder #1 (10-Jan-2026)** | 0.84 | ✅ Cocok 100% |
| **Utilisasi Reorder #2 (12-Jan-2026)** | 0.91 | ✅ Cocok 100% |

---

## 👤 Profil & Kontak
- **Nama:** Syarif Hidayatullah
- **Portfolio:** [syarifhidayatullah.web.id](https://www.syarifhidayatullah.web.id)
- **GitHub:** [@syarifhidaytullah](https://github.com/syarifhidaytullah)
- **Fastwork:** [@syarif112](https://fastwork.id/user/syarif112)
- **Email:** syarifhidaytul11@gmail.com
