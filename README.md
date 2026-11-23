# Kasir Minimarket

Backend: Node.js + Express + Prisma (SQLite). Frontend: React + Vite.

## Cara jalanin (buka 2 terminal di VS Code)

Prasyarat: Node.js LTS.

**Terminal 1 — backend**
```bash
cd backend
npm install
npx prisma migrate dev --name init   # bikin database + tabel
npm run db:seed                      # isi data contoh + akun login
npm run dev                          # API di http://localhost:4000
```

**Terminal 2 — frontend**
```bash
cd frontend
npm install
npm run dev                          # buka http://localhost:5173
```

## Akun demo
- admin / admin123 (bisa kelola produk & lihat laporan)
- kasir1 / kasir123 (hanya halaman kasir)

## Struktur
```
backend/
  prisma/schema.prisma   # struktur tabel
  prisma/seed.js         # data awal
  src/routes/            # auth, products, transactions, reports
frontend/
  src/pages/             # Login, Kasir, Produk, Laporan
```

## Catatan
- Ganti `JWT_SECRET` di `backend/.env` sebelum dipakai beneran.
- Lihat isi database: `cd backend && npm run db:studio`.
- Pindah ke MySQL/PostgreSQL: ubah `provider` dan `DATABASE_URL`, lalu migrate ulang.
