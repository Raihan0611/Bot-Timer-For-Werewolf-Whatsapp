BOT TIMER For Werewolf
==========

Ringkasan
--------
Script `bot timer` berisi adaptor ringan yang menangani pesan timer untuk sistem Werewolf. dan akan berkomunikasi dengan bot Werewolf untuk mengelola pesan timer di grup. seperti ini komunikasinya:
- Menerima pertanyaan natural: "Apakah kamu ada di grup `(groupId)` dan menjawab "Iya"/"Tidak".
- Menyimpan message key per grup untuk standby/info message agar bisa diedit/hapus.
- Menangani perintah natural dari executor (mis. `Update timer di grup ...`, `Hapus timer di grup ...`) untuk mengedit atau menghapus pesan timer.

Konfigurasi
-----------
- Pastikan pastikan isi nomor bot timer di `config.js` bot Werewolf jika Anda ingin integrasi dengan bot eksternal timer. Contoh:

```js
const pakaiBotTimer = false; // Ganti dengan true jika ingin menggunakan timer, false jika tidak ingin menggunakan timer
const LidbotTimer = "-"; // Ganti dengan nomor @Lid Bot Timer Anda jika tidak ada isi dengan strip '-'
```

- Jika Anda ingin menonaktifkan integrasi eksternal dan pakai timer lokal, isi `botTimer` dengan karakter `-` (mis. `"-"`).

Cara Pakai
---------
- Jalankan bot seperti biasa npm install, lalu start.
- Pastikan bot timer dan bot Werewolf ada di grup yang sama.
- Bot Werewolf akan berkomunikasi dengan bot timer melalui private chat sesuai konfigurasi.
  - "Apakah kamu ada di grup 12345@g.us" — bot menjawab `Iya` atau `Tidak`. Jika `Iya`, bot timer akan membuat (jika belum ada) pesan standby di grup tersebut dan menyimpan message key.
  - "Update timer di grup 12345@g.us" — bot mengedit pesan standby di grup  dan mulai hitungan mundur.
  - "Hapus timer di grup 12345@g.us" — bot menghapus pesan timer (menggunakan message key) untuk semua orang.

Pengujian
--------
- Tes mode lokal: set `botTimer` menjadi `-` dan jalankan flow `.ww timer` di plugin Werewolf.
- Tes mode eksternal: set `botTimer` ke nomor, pastikan bot eksternal merespon "Iya"/"Tidak" dalam 5s.

Selamat Mencoba!
---