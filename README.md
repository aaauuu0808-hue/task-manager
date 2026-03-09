# MERN Full-Stack Task Manager

Bu proje MongoDB + Express + React + Node.js ile olusturulmus full-stack gorev yoneticisidir.

## Ozellikler

- Tam CRUD: gorev olusturma, listeleme, guncelleme, silme
- Kanban gorunumu: `todo`, `in-progress`, `done`
- Gelismis filtreleme: durum, oncelik, kategori, arama
- Due date ve gecikme gorunumu
- Alt gorev (subtask) checklist
- Dashboard istatistikleri (toplam, tamamlanan, geciken, bugun biten)
- Optimistic UI guncelleme

## Klasor Yapisi

- `server/`: Express API + Mongoose
- `client/`: React + Vite arayuzu

## Kurulum

1. MongoDB'nin lokal olarak calistigindan emin ol (`mongodb://127.0.0.1:27017`).
2. Backend ortam degiskenlerini olustur:
   - `server/.env.example` dosyasini `server/.env` olarak kopyala.
3. Bagimliliklar zaten yuklendi degilse:
   - Root: `npm install`
   - Server: `cd server && npm install`
   - Client: `cd client && npm install`

## Calistirma

Root klasorde:

```bash
npm run dev
```

Bu komut su servisleri birlikte baslatir:

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:3000`

## Seed (Ornek Veri)

```bash
npm run seed
```

## API Endpointleri

- `GET /api/tasks`
- `GET /api/tasks/:id`
- `POST /api/tasks`
- `PUT /api/tasks/:id`
- `DELETE /api/tasks/:id`

Desteklenen query parametreleri (`GET /api/tasks`):

- `status` (ornek: `todo,in-progress`)
- `priority` (ornek: `high,urgent`)
- `category`
- `search`
- `sort` (ornek: `-createdAt,dueDate`)
- `limit`

## Notlar

- Frontend API istekleri Vite proxy ile `/api` uzerinden backend'e yonlendirilir.
- Backend CORS ayari varsayilan olarak `http://localhost:5173` origin'ini kabul eder.