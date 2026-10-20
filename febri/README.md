# Dashboard BI - UTS Business Intelligence (P8)

Flask + pandas + scikit-learn: EDA, Preprocessing, Apriori, K-Means, Dashboard BI.

## Jalankan lokal
    pip install -r requirements.txt
    python uts_bi.py        # http://127.0.0.1:5000

## Struktur repo
    uts_bi.py  requirements.txt  render.yaml  Procfile  .gitignore  README.md
    foto.jpg   (opsional, foto cover; taruh di folder yang sama dan ikut di-commit)

## Deploy ke Render (kode disimpan di GitHub)
1. Push semua file ke repo GitHub.
2. Render -> New + -> Blueprint (atau Web Service) -> pilih repo.
   - Blueprint: otomatis membaca `render.yaml`.
   - Manual: Build `pip install -r requirements.txt`,
     Start `gunicorn uts_bi:app --workers 1 --threads 4 --timeout 300 --bind 0.0.0.0:$PORT`.
3. Buka URL `https://<nama>.onrender.com`, login, unggah `P8__UTS_Business_Intelligence.xlsx`.

Catatan:
- GitHub Pages tidak bisa menjalankan Flask; GitHub hanya tempat kode, yang menjalankan aplikasi adalah Render.
- Jangan ubah ke lebih dari 1 worker (state analisis ada di memori proses).
- Plan free tertidur saat tidak dipakai. Setelah bangun, analisis dipulihkan otomatis dari
  unggahan terakhir selama disk belum dibersihkan; bila hilang, cukup unggah ulang file Excel.
- Username/password bisa diganti lewat env `APP_USER` dan `APP_PASSWORD` di Render.
