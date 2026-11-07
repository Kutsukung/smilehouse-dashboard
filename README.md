# Smilehouse Dashboard: ไอคอนบนหน้าจอโฮม (iPhone / Android)

หน้านี้ (GitHub Pages) ทำหน้าที่เป็น "ตัวเปิดแอป" อย่างเดียว: ไอคอน ชื่อแอป และกรอบเต็มจอที่เปิดแดชบอร์ด Apps Script
ตัวแดชบอร์ดยังอยู่ที่ Google Apps Script เหมือนเดิม

- **อัปเดตแดชบอร์ด (Apps Script)**: Deploy > Manage deployments > ดินสอ > Version: **New version** (URL เดิม) → **ไม่ต้องแก้ repo นี้**
- **ห้ามกด New deployment** (จะได้ URL ใหม่ ต้องแก้ `DASH_URL` ใน `index.html`)
- URL แดชบอร์ดอยู่ที่ `DASH_URL` ใน `index.html` (repo เป็น public ใครเปิดก็เห็นหน้าเข้าสู่ระบบได้ ข้อมูลยังต้องใช้ชื่อ + PIN · เพิ่มชื่อในแท็บ users เฉพาะเมื่อคนนั้นพร้อมตั้ง PIN ทันที)

## ครั้งเดียว: Apps Script ต้องอนุญาตให้ฝังหน้า
`doGet()` ใน Code.gs (FD Multiverse รุ่น 1.1 ขึ้นไป) มี `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)` แล้ว
วาง Code.gs ใหม่ → บันทึก → Deploy > Manage deployments > New version

## ลิงก์ที่ส่งให้พนักงาน
```
https://kutsukung.github.io/smilehouse-dashboard/
```
(ใส่ `#u=<URL /exec หรือรหัส deployment>` ต่อท้ายได้ ถ้าต้องการเปิดแดชบอร์ดชุดอื่นชั่วคราว)

## เพิ่มไอคอนในมือถือ
- **iPhone**: เปิดลิงก์ใน Safari > ปุ่มแชร์ > เพิ่มไปยังหน้าจอโฮม > เพิ่ม
- **Android**: เปิดลิงก์ใน Chrome > ⋮ > ติดตั้งแอป (หรือ เพิ่มลงในหน้าจอหลัก) หรือกดปุ่ม "ติดตั้งแอป Smilehouse" ในหน้า
- เปิดจากไอคอน = แดชบอร์ดเต็มจอ (เข้าด้วยชื่อ + PIN เหมือนเดิม) · เปิดลิงก์ในเบราว์เซอร์ = หน้าวิธีเพิ่มไอคอน

## ไฟล์
- `index.html` หน้าเปิดแอป (`DASH_URL` = URL แดชบอร์ด · iPhone ใช้ apple-touch-icon · Android ใช้ manifest)
- `manifest.webmanifest` ชื่อแอป ไอคอน สีพื้น (Android)
- `icons/` apple-touch-icon 180 px, icon 192/512, maskable 192/512 (ภาพย่อวางกลางสำหรับไอคอนวงกลม/สี่เหลี่ยมมนของ Android), favicon 32
- เปลี่ยนไอคอน: แทนไฟล์ใน `icons/` ชื่อเดิม ขนาดเดิม (iPhone ที่เพิ่มไอคอนไว้แล้วต้องลบแล้วเพิ่มใหม่จึงจะเห็นไอคอนใหม่)
