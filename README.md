# 3 Road Down — Data Hub (BDI BKK Hackathon 2026)

> **SafePath BKK × AroundBangkok × Tor Sai · Data for better Journey Research**
> พื้นที่กลางรวม dashboard และกราฟที่ประมวลผลแล้ว ให้ทีมเข้ามาดู / ดึงไปใช้ได้

🔗 **เว็บไซต์ (GitHub Pages):** https://veekeancodemaipen.github.io/3RoadDown_BDI_BKK_Hackathon_2026/

---

## มีอะไรบ้าง (Knowledge Map)

หน้า `index.html` คือ "แผนที่ความรู้" รวมทุกอย่างที่ประมวลผลแล้ว — ค้นหา / กรอง / เปิด / ดาวน์โหลดได้ในหน้าเดียว

| โฟลเดอร์ | มีอะไร |
|---|---|
| `dashboards/` | Dashboard HTML แบบเปิดดูได้เลย (self-contained) |
| `charts/` | กราฟ/ไดอะแกรมเป็นไฟล์ PNG ดาวน์โหลดได้ |
| `catalog.json` | ทะเบียนรายการทั้งหมด — หน้าเว็บอ่านไฟล์นี้มาแสดง |
| `index.html` | หน้า hub (ไม่ต้องแก้เวลามีของใหม่) |

### รายการตอนนี้
- **Traffy Fondue — Dashboard 5 ปี (2565–2569)** — เทรนด์เรื่องร้องเรียนการเดินทาง/ทางเท้า กทม.
- **Dashboard เรื่องร้องเรียน Traffy Fondue** — สรุปแบบกราฟอินเทอแอกทีฟ
- **ตารางข้อมูลดิบ Traffy 5 ปี (2565–2569)** — ค้น/กรอง/เรียงในหน้าได้
- **กราฟแยกตามกลุ่มประเภท** · **กราฟเขตสูงสุด** · **แผนภาพรวมโปรเจกต์** (PNG)

---

## ➕ วิธีเพิ่มของใหม่ (รองรับการสเกล)

1. วางไฟล์ลง `dashboards/` (HTML) หรือ `charts/` (PNG)
2. เพิ่ม 1 บล็อกใน `catalog.json`:

```json
{
  "id": "ชื่อสั้นไม่ซ้ำ",
  "title": "ชื่อที่จะแสดง",
  "type": "dashboard",          // "dashboard" หรือ "chart"
  "file": "dashboards/ไฟล์.html",
  "desc": "คำอธิบายสั้น ๆ",
  "updated": "2026-06-19",
  "tags": ["traffy", "mobility"]
}
```

3. commit + push — หน้าเว็บอัปเดตให้อัตโนมัติ **ไม่ต้องแก้ HTML**

---

## เปิดดูในเครื่อง
อย่าดับเบิลคลิกไฟล์ตรง ๆ (browser จะโหลด `catalog.json` ไม่ได้) — รันเซิร์ฟเวอร์เล็ก ๆ แทน:

```bash
python3 -m http.server 8000
# เปิด http://localhost:8000
```

---

## หมายเหตุ
- ชุดข้อมูลดิบ CSV 5 ปี (~144MB) ยังไม่ได้ใส่ใน repo เพื่อให้เบา — ถ้าต้องการให้ทีมโหลด CSV เพิ่ม ทำเป็นไฟล์ zip หรือ GitHub Releases ได้
- ที่มาข้อมูล: Traffy Fondue (เรื่องร้องเรียนเมือง กรุงเทพฯ)
