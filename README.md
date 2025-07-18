# fathirv2
Berikut deskripsi lengkap tentang **cara menjalankan script (sc) bot Telegram menggunakan Termux di Android**:

---

### 📱 Cara Menjalankan Script Bot Telegram di Termux Android

Ingin menjalankan bot Telegram langsung dari HP Android tanpa laptop atau VPS? Kamu bisa menggunakan **Termux**, sebuah aplikasi terminal emulator yang memungkinkan kita menjalankan script seperti di Linux!

#### 🔧 Persiapan Awal

1. **Install Termux:**

   * Unduh Termux dari F-Droid ([https://f-droid.org/packages/com.termux/](https://f-droid.org/packages/com.termux/)), **bukan dari Play Store** agar versi terbaru.
2. **Install Termux\:API** *(Opsional, untuk akses perangkat Android)*

#### 📦 Install Paket yang Dibutuhkan

Buka Termux lalu ketik perintah berikut:

```bash
pkg update && pkg upgrade -y
pkg install nodejs -y
pkg install git -y
pkg install ffmpeg imagemagick -y
```

> Tambahan jika menggunakan modul `canvas`:

```bash
pkg install libjpeg-turbo libpng libwebp -y
```

#### ⬇️ Clone Script Bot

Clone atau download script bot kamu (contoh pakai GitHub):

```bash
git clone https://github.com/NamaUser/NamaRepo
cd NamaRepo
```

Kalau kamu punya file zip, kamu bisa unzip dan `cd` ke dalam folder-nya.

#### 📦 Install Dependency Bot

Jalankan:

```bash
npm install
```

Jika menggunakan `yarn`:

```bash
yarn install
```

#### 🔑 Setting Token Bot

Edit file konfigurasi atau `.env` sesuai kebutuhan bot kamu. Biasanya token bot ditaruh di `.env` atau file `config.js`:

```bash
nano config.js
```

Paste token bot kamu dari BotFather.

#### ▶️ Jalankan Bot

Setelah semua siap, jalankan bot:

```bash
node index.js
```

Atau jika bot kamu menggunakan file utama lain:

```bash
node bot.js
```

Jika ingin tetap aktif meskipun keluar dari Termux, gunakan:

```bash
npm install pm2 -g
pm2 start index.js
```

#### ✅ Bot Berhasil Jalan!

Jika muncul log seperti "Bot ready" atau tidak error, berarti bot Telegram kamu berhasil berjalan di Android menggunakan Termux.

---

### ⚠️ Tips & Catatan

* Gunakan **Termux versi terbaru dari F-Droid**.
* Pastikan koneksi internet stabil.
* Jangan tutup Termux saat bot aktif, kecuali kamu pakai PM2.

