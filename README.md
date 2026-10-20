# Portofolio Kumala Desy

Situs portofolio statis (tanpa build). Seluruh isi ada di **`content.json`**, jadi cukup edit file itu langsung di GitHub.

## Pasang di GitHub Pages
1. Buat repositori baru di GitHub (mis. `portofolio`), lalu upload **semua isi folder ini** (termasuk folder `assets/` dan file `.nojekyll`).
2. Buka **Settings → Pages**. Pada *Build and deployment* pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
3. Tunggu 1–2 menit. Alamat situs: `https://USERNAME.github.io/NAMA-REPO/`.

> Jangan buka `index.html` dengan klik ganda dari komputer: browser akan menolak memuat `content.json`. Gunakan GitHub Pages, atau jalankan `python3 -m http.server` di folder ini lalu buka `http://localhost:8000`.

## Cara mengedit lewat GitHub
Buka `content.json` di GitHub → ikon pensil (✏️) → ubah → **Commit changes**. Situs ikut berubah setelah GitHub Pages selesai deploy (biasanya 1–2 menit; tekan *Ctrl+Shift+R* jika belum berubah).

Pastikan JSON tetap valid (tanda kutip `"` dan koma `,` jangan terhapus). Jika salah, muncul pesan merah di bawah halaman. Cek di <https://jsonlint.com> bila perlu.

### Bagian penting di `content.json`
| Kunci | Isinya |
|---|---|
| `photo` | Foto profil (alamat file di `assets/`) |
| `ed` | Teks yang bisa diubah per bahasa: `id`, `en`, `fr`, `zh` (mis. `bio`, `a0` = paragraf Tentang) |
| `about` | Tab Tentang: `edu` (pendidikan, tiap item punya `y` tahun, `t` nama, `m` jurusan, `w` link web), `btns` (tombol, termasuk **Download CV**) |
| `cv.exp` | Pengalaman kerja/magang: `t` jabatan, `o` lembaga, `p` periode, `u` link, `b` daftar poin |
| `cv.org` | Organisasi & kepanitiaan (isi sama seperti `cv.exp`) |
| `cv.ach` | Prestasi: `t` judul, `o` penyelenggara, `y` tahun, `u` link |
| `cv.skl` | Skill: `t` judul kelompok, `c` daftar skill |
| `contact` | Tab Kontak: `rows` (daftar kontak) dan `via` (pilihan kirim pesan) |
| `socials` | Ikon sosmed di halaman depan (`ig`, `tt`, `in`, …) |
| `navHide` | Tab yang disembunyikan dari menu (mis. `"org"`, `"ach"`) |
| `order` | Urutan tab |
| `ft` | Fitur tambahan (Wishbox, Now Page, Statistik, Peta, Polaroid, Personality, Favorites, Rekomendasi) |

Contoh menambah pengalaman: salin satu blok `{ ... }` di `cv.exp`, tempel di bawahnya (pisahkan dengan koma), lalu ubah isinya.

### Mengganti foto atau CV
- Upload file baru ke folder `assets/` (**Add file → Upload files**), lalu ubah alamatnya di `content.json`, mis. `"photo": "assets/foto-baru.jpg"`.
- CV: timpa `assets/CV_KUMALA_DESY.pdf` dengan file baru bernama sama. Tombol *Download CV* langsung memakai file itu.

## Perbedaan dengan versi di Claude
- Mode edit visual (geser, hapus, sembunyikan elemen) hanya ada di versi Claude. Di GitHub, ubah lewat `content.json`.
- Wishbox hanya tersimpan di browser pengunjung (tidak real-time antar pengunjung).
- Isi `content.json` bersifat publik, termasuk email dan username di dalamnya.
