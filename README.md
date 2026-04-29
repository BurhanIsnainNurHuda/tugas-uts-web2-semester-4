# tugas-uts-web2-semester-4

    Nama: Burhan Isnain Nur Huda  
    NIM: 312410226  
    Kelas: I241B 
    Mata Kuliah: Pemrograman Web 2
    WebSocket vs HTTP Polling — Eksperimen Chat Real-Time

#  WebSocket vs HTTP Polling — Eksperimen Chat Real-Time

> **Tugas UTS Pemrograman Web**  
> Artikel: *"WebSocket vs HTTP: Eksperimen Membangun Aplikasi Chat Real-Time Sederhana"*

---

##  Deskripsi

Repository ini berisi kode sumber eksperimen perbandingan dua pendekatan komunikasi dalam pengembangan aplikasi web:

| Pendekatan | Port | Deskripsi |
|---|---|---|
| **HTTP Polling** | `3000` | Klien mengecek pesan baru ke server setiap 2 detik |
| **WebSocket** | `3001` | Satu koneksi persisten, pesan dikirim langsung (real-time) |

---

##  Struktur Project
chat-app/
├── server-http.js       # Server HTTP Polling (Express.js, port 3000)
├── server-ws.js         # Server WebSocket (library ws, port 3001)
├── package.json
├── public-http/
│   └── index.html       # Klien chat HTTP Polling
└── public-ws/
└── index.html       # Klien chat WebSocket

---

##  Teknologi

- **Runtime:** Node.js v20+
- **HTTP Server:** Express.js v4
- **WebSocket:** library `ws` v8
- **Frontend:** HTML5, CSS3, Vanilla JavaScript

---

##  Cara Menjalankan

### 1. Install Dependencies
```bash
npm install
```

### 2. Jalankan HTTP Polling
```bash
node server-http.js
```
Buka browser → **http://localhost:3000**

### 3. Jalankan WebSocket
```bash
node server-ws.js
```
Buka browser → **http://localhost:3001**

---

##  Hasil Eksperimen

| Parameter | HTTP Polling | WebSocket |
|---|---|---|
| Jumlah request/menit | ~40 request otomatis | 1 koneksi persisten |
| Latensi pesan | 0 – 2.000 ms | < 50 ms |
| Overhead per event | ~178 byte | ~2–10 byte |
| Responsivitas | Ada delay | Seketika |

---

##  Cara Mengamati di DevTools

**HTTP Polling:**
1. Buka `http://localhost:3000` → tekan **F12** → tab **Network**
2. Lihat request `GET /messages` muncul otomatis setiap 2 detik

**WebSocket:**
1. Buka `http://localhost:3001` → tekan **F12** → tab **Network** → filter **Socket**
2. Hanya **1 koneksi** WebSocket yang terbuka sepanjang sesi

---

##  Referensi

1. Fette, I., & Melnikov, A. (2011). *The WebSocket Protocol*. RFC 6455. IETF.
2. Eka Putra et al. (2024). Analisis Komparasi Protokol Websocket dan MQTT. *Jurnal Sistim Informasi dan Teknologi*, 5(4).
3. Saputra & Latif (2024). Analisis Performa Real-Time Data Streaming Menggunakan WebSocket. *JEKIN*, 16(2).
4. [MDN WebSocket API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
5. [Node.js Documentation](https://nodejs.org/en/docs/)

---

##  Lisensi

MIT License — bebas digunakan untuk keperluan pembelajaran.
