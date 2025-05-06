# Osrequest Bot

Bot ini memungkinkan pengguna mengetik `!req beatmap_id` di YouTube Live Chat untuk mengambil detail beatmap dari osu! API dan mengirimkannya sebagai embed ke Discord Webhook.

---

## 📌 Fitur  
- ✅ Membaca pesan `!req beatmap_id` di YouTube Live Chat  
- ✅ Mengambil detail beatmap dari osu! API  
- ✅ Mengirim embed ke Discord Webhook  

---

## 🛑 Persyaratan  
1. **Node.js** 16 atau versi lebih baru  
2. **BTMC**  

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

### 3. Konfigurasi File `.env`  
1. Ubah nama file `.env.example` menjadi `.env`.  
2. Lengkapi konfigurasi berikut:  
   ```env
   YT_API_KEY=your_youtube_api_key      # API Key untuk YouTube Data API v3
   OSU_API_KEY=your_osu_api_key         # API Key osu!
   DISCORD_WEBHOOK=your_webhook_url     # URL Webhook Discord
   YT_LIVE_CHAT_ID=your_live_chat_id    # ID Live Chat YouTube
   ```

   **Cara Mendapatkan `YT_LIVE_CHAT_ID`:**  
   Gunakan YouTube Data API:  
   ```sh
   https://www.googleapis.com/youtube/v3/videos?part=liveStreamingDetails&id=VIDEO_ID&key=YT_API_KEY
   ```
   Ambil nilai `liveStreamingDetails.activeLiveChatId`.

---

## 🔑 Mendapatkan YouTube API Key  
1. **Buka Google Cloud Console:**  
   - Masuk ke **[Google Cloud Console](https://console.cloud.google.com/)** dan login.  
2. **Buat Proyek:**  
   - Klik **"Select a project"**, lalu pilih atau buat proyek baru.  
3. **Aktifkan YouTube Data API v3:**  
   - Pergi ke **"APIs & Services" > "Library"**, cari **"YouTube Data API v3"**, lalu aktifkan.  
4. **Buat API Key:**  
   - Pergi ke **"APIs & Services" > "Credentials"**, klik **"Create Credentials"** > **"API Key"**, lalu salin API Key yang dihasilkan.  
5. Tambahkan API Key ke file `.env`:  
   ```env
   YT_API_KEY=AIzaSyDk_example123456789-abcdefg
   ```

---

## 📜 Menjalankan Bot  
Jalankan bot dengan perintah:  
```sh
npm start
```

Bot akan membaca chat YouTube dan menangkap request format:  
```
!req 5018968
```
Jika beatmap ditemukan, bot akan mengirim embed ke Discord Webhook dengan detail beatmap.

---

## 🛠 Troubleshooting  

**Masalah**: Bot tidak membaca chat YouTube.  
**Solusi**:  
- Pastikan `YT_LIVE_CHAT_ID` sudah benar.  
- Periksa apakah `YT_API_KEY` memiliki akses ke YouTube Data API v3.  
- Cek limit kuota API di Google Cloud Console.  

**Masalah**: Bot tidak mengirim pesan ke Discord Webhook.  
**Solusi**:  
- Periksa apakah URL webhook di `.env` sudah benar.  
- Pastikan bot memiliki izin mengirim pesan di channel Discord.  

---

## 📜 Lisensi  
Proyek ini bersifat open-source dan dapat dimodifikasi sesuai kebutuhan.  
