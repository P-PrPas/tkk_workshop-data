# tkk_workshop-data

ข้อมูลสำหรับ workshop CV101 — ผูกเป็น submodule `data/` ของ repo หลัก
สเปกอยู่ที่ [`docs/02-data.md`](https://github.com/P-PrPas/tkk_workshop/blob/main/docs/02-data.md)

```
images/{train,val,test}/   รูป .jpg
labels/{train,val,test}/   label YOLO .txt ชื่อตรงกับรูป  (41 cx cy w h, normalize 0-1)
cup.yaml                   dataset config — สคีมา COCO 80 คลาส (cup = 41)
hand_landmarker.task       mirror ของ MediaPipe (เผื่อ URL ต้นทางตาย) — แอปใช้ไฟล์นี้ถ้ามี
```

## สถานะ
- `images/` + `labels/` — train ~33 (รูปในห้อง `IMG_*` 15 + รูปแก้วทั่วไป `coco_*` ~18), val 2, test 3
  label เป็น **class 41** (`cup` ในสคีมา COCO) — โมเดลจิ๋วต้องเก็บหัว 80 คลาสไว้ ดู docs/03
  `IMG_*` auto-label ด้วย `yolo11x.pt` (`IMG_7184` ตีมือ) · `coco_*` มาจาก COCO val2017
  ตรวจกล่องทุกใบด้วยตาแล้ว
- test มีรูปยากตามสเปก: `IMG_7184` (มองจากบน พื้นสว่าง), `IMG_7192` (แก้วเล็กในฉากรก มีขวดในเฟรม)
- ไม่มี `sample.mp4` — พาร์ท realtime เปิดกล้องใน Colab ตรงๆ ถ้ากล้องพังหน้างานให้อัดคลิปสดแล้วใช้ `run_video()`
