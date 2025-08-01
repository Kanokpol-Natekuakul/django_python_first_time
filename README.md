# Django Blog

เว็บไซต์บล็อกง่ายๆ ที่สร้างด้วย Django Framework สำหรับการเขียนและแสดงบทความ

## 📋 คุณสมบัติ

- แสดงรายการบทความในหน้าแรก
- ระบบจัดการบทความผ่าน Django Admin
- หน้าเกี่ยวกับเรา (About)
- ออกแบบ UI แบบเรียบง่าย
- รองรับการแสดงวันที่โพสต์

## 🛠️ เทคโนโลยีที่ใช้

- **Python** 3.x
- **Django** 5.2.4
- **SQLite** (ฐานข้อมูลเริ่มต้น)
- **HTML/CSS** สำหรับ Frontend

## 📁 โครงสร้างโปรเจค

```
mywebsite/
├── blog/                    # Django App หลัก
│   ├── migrations/          # ไฟล์ Migration ฐานข้อมูล
│   ├── templates/blog/      # Template HTML
│   │   ├── home.html       # หน้าแรก
│   │   └── about.html      # หน้าเกี่ยวกับ
│   ├── models.py           # Model ฐานข้อมูล
│   ├── views.py            # Views ควบคุมการแสดงผล
│   ├── urls.py             # URL Routing
│   └── admin.py            # การตั้งค่า Admin
├── mywebsite/              # การตั้งค่าหลักของโปรเจค
│   ├── settings.py         # การตั้งค่า Django
│   ├── urls.py             # URL หลัก
│   └── wsgi.py             # WSGI Configuration
└── manage.py               # คำสั่งจัดการ Django
```

## 🚀 วิธีการติดตั้งและใช้งาน

### 1. เตรียมสภาพแวดล้อม

```bash
# สร้าง Virtual Environment
python -m venv venv

# เปิดใช้งาน Virtual Environment
# สำหรับ Windows
venv\Scripts\activate
# สำหรับ macOS/Linux
source venv/bin/activate

# ติดตั้ง Django
pip install django==5.2.4
```

### 2. ตั้งค่าฐานข้อมูล

```bash
# สร้างและปรับปรุงฐานข้อมูล
python manage.py makemigrations
python manage.py migrate

# สร้างผู้ใช้ Admin (ทำครั้งแรกเท่านั้น)
python manage.py createsuperuser
```

### 3. เรียกใช้เซิร์ฟเวอร์

```bash
python manage.py runserver
```

เปิดเบราว์เซอร์และไปที่: `http://127.0.0.1:8000`

## 📝 การใช้งาน

### เพิ่มบทความใหม่
1. เข้าสู่ระบบ Admin: `http://127.0.0.1:8000/admin`
2. ใช้ Username และ Password ที่สร้างไว้
3. คลิกที่ "Posts" และเลือก "Add Post"
4. กรอกข้อมูล:
   - **Title**: หัวข้อบทความ
   - **Content**: เนื้อหาบทความ
   - **Date posted**: วันที่โพสต์ (จะตั้งค่าอัตโนมัติ)

### หน้าเว็บไซต์
- **หน้าแรก** (`/`): แสดงรายการบทความทั้งหมด
- **เกี่ยวกับ** (`/about/`): ข้อมูลเกี่ยวกับเว็บไซต์

## 🗃️ โมเดลฐานข้อมูล

### Post Model
```python
class Post(models.Model):
    title = models.CharField(max_length=100)      # หัวข้อบทความ
    content = models.TextField()                  # เนื้อหาบทความ
    date_posted = models.DateTimeField()          # วันที่โพสต์
```

## 🎨 การปรับแต่ง

### แก้ไข Template
- **หน้าแรก**: `blog/templates/blog/home.html`
- **หน้าเกี่ยวกับ**: `blog/templates/blog/about.html`

### เพิ่มฟีเจอร์ใหม่
1. แก้ไข `models.py` เพื่อเพิ่มฟิลด์ใหม่
2. สร้าง Migration: `python manage.py makemigrations`
3. อัปเดตฐานข้อมูล: `python manage.py migrate`
4. ปรับแต่ง Views และ Templates ตามต้องการ

## 🔧 คำสั่งที่มีประโยชน์

```bash
# ดูรายการ URL ทั้งหมด
python manage.py show_urls

# สร้างข้อมูลตัวอย่าง
python manage.py shell

# ตรวจสอบความถูกต้องของโปรเจค
python manage.py check

# สำรองฐานข้อมูล
python manage.py dumpdata > backup.json

# กู้ข้อมูลจากไฟล์สำรอง
python manage.py loaddata backup.json
```

## 📚 การพัฒนาต่อ

สิ่งที่สามารถเพิ่มเติมได้:
- ระบบผู้ใช้และการล็อกอิน
- ระบบค้นหาบทความ
- การแบ่งหน้า (Pagination)
- ระบบหมวดหมู่บทความ
- ระบบความคิดเห็น
- การอัปโหลดรูปภาพ
- ระบบแท็ก
- การแชร์โซเชียลมีเดีย

## 🤝 การสนับสนุน

หากพบปัญหาหรือต้องการความช่วยเหลือ:
1. ตรวจสอบ Django Documentation
2. ดูข้อผิดพลาดใน Terminal
3. ตรวจสอบไฟล์ `settings.py` ว่าครบถ้วน

## 📄 ใบอนุญาต

โปรเจคนี้เป็นโอเพนซอร์สและสามารถนำไปใช้ได้อย่างอิสระ

---

**หมายเหตุ**: นี่เป็นโปรเจคตัวอย่างสำหรับการเรียนรู้ Django ไม่แนะนำให้ใช้ในการผลิตจริงโดยไม่มีการปรับปรุงด้านความปลอดภัย
