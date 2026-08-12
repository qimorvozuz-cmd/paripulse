# 💎 PariPulse Affiliate Support / CRM Bot

Uch tilli (UZ/RU/EN) Telegram affiliate bot. Aiogram 3, SQLite va Telegram inline tugmalari asosida Railway uchun tayyorlangan.

## Imkoniyatlar

- 🌍 UZ/RU/EN kutib olish va menyu
- 💎 RevShare (35% gacha), FIX, Hybrid va PostPay tavsifi; CPA yo‘q
- 📝 Qat’iy validatsiyali RevShare arizasi: Email, User, Kanal, RS, GEO, Promo
- 🆔 Avtomatik `AFF-000001` formatidagi partner ID
- 💬 Ikki tomonlama ticket/chat; ochiq suhbat vaqtida boshqa menyular bloklanadi
- 🛡 Arizani tasdiqlash/rad etish, ban/unban, qidiruv, hamkorlar, statistika
- 📣 Broadcast va AFF ID bo‘yicha individual xabar
- 👑 Owner tomonidan admin qo‘shish
- ✨ Telegram cheklovlariga mos premium emoji UX va ixtiyoriy animation `file_id`

## Mahalliy ishga tushirish

1. Python 3.11+ o‘rnating.
2. Virtual environment yarating va `pip install -r requirements.txt` bajaring.
3. `.env.example` nusxasini `.env` nomida saqlang.
4. `BOT_TOKEN`, `REGISTRATION_URL` va kerak bo‘lsa animation `file_id` ni kiriting.
5. `python main.py` ni ishga tushiring.

BotFather orqali olingan tokenni hech qachon Git’ga joylamang.

## Railway deploy

1. Loyihani GitHub repository’ga yuklang va Railway’da **New Project → Deploy from GitHub** tanlang.
2. Variables bo‘limida kamida `BOT_TOKEN` va `REGISTRATION_URL` yarating. `OWNER_ID=8158007502`.
3. Start command: `python main.py` (yoki Procfile avtomatik ishlaydi).
4. SQLite fayli deploy qayta yaratilganda yo‘qolmasligi uchun Railway Volume ulang va `DATABASE_PATH=/data/paripulse.db` belgilang.

## Telegram animatsiyasi

Bot API uchinchi tomon botlariga foydalanuvchidek premium animated emoji yuborishni to‘liq bermaydi. Loyiha oddiy emoji va inline tugmalardan foydalanadi. Botga GIF/MP4 animation yuborib, update’dan olingan `file_id` ni `WELCOME_ANIMATION_FILE_ID` ga qo‘ysangiz welcome animatsiya ishlaydi. Noto‘g‘ri yoki bo‘sh `file_id` bo‘lsa matnli fallback ishlaydi.

## Admin ishlatish

- Owner: `8158007502`
- `/admin` — CRM panel
- Owner panel orqali Telegram numeric ID bilan admin qo‘shadi.
- Broadcast yuborishda Telegram limiti uchun xabarlar orasida kichik pauza qo‘yilgan.

## Production eslatmalari

SQLite kichik/o‘rta bot uchun mos. Yuqori trafik yoki bir nechta worker uchun PostgreSQL’ga o‘tish tavsiya qilinadi. Bot polling rejimida ishlaydi; Railway worker uchun webhook shart emas.
