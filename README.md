# [NAMA CAFE] — Static Cafe Shop

Website cafe full frontend menggunakan HTML5, CSS3, dan Vanilla JavaScript ES6+. Tidak memakai React, Next.js, Vue, Angular, TypeScript, Node.js, PHP, Python, database lokal, Docker, atau library frontend besar.

## Fitur
- Homepage, menu, search, filter, sorting
- Detail produk: ukuran, gula, es, topping, catatan, quantity
- Cart berbasis localStorage
- Voucher dengan minimum purchase, periode, dan maximum discount
- Checkout: dine-in, take-away, delivery
- Payment UI: QRIS, Cash, Bank Transfer, E-Wallet
- Order number `CAF-YYYYMMDD-XXXX`
- Order tracking dan status
- Receipt-ready data dan print styling dapat dikembangkan dari order detail
- WhatsApp order dengan pesan URL encoded
- Admin demo: orders, products, categories, toppings, promos, inventory, transactions, reports, settings
- Dark mode / light / system preference
- Responsive 360px sampai desktop
- SEO metadata, robots.txt, sitemap.xml, manifest

## Menjalankan dari HP
1. Upload folder project ke GitHub melalui browser.
2. Pastikan `index.html` berada di root repository.
3. Di Vercel, pilih repository GitHub tersebut lalu deploy sebagai static project. Tidak perlu build command dan tidak perlu server.
4. Semua data demo disimpan di localStorage browser.

## Mengubah branding
Edit `js/config.js`. Ubah `CAFE_NAME`, tagline, alamat, WhatsApp, warna, pajak, service fee, delivery fee, dan Google Maps URL.

## Mengubah produk
Edit array `INITIAL_PRODUCTS` di `js/data.js`. Setelah browser pernah menjalankan project, data awal tersimpan di localStorage. Untuk mendapatkan data awal baru, hapus key `products` dari Application Storage browser lalu reload.

## Mengubah QRIS
Ganti `assets/images/qris-placeholder.svg` dengan gambar QRIS milik cafe dan sesuaikan `QRIS_IMAGE` di `js/config.js`. Jangan memasukkan secret payment gateway ke frontend.

## Admin demo
Username: `admin`  
Password: `admin123`

Ini hanya simulasi frontend. `sessionStorage` dan localStorage bukan authentication production dan dapat dimanipulasi pengguna. Jangan gunakan credential demo untuk sistem nyata.

## Pembayaran
Status pembayaran default adalah `WAITING FOR PAYMENT`. Tombol pembayaran tidak mengklaim pembayaran berhasil. Untuk pembayaran sungguhan, gunakan payment provider/backend yang memiliki server-side verification dan webhook.

## Keterbatasan static frontend
Karena project ini sengaja tanpa backend/database, data hanya berada di browser masing-masing pengguna. Order tidak otomatis masuk ke komputer kasir dan stok tidak tersinkron antar perangkat. Authentication, payment verification, customer account, multi-device sync, dan database production memerlukan backend/provider.

## GitHub dari HP
- Buat repository baru di GitHub.
- Pilih Add file / Upload files.
- Upload isi folder project.
- Commit changes.
- Pastikan file `index.html`, `css/`, `js/`, dan `assets/` ada di root.

## Vercel dari HP
- Login ke Vercel melalui browser.
- Add New Project.
- Import repository GitHub.
- Deploy.
- Karena static, jangan menambahkan Node/PHP/Python backend.

## Production upgrade
Untuk production, pertahankan UI tetapi pindahkan products, orders, users, inventory, promo, settings, dan payment verification ke backend/database. Authentication harus server-side, payment diverifikasi melalui webhook/provider, dan authorization harus dilakukan server-side.
