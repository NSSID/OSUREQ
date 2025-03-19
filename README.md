# Osrequest ( Last Banget )

Bot ini memungkinkan penonton di YouTube Live Chat untuk mengetik `!req beatmap_id`, dan bot akan mengambil detail beatmap dari osu! API lalu mengirimkannya sebagai embed ke Discord Webhook.  

---

## 📌 Fitur  
✅ Membaca pesan di YouTube Live Chat yang berisi `!req beatmap_id`  
✅ Mengambil detail beatmap dari osu! API  
✅ Mengirim embed ke Discord Webhook  

---

## 🚀 Instalasi & Konfigurasi  

### 1. Clone Repository & Masuk ke Direktori  
```sh
git clone https://github.com/neofetchnpc/Osrequest.git
cd Osrequest
```

### 2. Install Dependencies  
```sh
npm install
```

### 3. Buat File `.env`  
Buat file `.env` di root folder dan masukkan API key yang diperlukan:  
```env
# API Key dari Google Cloud untuk YouTube Data API v3
YT_API_KEY=your_youtube_api_key

# API Key dari osu! API
OSU_API_KEY=your_osu_api_key

# Webhook Discord untuk mengirim embed request beatmap
DISCORD_WEBHOOK=https://discord.com/api/webhooks/your_webhook_id/your_webhook_token

# ID Live Chat dari YouTube Streaming
YT_LIVE_CHAT_ID=your_live_chat_id
```

> **Cara mendapatkan `YT_LIVE_CHAT_ID`**  
> - Gunakan YouTube Data API:  
>   ```sh
>   https://www.googleapis.com/youtube/v3/videos?part=liveStreamingDetails&id=VIDEO_ID&key=YT_API_KEY
>   ```
> - Ambil nilai `liveStreamingDetails.activeLiveChatId`  

---

---

## **🔑 Cara Mendapatkan YouTube API Key**  

### **1. Buka Google Cloud Console**  
1. Masuk ke **[Google Cloud Console](https://console.cloud.google.com/)**  
2. Login dengan akun Google yang ingin kamu gunakan.  

### **2. Buat atau Pilih Proyek**  
1. Klik **"Select a project"** (Pilih proyek) di bagian atas.  
2. Klik **"New Project"** (Proyek baru) jika belum ada proyek.  
3. Beri nama proyek (misal: `OsuRequestBot`).  
4. Klik **"Create"** (Buat).  

### **3. Aktifkan YouTube Data API v3**  
1. Di menu sebelah kiri, pilih **"APIs & Services" > "Library"**.  
2. Cari **"YouTube Data API v3"**.  
3. Klik **"Enable"** (Aktifkan).  

### **4. Buat API Key**  
1. Pergi ke **"APIs & Services" > "Credentials"**.  
2. Klik **"Create Credentials"** > **"API Key"**.  
3. Setelah API Key dibuat, salin key tersebut.  

**🔹 Contoh API Key:**  
```
AIzaSyDk_example123456789-abcdefg
```

---

## **📌 Menggunakan API Key di `.env`**
Setelah mendapatkan API Key, tambahkan ke file `.env` seperti ini:  
```env
YT_API_KEY=AIzaSyDk_example123456789-abcdefg
```

---

## 📜 Penggunaan  
Jalankan bot dengan perintah berikut:  
```sh
npm start
```

Bot akan membaca chat YouTube secara berkala dan menangkap request dengan format:  
```
!req 5018968
```

Jika beatmap ditemukan, bot akan mengirim embed ke Discord Webhook dengan detail beatmap.  

---

## 🛠 Troubleshooting  
❓ **Bot tidak membaca chat dari YouTube**  
✔️ Pastikan `YT_LIVE_CHAT_ID` sudah benar  
✔️ Periksa apakah `YT_API_KEY` memiliki akses ke YouTube Data API v3  
✔️ Cek limit kuota API di Google Cloud Console  

❓ **Bot tidak mengirim ke Discord Webhook**  
✔️ Periksa apakah URL webhook di `.env` sudah benar  
✔️ Pastikan bot memiliki izin mengirim pesan di channel Discord  

---

## 📜 Lisensi  
Bot ini open-source dan dapat digunakan serta dimodifikasi sesuai kebutuhan.  
