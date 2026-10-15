# Pantau situs seleksi

Pemeriksaan otomatis untuk https://seleksibinaantarbudaya.or.id setiap 15 menit lewat GitHub Actions:

- halaman depan harus terbuka (HTTP 200);
- https://seleksibinaantarbudaya.or.id/api/v1/readyz harus menjawab `"status":"ok"` (database, penyimpanan berkas, antrean).

Bila salah satu gagal tiga kali berturut-turut, run ditandai gagal dan GitHub mengirim email ke pemilik repo.
Repo ini hanya membaca alamat publik, persis seperti pengunjung biasa: tidak ada kredensial dan tidak ada akses ke server.

- **Riwayat pemeriksaan:** tab Actions. Centang hijau berarti sehat, silang merah berarti bermasalah.
- **Menguji email peringatan:** Actions → "Pantau situs seleksi" → Run workflow → centang `uji_email` → Run workflow.
- **Menghentikan pemantauan:** Actions → "Pantau situs seleksi" → tombol `···` → Disable workflow.
