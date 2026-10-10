# LINGKOR (Linguistik Korpus Nusantara)

Prototype website: penerjemah bahasa daerah ke slang, kamus, dan quiz.
HTML, CSS, dan JavaScript biasa. Tanpa build, tanpa API key.

## Cara menjalankan
1. Ekstrak folder ini.
2. Klik dua kali `index.html` (atau jalankan `python3 -m http.server` lalu buka http://localhost:8000).
Font dimuat dari Google Fonts; tanpa internet, tampilan memakai font sistem.

## Struktur
- `data/kamus.js`  entri kamus (semua contoh prototype, belum diverifikasi ahli bahasa)
- `data/soal.js`   soal quiz, kunci jawaban (`benar`), dan level
- `js/core.js`     router, ikon, favorit (localStorage), toast, tema
- `js/translator-service.js`  provider penerjemah (kamus lokal)
- `js/pages/*.js`  halaman: beranda, penerjemah, kamus, quiz, tentang
- `css/styles.css` gaya, tema terang/gelap

## Menambah kata
Salin satu objek di `data/kamus.js`, ubah isinya, pastikan `id` unik.

## Menghubungkan API di kemudian hari
Di `js/translator-service.js`, daftarkan provider baru dengan `LK.translator.register('api', { nama, translate })`,
lalu set `LK.translator.provider = 'api'`. Halaman penerjemah tidak perlu diubah selama bentuk hasilnya sama.
