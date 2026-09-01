# tkk_workshop-data

ข้อมูลสำหรับ workshop CV101 — ผูกเป็น submodule `data/` ของ repo หลัก
สเปกอยู่ที่ [`docs/02-data.md`](https://github.com/P-PrPas/tkk_workshop/blob/main/docs/02-data.md)

```
images/{train,val,test}/   รูป .jpg  (10 / 2 / 3)
labels/{train,val,test}/   label YOLO .txt ชื่อตรงกับรูป  (class cx cy w h, normalize 0-1)
cup.yaml                   dataset config (1 class: cup)
```

## สถานะ
- `images/` + `labels/` — 15 รูป (10/2/3) พร้อม label ครบแล้ว
  label ทำแบบ auto-label: รัน `yolo11x.pt` (COCO) กรองเฉพาะ class 41 = cup แปลงเป็น class 0
  ยกเว้น `test/IMG_7184` (มุมมองจากด้านบน โมเดลจับไม่ได้) ตีกล่องด้วยมือ
  ตรวจกล่องทุกใบด้วยตาแล้ว
- test มีรูปยากตามสเปก: `IMG_7184` (มองจากบน พื้นสว่าง), `IMG_7192` (แก้วเล็กในฉากรก มีขวดในเฟรม)
- ไม่มี `sample.mp4` — พาร์ท realtime เปิดกล้องใน Colab ตรงๆ ถ้ากล้องพังหน้างานให้อัดคลิปสดแล้วใช้ `run_video()`
