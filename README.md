# Smilehouse Dashboard: ไอคอนบนหน้าจอโฮม (iPhone / Android)

หน้านี้ (GitHub Pages) ทำหน้าที่เป็น "ตัวเปิดแอป" อย่างเดียว: ไอคอน ชื่อแอป และกรอบเต็มจอที่เปิดแดชบอร์ด Apps Script
ตัวแดชบอร์ดยังอยู่ที่ Google Apps Script เหมือนเดิม

- **อัปเดตแดชบอร์ด (Apps Script)**: Deploy > Manage deployments > ดินสอ > Version: **New version** (URL เดิม) → **ไม่ต้องแก้ repo นี้**
- **ห้ามกด New deployment** (จะได้ URL ใหม่ ต้องส่งลิงก์ใหม่และเพิ่มไอคอนใหม่ทุกเครื่อง)
- repo นี้ **ไม่มีลิงก์แดชบอร์ด** (repo เป็น public) ลิงก์อยู่ในส่วน `#u=` ของลิงก์ที่ส่งให้พนักงานเท่านั้น

## ครั้งเดียว: Apps Script ต้องอนุญาตให้ฝังหน้า
`doGet()` ใน Code.gs (FD Multiverse รุ่น 1.1 ขึ้นไป) มี `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)` แล้ว
วาง Code.gs ใหม่ → บันทึก → Deploy > Manage deployments > New version

## ลิงก์ที่ส่งให้พนักงาน (ส่งทาง LINE ส่วนตัว อย่าโพสต์สาธารณะ)
```
https://kutsukung.github.io/smilehouse-dashboard/#u=<รหัส deployment>
```
รหัส deployment = ส่วนระหว่าง `/s/` กับ `/exec` ของ URL แดชบอร์ด (ขึ้นต้นด้วย AKfy…) ใส่ URL /exec ทั้งเส้นแทนก็ได้

## เพิ่มไอคอนในมือถือ
- **iPhone**: เปิดลิงก์ใน Safari > ปุ่มแชร์ > เพิ่มไปยังหน้าจอโฮม > เพิ่ม
- **Android**: เปิดลิงก์ใน Chrome > ⋮ > ติดตั้งแอป (หรือ เพิ่มลงในหน้าจอหลัก) หรือกดปุ่ม "ติดตั้งแอป Smilehouse" ในหน้า
- เปิดจากไอคอน = แดชบอร์ดเต็มจอ (เข้าด้วยชื่อ + PIN เหมือนเดิม) · เปิดลิงก์ในเบราว์เซอร์ = หน้าวิธีเพิ่มไอคอน
- เปิดจากไอคอนแล้วขึ้นช่อง "ใส่ลิงก์แดชบอร์ด": วางลิงก์ด้านบนครั้งเดียว

## ไฟล์
- `index.html` หน้าเปิดแอป (iPhone ใช้ apple-touch-icon และลิงก์ปัจจุบัน · Android ใช้ manifest และจำลิงก์ในเครื่อง)
- `manifest.webmanifest` ชื่อแอป ไอคอน สีพื้น (Android)
- `icons/` apple-touch-icon 180 px, icon 192/512, maskable 192/512 (ภาพย่อวางกลางสำหรับไอคอนวงกลม/สี่เหลี่ยมมนของ Android), favicon 32
- เปลี่ยนไอคอน: แทนไฟล์ใน `icons/` ชื่อเดิม ขนาดเดิม (iPhone ที่เพิ่มไอคอนไว้แล้วต้องลบแล้วเพิ่มใหม่จึงจะเห็นไอคอนใหม่)
