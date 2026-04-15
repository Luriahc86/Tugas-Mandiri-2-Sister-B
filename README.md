# Simulasi Komunikasi Sistem Terdistribusi

Visualisasi interaktif berbasis web untuk mempelajari dua pola komunikasi pada sistem terdistribusi:

- **Request-Response** (sinkron, client-server)
- **Publish-Subscribe** (asinkron, publisher-broker-subscriber)

Project ini cocok untuk kebutuhan pembelajaran, presentasi kelas, dan demo konsep dasar arsitektur komunikasi terdistribusi.

---

## Deskripsi Project

Aplikasi ini dibuat dalam **satu file HTML** (`distributed_comm_simulation.html`) dengan CSS dan JavaScript terintegrasi (tanpa framework eksternal).  
Fokus utama project:

- memperlihatkan alur pesan secara visual menggunakan animasi canvas,
- membandingkan karakteristik dua pola komunikasi,
- memberikan metrik sederhana seperti latency, throughput, jumlah pesan sukses, dan error/timeout.

---

## Fitur Utama

### 1) Tab Request-Response
- Pilih client pengirim dan server tujuan.
- Atur latency jaringan melalui slider.
- Kirim request normal atau simulasi timeout.
- Pantau:
  - jumlah request dikirim,
  - jumlah respons diterima,
  - jumlah error,
  - rata-rata latency,
  - log aktivitas pesan.

### 2) Tab Publish-Subscribe
- Pilih publisher/sensor dan topic.
- Publish pesan manual atau aktifkan auto publish.
- Simulasi distribusi pesan melalui broker ke subscriber yang sesuai topic.
- Pantau:
  - jumlah publish,
  - jumlah pesan delivered,
  - subscriber aktif,
  - throughput,
  - log distribusi pesan.

### 3) Tab Perbandingan
- Menampilkan perbandingan konseptual Request-Response vs Publish-Subscribe:
  - sinkron vs asinkron,
  - tight coupling vs loose coupling,
  - karakter latency dan throughput,
  - contoh use case dunia nyata.

---

## Teknologi yang Digunakan

- **HTML5**
- **CSS3**
- **Vanilla JavaScript**
- **Canvas API** untuk animasi topologi jaringan dan alur pesan

Tidak membutuhkan instalasi dependency tambahan.

---

## Cara Menjalankan Project

### Opsi 1 (paling cepat)
1. Buka file `distributed_comm_simulation.html`.
2. Jalankan langsung di browser (Chrome/Edge/Firefox).

### Opsi 2 (disarankan saat demo)
Gunakan local server sederhana agar akses lebih konsisten:

```bash
python -m http.server 8000
```

Lalu buka:

`http://localhost:8000/distributed_comm_simulation.html`

---

## Cara Penggunaan Saat Demo

### Skenario A — Request-Response
1. Masuk tab **Request-Response**.
2. Pilih Client A -> Auth Server.
3. Set latency ke nilai sedang (mis. 600ms), lalu klik **Kirim Request**.
4. Tunjukkan log request dan response.
5. Klik **Simulasi Timeout** untuk menunjukkan kasus gagal.
6. Jelaskan dampaknya ke metrik (error naik, latency/throughput terpengaruh).

### Skenario B — Publish-Subscribe
1. Masuk tab **Publish-Subscribe**.
2. Pilih publisher + topic (mis. `temperature`), lalu klik **Publish Pesan**.
3. Tunjukkan hanya subscriber yang subscribe topic tersebut yang menerima pesan.
4. Aktifkan **Auto Publish** untuk simulasi trafik berkelanjutan.
5. Jelaskan peningkatan throughput dan pola distribusi many-to-many.

### Skenario C — Perbandingan
1. Buka tab **Perbandingan**.
2. Bandingkan latency, throughput, coupling, dan scalability.
3. Hubungkan dengan use case nyata:
   - Request-Response: REST API, query database.
   - Publish-Subscribe: IoT event stream, notifikasi real-time.
---

## Struktur Project

```text
.
├── distributed_comm_simulation.html
└── README.md
```

---

## Pengembangan Lanjutan (Opsional)

- Tambah mode simulasi packet loss/retry.
- Tambah grafik real-time untuk latency dan throughput.
- Pisahkan CSS/JS ke file terpisah agar mudah maintenance.
- Tambahkan test skenario demo dan checklist observasi.

---
