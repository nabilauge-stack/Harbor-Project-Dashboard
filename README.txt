# Harbor Project Control Dashboard — Private Web Version

## Fitur
- Planned dan Actual dapat diedit.
- Deviation otomatis = Actual - Planned.
- Status otomatis berdasarkan threshold.
- Data tersimpan di Supabase, bukan localStorage.
- User login memakai email magic link.
- User baru berstatus pending.
- Owner dapat approve/reject request.
- Role: owner, editor, viewer, pending, rejected.
- Perubahan data tersinkron untuk user yang memiliki akses.

## Setup
1. Buat project di Supabase.
2. Buka SQL Editor dan jalankan `supabase-schema.sql`.
3. Login pertama kali memakai email Anda.
4. Di SQL Editor jalankan:
   `update public.profiles set role='owner' where email='EMAIL_ANDA';`
5. Buka `index.html`, isi:
   - `SUPABASE_URL`
   - `SUPABASE_ANON_KEY`
6. Upload `index.html` ke hosting static seperti Vercel/Netlify/GitHub Pages.
7. Set Authentication > URL Configuration di Supabase agar `Site URL` dan redirect URL mengarah ke URL dashboard.
8. Bagikan URL dashboard. User lain login dengan email lalu request access.

## Catatan
Versi ini mempertahankan konsep dashboard asli sebagai basis, tetapi penyimpanan lokal diganti menjadi database bersama.
Untuk produksi internal, aktifkan email confirmation/SMTP sesuai kebijakan organisasi.
