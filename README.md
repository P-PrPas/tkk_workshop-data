# tkk_workshop-data

ข้อมูลสำหรับ workshop CV101 — ผูกเป็น submodule `data/` ของ repo หลัก
สเปกอยู่ที่ [`docs/02-data.md`](https://github.com/P-PrPas/tkk_workshop/blob/main/docs/02-data.md)

```
images/{train,val,test}/   รูป .jpg  (10 / 2 / 3)
labels/{train,val,test}/   label YOLO .txt ชื่อตรงกับรูป  (class cx cy w h, normalize 0-1)
cup.yaml                   dataset config (1 class: cup)
sample.mp4                 วิดีโอสำรอง ~20 วิ ใช้เมื่อกล้องพัง
```

รูป label และวิดีโอถ่าย/เตรียมโดยเจ้าของงาน ยังไม่ commit ในรอบนี้
