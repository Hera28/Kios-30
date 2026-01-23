# Kios-30

Project ini adalah website kecil untuk toko serbaguna orang tua, di mana penjual dapat mengupdate stok barang dan pembeli dapat melihat daftar barang.

## Setup Firebase

1. Buat project di [Firebase Console](https://console.firebase.google.com/).
2. Enable Firestore Database.
3. Set rules Firestore ke allow read/write untuk semua (untuk testing, tapi hati-hati untuk production):
   ```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /{document=**} {
         allow read, write: if true;
       }
     }
   }
   ```
4. Di Project settings > General > Your apps, tambah web app, copy config.
5. Ganti config di `index.html` dengan config Firebase kamu.

## Deploy ke GitHub Pages

1. Push code ke GitHub repo `Hera28/Kios-30`.
2. Di repo settings > Pages, set source ke `Deploy from a branch`, branch `main`, folder `/ (root)`.
3. Site akan live di `https://hera28.github.io/Kios-30/`.

## Cara Pakai

- Pembeli: Klik "Saya Pembeli" untuk lihat daftar barang.
- Penjual: Klik "Saya Penjual", masukkan password `11229911`, lalu update barang.

Data disimpan di Firestore, jadi shared antara semua user.
