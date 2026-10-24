# BL-01 | Specification Baseline B1 | บ้านพร้อม R1

tag: B1 | date: 2569-09-06 | approved-by: SH-01 (เจ้าของ), กลุ่ม X (RE) | next-review: Baseline B2

## ขอบเขตของ baseline

- เข้า B1: REQ สถานะ Approved 23 ข้อ | UC-07, UC-03 (fully dressed) + 3 brief | BR-01..05 | AC-07-01..10, AC-03-01..04 |
  MD-ACT-07, MD-DOM-01, MD-STM-01, MD-CTX-01, MD-SEQ-07-05 | glossary v1.0 | data-dictionary v1.0
- ไม่เข้า B1: REQ สถานะ Draft (REQ-FN-041, REQ-IF-005, REQ-IF-006, REQ-PRV-00x) รอ Q-18/19/22 | REQ-AI-002 (Won't R1) |
  หมวด QA/OP/SEC/CMP จะเติมในบทเรียนกลุ่มความต้องการเชิงคุณภาพ
- คำถามเปิดที่ประกาศพร้อม baseline: Q-14, Q-18, Q-19, Q-20, Q-22 (พฤติกรรมชั่วคราวอยู่ใน spec)
- CC ที่ยังเปิด: CC-02, CC-05, CC-06, CC-07

## กติกาการเปลี่ยนแปลงหลัง B1

1. ทุกการเปลี่ยน REQ/AC/BR/MD ที่อยู่ใน B1 ต้องเปิด CR-xx (ผู้ขอ เหตุผล EV ใหม่ถ้ามี) ไว้ใน specs/<feature>/changes/
2. วิเคราะห์ผลกระทบด้วย RTM: กระทบ REQ/AC/MD/task ใดบ้าง
3. ผู้อนุมัติ: เปลี่ยน Must/ขอบเขต/BR = SH-01 | เปลี่ยนถ้อยคำ/แก้ CC = RE lead
4. เวอร์ชัน: patch (x.y.Z) = แก้ถ้อยคำไม่เปลี่ยนความหมาย | minor (x.Y) = เพิ่ม/แก้ REQ | major (X) = เปลี่ยนขอบเขต
5. Draft ที่ยังไม่เข้า B1 แก้ได้อิสระ แต่ต้องมีสถานะ Draft ชัดเจน

## CR ที่เปิดหลัง B1

| CR | เรื่อง | สถานะ |
|---|---|---|
| CR-01 | AC-07-04 นิยาม "ใกล้เคียง" เป็นไม่เกิน 3 ชั่วโมง | Approved 4 ต.ค. 2569 (RE lead: แก้ถ้อยคำให้วัดได้ ไม่เปลี่ยนความหมาย) |
| CR-02 | ทำให้ REQ-QA-003 วัดได้ด้วย QAS | Proposed รอ SH-01 |

## บันทึกตอนประกาศ B1 (ยกมาจาก repo baanprom-sdd-02-build)

### เวอร์ชันของต้นฉบับ

catalogue v1.0 | booking.feature v1.0 | models v1.0 | rules v1.0 | glossary v1.0 | specs/002-booking/spec.md (SPEC-BOOKING) v1.0
ต้นฉบับอื่นใน docs/srs ที่ใช้ประกอบ: catalogue-other.md, evidence.md, stakeholders.md, cc-log.md, questions.md, data-dictionary.md (ดู docs/srs/README.md)

### AI disclosure

docs/srs/ai-prompt-log.md #1 ถึง #19 | ส่วนที่ AI ร่าง: spec ส่วน 4 ถึง 6, โครงตารางตามรอย | ผู้ตรวจ: สมาชิกทุกคนลงชื่อ

### Checklist พร้อมประกาศ B1

- ทุก REQ ที่เข้า B1 มีช่องบังคับครบ มี EV-ID และสถานะ Approved: ผ่าน
- ทุก REQ-FN และ REQ-BR ที่เข้า B1 มี AC อย่างน้อยหนึ่งข้อ: ผ่านบางส่วน REQ-BR-002 ยังไม่มี AC โดยตรง (ตรวจด้วยตัวอย่างการคำนวณในตาราง BR-01) จดเป็นงานค้างของ RE lead
- CC-log ไม่มี Contradiction ที่เปิดอยู่: ผ่าน (CC-01 ปิดแล้ว)
- Glossary ครอบคลุมทุกสถานะและบทบาท: ผ่าน
- Open Questions ทุกข้อมีเจ้าของ กำหนด และพฤติกรรมชั่วคราว: ผ่าน (spec.md ส่วน 9 และ docs/srs/questions.md)
- ตัวเลขสมมติทุกตัวติดป้าย <ต้องยืนยัน> และมี Q-ID: ผ่าน (Q-18, Q-19)
- Non-goals อย่างน้อย 3 ข้อพร้อมเหตุผล: ผ่าน (5 ข้อ)
- ผู้รับรองเป็นเจ้าของความต้องการ: ผ่าน (SH-01)
- ทุกต้นฉบับอยู่ใน version control และติด tag B1: ผ่าน
