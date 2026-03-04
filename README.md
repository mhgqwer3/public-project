# 🗑️ Smart Bins System — Docker Setup

## هيكل المشروع

```
GraduationProject/
├── backend/                        # PHP API
│   ├── API.php                     # الـ endpoints الرئيسية
│   ├── auth.php                    # Login / Logout
│   ├── Helpers.php                 # DB connection + helpers
│   └── Database/
│       └── smart_bins_system.sql  # Schema + بيانات أولية
├── frontend/                       # HTML/CSS/JS
│   ├── pages/                      # صفحات الموقع
│   ├── CSS/
│   └── JAVASCRIPT/
├── Dockerfile.backend              # PHP + Apache
├── Dockerfile.frontend             # Nginx
├── docker-compose.yml              # كل الـ services مع بعض
├── nginx.conf                      # إعدادات Nginx
├── .env                            # الـ secrets (متبعتش على GitHub!)
└── .env.example                    # template للـ .env
```

---

## تشغيل المشروع

```bash
# 1. انسخ الـ .env
cp .env.example .env

# 2. عدل الـ passwords في .env
# DB_PASSWORD=your_password
# DB_ROOT_PASSWORD=your_root_password

# 3. شغل كل حاجة
docker compose up -d

# 4. استنى 20-30 ثانية MySQL تشتغل
```

## الروابط

| الخدمة     | الرابط                                              |
|-----------|-----------------------------------------------------|
| Frontend  | http://localhost:3000/pages/login.html              |
| Backend   | http://localhost:8080                               |
| phpMyAdmin| http://localhost:8081                               |

---

## أهم الأوامر

```bash
# شغل
docker compose up -d

# شوف الـ logs
docker compose logs -f

# وقف
docker compose down

# وقف + امسح الداتا
docker compose down -v

# ابني من أول لو غيرت في الكود
docker compose up -d --build
```

---

## الـ Services

| Service      | Port | الوظيفة                    |
|-------------|------|---------------------------|
| frontend    | 3000 | Nginx بيخدم HTML/CSS/JS   |
| backend     | 8080 | PHP + Apache API          |
| mysql       | 3306 | Database                  |
| phpmyadmin  | 8081 | إدارة الـ Database         |
