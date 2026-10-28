# 🌿 GreenWaste 7 — Autonomous Waste Sorting Core

Web Dashboard modern, minimalis, dan futuristik untuk sistem pemilahan sampah otomatis 7 kategori (**GreenWaste 7**).

---

## 🚀 Fitur Utama

1. **Panel Kamera Real-Time (WebRTC Viewport)**:
   - Akses langsung ke webcam fisik perangkat secara real-time (`navigator.mediaDevices.getUserMedia`).
   - Mendukung peralihan kamera depan/belakang (*flip/cycle camera*).
   - Dilengkapi **AI HUD & Laser Scanning Overlay**: reticle target, visualisasi bounding box ber-gaya sci-fi/cyber-industrial, confidence score, dan indikator latensi inferensi.
   - **Mode Demo Sim**: Jika tidak ada kamera fisik atau izin ditolak, sistem otomatis beralih ke simulasi sabuk konveyor industri bergerak.
   - Tombol manual **"Classify Now"** untuk memicu snapshot klasifikasi.

2. **Visualisasi 7 Kategori Sampah Lengkap**:
   - 🔷 **Plastic** (PET, HDPE, kantong plastik, botol air minum) — *Chute #1*
   - 🔶 **Paper** (Kardus, kertas majalah, cup kertas) — *Chute #2*
   - ⚙️ **Metal** (Kaleng soda aluminium, tutup botol, besi seng) — *Chute #3*
   - 🟣 **Cloth** (Kain tekstil, potongan pakaian, kapas) — *Chute #4*
   - 🔴 **Styrofoam** (Gabus styrofoam EPS, wadah makanan busa) — *Chute #5*
   - 🟢 **Organic** (Sisa makanan, kulit buah, sampah organik basah) — *Chute #6*
   - 💎 **Glass** (Botol kaca bening/amber, pecahan kaca, toples) — *Chute #7*

3. **Simulasi Aktuator Pneumatik 7-Lane**:
   - Visualisasi lampu LED dan katup pengarah (*pneumatic chute diverter*) yang bereaksi secara instan ketika material sampah terdeteksi.

4. **Metrik Lingkungan & Analitik**:
   - Penghitung total item & akumulasi bobot sampah terpilah (kg).
   - Estimasi reduksi jejak karbon (*CO₂ Equivalent Offset*).
   - Rasio daur ulang (*Recyclability Rate*).
   - Donut Chart dinamis (Chart.js) rasio distribusi bobot material secara live.

5. **Efek Audio Futuristik (Web Audio API Synthesizer)**:
   - Suara *lock-on chirp* & klik katup solenoid pneumatik sintetis (dapat dinyalakan/dimatikan dengan tombol SFX).

6. **Audit Telemetry Log & Ekspor CSV**:
   - Log aktivitas pemilahan real-time dengan timestamp detik.
   - Tombol ekspor instan ke format `.csv` untuk laporan berkala.

---

## 💻 Cara Menjalankan

### Cara 1: Buka Langsung di Browser
Cukup klik ganda (double-click) file `index.html` di File Explorer, atau jalankan perintah berikut di terminal:
```powershell
Start-Process "C:\Users\HYPE AMD\.gemini\antigravity\scratch\greenwaste-7\index.html"
```

### Cara 2: Menjalankan via Local Web Server (Direkomendasikan untuk izin Camera API)
Beberapa browser membatasi akses webcam pada protokol `file://`. Untuk pengalaman terbaik, jalankan server statis lokal:

**Menggunakan Node.js / npx:**
```powershell
cd "C:\Users\HYPE AMD\.gemini\antigravity\scratch\greenwaste-7"
npx serve
```

**Atau menggunakan Python:**
```powershell
cd "C:\Users\HYPE AMD\.gemini\antigravity\scratch\greenwaste-7"
python -m http.server 3000
```
Lalu buka: `http://localhost:3000` di Google Chrome / Edge / Firefox.

---

## 🎨 Desain & Arsitektur
- **Minimalist & Clean**: Palet warna Obsidian Dark (`#070a12`), Slate, dan aksen Neo-Emerald ramah lingkungan.
- **Tanpa Build Step Rumit**: Tailwind CSS via CDN, Lucide Icons, dan Chart.js murni di browser.
