# baanprom-sdd-03-vv

repo ตัวอย่างของรายวิชา 517511-266 Requirement Engineering (AI-Native RE)
ภาควิชาคอมพิวเตอร์ คณะวิทยาศาสตร์ มหาวิทยาลัยศิลปากร

เคส: บ้านพร้อม (แพลตฟอร์มจองช่างซ่อมบ้าน) feature ที่ทำครบรอบคือ UC-07 จองงานบริการซ่อมบำรุง
ข้อมูลทั้งหมดในเคสนี้เป็นข้อมูลสมมติเพื่อการสอน

## repo นี้คืออะไร

repo นี้คือสภาพงานของกลุ่มตัวอย่าง (กลุ่ม X) หลังทำครบรอบแรกของ Spec-Driven Development
คือ /clarify, /plan, /tasks, /implement แล้วรัน test ทั้งชุด กรอกตารางผล AC บันทึกช่องว่าง เปิด CR-01 และ CR-02 และทำข้อกำหนดคุณภาพให้วัดได้

ทุกไฟล์ที่ AI สร้างถูกเก็บไว้ตามที่สร้างจริง
รวมถึงจุดที่ AI ทำผิดกติกาและทีมสั่งแก้ (ดู specs/002-booking/gaps.md และ prompt-log.md)

## ใช้เริ่มบทเรียนไหน และเป็นเฉลยของบทไหน

- ใช้เริ่มบทเรียน **Verification, Validation และ Change**
- เป็นเฉลยของบทเรียน **AI Build from Spec**

## ชุด repo ทั้ง 8

แต่ละ repo คือจุดเริ่มของบทหนึ่ง และเป็นเฉลยของบทก่อนหน้า repo ถัดไปจึงเป็นเฉลยของงานในบทนี้

| repo | ใช้เริ่มบท | ข้างในคือเฉลยของ |
|---|---|---|
| [baanprom-sdd-01-spec](https://github.com/ppsajja/baanprom-sdd-01-spec) | Modern Specification และ SDD | ชิ้นงานบท 1 ถึง 7 (Problem Framing ถึง Integrated Modelling) |
| [baanprom-sdd-02-build](https://github.com/ppsajja/baanprom-sdd-02-build) | AI Build from Spec | Modern Specification และ SDD: spec plan tasks ที่กลุ่มเขียนเอง และ Baseline B1 |
| **baanprom-sdd-03-vv** (repo นี้) | Verification, Validation และ Change | AI Build from Spec: โค้ดและ test ที่ AI สร้าง ac-results gaps CR-01 CR-02 |
| [baanprom-sdd-04-ops](https://github.com/ppsajja/baanprom-sdd-04-ops) | Operational, Security และ Privacy | V&V และ Change: RTM mockup CR-03 ถึง CR-06 Baseline B2 และ R1 ครบ (003 004) |
| [baanprom-sdd-05-ai](https://github.com/ppsajja/baanprom-sdd-05-ai) | Data, AI และ Agent | Operational, Security และ Privacy: CR-07 อนุมัติ และ Baseline B3 |
| [baanprom-sdd-06-accept](https://github.com/ppsajja/baanprom-sdd-06-accept) | RE in One Line และการตรวจรับ | Data, AI และ Agent: ผู้ช่วย AI UC-14 (CR-09) และ Baseline B4 |
| [baanprom-sdd-07-r1-done](https://github.com/ppsajja/baanprom-sdd-07-r1-done) | บทเสริม การตรวจรับและการส่งมอบ | RE in One Line และการตรวจรับ: ตรวจรับ R1 (CR-10) และ Baseline B5 |
| [baanprom-sdd-08-complete](https://github.com/ppsajja/baanprom-sdd-08-complete) | (ระบบสมบูรณ์ของวิชา) | บทเสริม การตรวจรับและการส่งมอบ: R2 ครบทุก UC ส่งมอบตาม TOR และ Baseline B7 |

## อะไรใหม่เมื่อเทียบกับ repo ก่อนหน้า (baanprom-sdd-02-build)

| ไฟล์ | สิ่งที่เพิ่มหรือแก้ | เพราะอะไร |
|---|---|---|
| specs/002-booking/spec.md | เป็นรุ่น 1.1 (v2 หลัง /clarify) และ 1.2 (v3 ผ่าน CR-01) มีแถว CR-02 ที่รออยู่ใน Change Log | AI ถามก่อนแล้วทีมตอบ และ AC-07-04 ต้องวัดได้ก่อนเขียน assert |
| specs/002-booking/plan.md, tasks.md | เป็นแผนและงานย่อยที่ AI สร้างด้วย /plan และ /tasks (tasks.md มีบรรทัด "แก้รอบที่ 1") | ขั้น /plan และ /tasks ของบท AI Build |
| specs/002-booking/plan-compare.md, tasks-compare.md | ไฟล์ใหม่ เทียบของ AI กับที่กลุ่มเขียนเองด้วยมือ | ให้เห็นว่า AI ลืมอะไร และกลุ่มลืมอะไร |
| backend/, frontend/ | โค้ดและ test ของ T-01 ถึง T-11 test ตั้งชื่อตาม AC | ขั้น /implement ทีละ task |
| specs/002-booking/test-run.txt | ไฟล์ใหม่ ผลรัน pytest และ vitest จริง | ขั้นรัน test ทั้งชุด |
| specs/002-booking/ac-results.md, gaps.md | ไฟล์ใหม่ ตารางผล AC และช่องว่าง GAP-01 ถึง GAP-10 | กรอกจาก test-run.txt และทุกครั้งที่เจอจุดพลาด |
| specs/002-booking/changes/CR-01.md, CR-02.md | ไฟล์ใหม่ | แก้ของที่อยู่ใน Baseline B1 ต้องผ่าน CR |
| specs/002-booking/quality-requirements.md | ไฟล์ใหม่ QAS 6 ช่อง ค่าเป้าหมาย 3 ระดับ | ทำให้ "เร็ว ใช้ง่าย เสถียร" วัดได้ |
| prompt-log.md | เพิ่มบันทึก #20 ถึง #34 | ทุกคำสั่ง คำถามของ AI และคำตอบของทีม |
| docs/srs/baseline.md | เพิ่มตาราง CR ที่เปิดหลัง B1 | CR-01 อนุมัติแล้ว CR-02 รอ SH-01 |
| docs/srs/UC-07.md, glossary.md, specs/002-booking/rules.md, quality-requirements.md, frontend/src/App.jsx | แก้รหัสให้ตรงหน้าบทเรียน: การเข้าสู่ระบบของลูกค้าคือ UC-02 ของช่างคือ UC-01 คิวรอ (waitlist) ยังไม่มีรหัส UC ข้อเสนอเรื่องแก้ง่ายคือ REQ-QA-005 หัวหน้าช่างคือ SH-06 และเวลารอชำระ 30 นาทีเป็นคนละค่ากับการล็อก 10 นาที | ให้รหัสตรงกับ Use Case Diagram และทะเบียนผู้มีส่วนได้เสียในหน้าบทเรียน |

## อ่านรอบ AI Build ตามลำดับนี้

| ลำดับ | เปิดไฟล์ | ดูอะไร |
|---|---|---|
| 1 | specs/002-booking/spec.md ส่วน Change Log และ prompt-log.md #20 | AI ถามอะไรตอน /clarify และทีมตอบอย่างไร |
| 2 | specs/002-booking/plan.md และ plan-compare.md | เทคโนโลยีที่ทีมเลือกเอง และสิ่งที่แผนของกลุ่มลืม |
| 3 | specs/002-booking/tasks.md และ tasks-compare.md | บรรทัด "แก้รอบที่ 1" และ task ที่ติดคำถามเปิด |
| 4 | backend/tests/test_booking.py | test ตั้งชื่อตาม AC และ Given / When / Then ในโค้ด |
| 5 | specs/002-booking/test-run.txt และ ac-results.md | ผลรันจริง และสรุปสามบรรทัด |
| 6 | specs/002-booking/gaps.md และ changes/CR-01.md | ช่องว่างแยกตามสาเหตุ และการแก้สเปกก่อนแก้โค้ด |
| 7 | specs/002-booking/quality-requirements.md และ changes/CR-02.md | QAS 6 ช่อง และ CR ที่ยังรอเจ้าของ |

## งานของบทนี้ที่นักศึกษาต้องทำต่อ

บทเรียน Verification, Validation และ Change ทำรอบเปลี่ยนแปลงหนึ่งรอบกับ repo นี้

1. อัปเดตชุดคำสั่งเป็นรุ่น 2 (AGENTS.md 10 ข้อ และแบบเอกสารใน docs/)
2. ตามรอยด้วยตาราง RTM หาสายที่ขาด ได้ specs/002-booking/rtm.md
3. เอาหน้าจอ (mockup) เข้าสเปก ได้ specs/002-booking/mockups/ และ changes/CR-03.md
4. ย้าย Constraint ที่ใช้ทุก feature ไปไฟล์กลาง ได้ specs/000-shared/constraints.md และ changes/CR-04.md
5. แก้ plan, tasks และโค้ดเฉพาะจุด แล้วรัน test ทั้งชุดซ้ำ เทียบก่อนและหลังใน ac-results.md
6. ตั้ง Baseline B2 ใน docs/srs/baseline.md

ผลลัพธ์ของทุกข้ออยู่ใน repo ถัดไป **baanprom-sdd-04-ops**
repo นั้นมีรอบ R1 release ต่อท้ายด้วย (feature 003-job-status ผ่าน CR-05 และ 004-cancel-refund ผ่าน CR-06)
ทำของตัวเองก่อน แล้วค่อยเปิดเฉลย

## ถ้าทำของตัวเองพลาดหรือไม่ทัน

เอา repo นี้ไปทำต่อได้สองทาง

ทางที่ 1 บน GitHub

- เปิดหน้า repo นี้ กด Use this template แล้วเลือก Create a new repository
- ตั้งชื่อ repo ของกลุ่ม แล้วเปิดด้วย Codespaces

ทางที่ 2 clone แล้วเปลี่ยน remote

```
git clone https://github.com/ppsajja/baanprom-sdd-03-vv.git baanprom-group
cd baanprom-group
git remote set-url origin https://github.com/<บัญชีของกลุ่ม>/<ชื่อ repo ของกลุ่ม>.git
git push -u origin main
```

`git remote set-url origin` เปลี่ยนปลายทางของ push จาก repo ของผู้สอนเป็น repo ของกลุ่ม (ต้องสร้าง repo เปล่าบน GitHub ไว้ก่อน)

## ทีม

- ชื่อทีม: กลุ่ม X (ตัวอย่างของรายวิชา)
- สมาชิก: สมาชิก A, สมาชิก B, สมาชิก C, สมาชิก D
- เครื่องมือ AI ที่ใช้: Copilot Chat โหมด Agent ใน GitHub Codespaces (ผู้สอนเดโมด้วย Claude Code)

## โครงของ repo

```
README.md                      ไฟล์นี้
AGENTS.md                      กติกาที่ AI ต้องทำตาม 7 ข้อ + ข้อ 8 ของรายวิชา (agent-pack รุ่น 1)
CLAUDE.md                      ชี้ไป AGENTS.md (สำหรับ Claude Code)
prompt-log.md                  บันทึกทุกคำสั่ง คำถาม คำตอบ และสิ่งที่ AI เดา (เพิ่มต่อท้ายเท่านั้น)
docs/srs/                      ต้นฉบับจากบทเรียนก่อนหน้า: catalogue, UC-07, glossary, baseline B1
docs/agent-pack-README.md      วิธีติดตั้งและใช้ชุดคำสั่ง
specs/README.md                ดัชนี feature
specs/002-booking/             feature ที่ทำครบรอบ (ดูตารางด้านล่าง)
backend/                       Python FastAPI + SQLAlchemy (test ใช้ SQLite ในหน่วยความจำ)
frontend/                      React (Vite) + Tailwind CSS + Vitest
.github/prompts/               คำสั่ง /clarify /plan /tasks /implement สำหรับ Copilot
.claude/commands/              คำสั่งชุดเดียวกัน สำหรับ Claude Code
.cursor/commands/              คำสั่งชุดเดียวกัน สำหรับ Cursor
```

## ไฟล์ใน specs/002-booking/ และใครสร้าง

| ไฟล์ | ใครสร้าง | เกิดในขั้นไหน |
|---|---|---|
| spec.md | กลุ่มเขียน v1, AI แก้เป็น v2 หลัง /clarify, กลุ่มแก้ v3 ผ่าน CR-01 | บทเรียน Modern Specification และ SDD และ /clarify |
| booking.feature | กลุ่ม (จากบทเรียน Stories, Scenarios และ Use Cases) | ก่อน /clarify |
| rules.md, models.md | กลุ่ม (สรุปจาก docs/srs) | ก่อน /clarify |
| plan.md | AI (/plan) ทีมตรวจแล้ว | /plan |
| plan-compare.md | กลุ่ม | เทียบ plan ของ AI กับที่กลุ่มเขียนเอง |
| tasks.md | AI (/tasks) ทีมสั่งแก้ 1 รอบ | /tasks |
| tasks-compare.md | กลุ่ม | เทียบ tasks ของ AI กับที่กลุ่มเขียนเอง |
| test-run.txt | pytest และ vitest (ผลรันจริง) | รัน test ทั้งชุด |
| ac-results.md | กลุ่ม | กรอกจาก test-run.txt |
| gaps.md | กลุ่ม | ทุกครั้งที่พบจุดพลาด |
| changes/CR-01.md, CR-02.md | กลุ่ม | เมื่อต้องแก้สิ่งที่อยู่ใน Baseline B1 |
| quality-requirements.md | กลุ่ม | ขั้นทำข้อกำหนดคุณภาพให้วัดได้ ในบท AI Build from Spec |

## วิธีรัน

หลังบ้าน

```
cd backend
pip install -r requirements.txt
python -m pytest -v -k "AC_"
uvicorn app.main:app --reload --port 8000
```

หน้าจอ

```
cd frontend
npm install
npm test
npm run dev
```

ถ้าเปิดด้วย GitHub Codespaces คำสั่ง pip install และ npm install ถูกรันให้แล้วตอนสร้างเครื่อง

ผลที่ควรเห็น (รันจริงจาก repo นี้)

- Python 3.11: บรรทัดสุดท้าย `15 passed, 1 skipped` (อาจมี `1 warning` จาก starlette รุ่นใหม่ ไม่กระทบผล)
- Python 3.12 ขึ้นไป: `1 failed, 14 passed, 1 skipped` ตัวที่ไม่ผ่านคือ test_AC_07_08_search_under_load_scaled
- หน้าจอ: `Test Files 1 passed (1)` และ `Tests 1 passed (1)`

เรื่อง Python 3.12: ไม่มีใครแก้โค้ดส่วนนั้น สาเหตุคือ SQLite ในหน่วยความจำใช้ connection เดียวร่วมกัน 20 เธรด
บทเรียน Verification, Validation และ Change เจอเรื่องนี้ตอนรันซ้ำบนเครื่องที่สอง และบันทึกเป็น GAP-15 ใน repo ถัดไป
ถ้าอยากให้ test ผ่านก่อนเริ่มบท ให้หยิบไฟล์ที่แก้แล้วจาก repo ถัดไปไฟล์เดียว

```
git remote add next https://github.com/ppsajja/baanprom-sdd-04-ops.git
git fetch next
git checkout next/main -- backend/app/db/session.py
```

## สิ่งที่รู้อยู่แล้วว่ายังไม่ใช่ของจริง

- ทุก endpoint รับ `now=...` ใน query เพื่อให้ test กำหนดเวลาได้ (backend/app/clock.py) ก่อนขึ้นระบบจริงต้องปิดช่องนี้
- FakeGateway ใช้แทน Payment Gateway จริง (IF-01) และคิวแจ้งเตือนอยู่ในหน่วยความจำ (IF-02)
- ระยะทาง BR-03 ใช้สูตรคำนวณจากพิกัดแทนบริการแผนที่ (IF-03)
- AC-07-08 ผ่านแบบย่อส่วน 20 คำขอเท่านั้น ผลตรวจรับจริงต้องวัดบนเครื่องทดสอบ (รอ CR-02)
- AC-07-08 ไม่ผ่านบน Python 3.12 ขึ้นไป (ดูหัวข้อวิธีรัน)
- ลูกค้าและที่อยู่บนหน้าจอเป็นค่าคงที่ เพราะการเข้าสู่ระบบและเลือกที่อยู่เป็นของ UC-02
- `backend/seed_demo.py` ใส่ข้อมูลสมมติไว้เปิดดูหน้าจอ ไม่ใช่ส่วนของระบบ

## คำถามที่ยังเปิด และจะได้คำตอบใน repo ไหน

| คำถาม | เรื่อง | สถานะใน repo ถัดไป |
|---|---|---|
| CR-02 | ทำให้ REQ-QA-003 วัดได้ด้วย QAS (รอ SH-01) | ยังรอ SH-01 ใน baanprom-sdd-04-ops ไม่เข้า B2 |
| Q-14 | BR-01 R3 ยกเลิกขณะช่างเดินทาง คืนเท่าไร | ยังเปิดใน baanprom-sdd-04-ops (เลื่อนกำหนดตอบ) ระหว่างนี้ใช้พฤติกรรมชั่วคราวใน spec.md |
| Q-18, Q-19, Q-22, Q-23 | ระยะล็อก 10 นาที, timeout ของ gateway, geoPoint, ใครปลดล็อก | ยังเปิดใน baanprom-sdd-04-ops และประกาศพร้อม Baseline B2 |
| คิวรอ (waitlist) ใน UC-07 A1 | ยังไม่มีรหัส UC (docs/srs/UC-07.md อ้าง Q-33) | Q-33 ถูกเปิดอย่างเป็นทางการตอน /clarify ของ 004-cancel-refund ใน baanprom-sdd-04-ops |
| ช่องว่างที่ test ไม่เห็น | ความต้องการที่ไม่มี AC และหน้าจอที่ไม่มีในสเปก | เจอด้วย rtm.md และ mockup ใน baanprom-sdd-04-ops (F-01 ถึง F-08, Q-26 ถึง Q-29) |

## Reflection ของกลุ่ม X (5 บรรทัด)

1. คำถามของ AI ที่ไม่คาดคิด: ถามว่า "ใกล้เคียง" ใน AC-07-04 หมายถึงกี่ชั่วโมง ทั้งทีมไม่เคยสงสัยเลยจนกระทั่งต้องเขียน assert
2. คำถามของเพื่อนที่ AI ไม่ถาม: กลุ่มข้างเคียงถามว่าถ้าลูกค้าปิดเบราว์เซอร์ระหว่างล็อกช่วงเวลา ใครปลดล็อก (AI ถือว่าหมดอายุเองโดยไม่ถาม)
3. กฎที่ AI ละเมิดและจับได้: /implement T-01 แตะ router.py ซึ่งเป็นไฟล์ของ T-04 (กติกา "แตะเฉพาะไฟล์ในช่องไฟล์ที่แตะ") และ /tasks ตั้ง T-06 เป็นพร้อมทำทั้งที่ R3 รอ Q-14
4. สิ่งที่สเปกของกลุ่มคุมได้: ทุก endpoint อ้าง REQ ได้ ไม่มีฟีเจอร์เกิน ไม่มีคอลัมน์เบอร์โทรใน log และช่างไม่เห็นเบอร์ก่อน 2 ชั่วโมง
5. สิ่งที่หลุด: ค่า timeout ของ gateway ที่สเปกกับ Interface Contract บอกไม่ตรงกัน (GAP-07) และ "ระบบต้องเร็ว" ที่ยังวัดไม่ได้จนต้องเปิด CR-02
