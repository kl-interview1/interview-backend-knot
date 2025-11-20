# InterViewTest

## 🔹 Setup Database
1. สร้าง db :
```bash
psql postgresql://interview_usr_5c6bc2:IntV_2025_8e0cfbf4@10.0.100.153:15432/interview_db_20251118_1541 -f Database/migrations/create_db.sql
```

2. จำลองข้อมูล
```bash
psql postgresql://interview_usr_5c6bc2:IntV_2025_8e0cfbf4@10.0.100.153:15432/interview_db_20251118_1541 -f Database/seed/test.sql
```

3. แตกไฟล์ InterViewTest.rar

4. npm install

5. node app.js

Server จะรันที่ http://localhost:3000

## 🔹 API Endpoints

### Users
| Method | Endpoint        | Description       |
|--------|----------------|------------------------------|
| GET    | /users          | ดึงรายการผู้ใช้งาน|
| GET    | /user/:id      | ดึงรายละเอียดผู้ใช้|
| POST   | /user         | สร้างผู้ใช้|
| PUT    | /user/:id      | แก้ไขผู้ใช้|
| DELETE | /user/:id      | ลบผู้ใช้|

### Courses
| Method | Endpoint          | Description  |
|--------|-----------------|------------------------------------|
| GET    | /courses         | ดึงรายการคอร์ส|
| GET    | /course/:id     | ดึงรายละเอียดคอร์ส|
| POST   | /courses        | สร้างคอร์ส (Admin Only)|
| PUT    | /course/:id     | แก้ไขคอร์ส (Admin Only)|
| DELETE | /course/:id     | ลบคอร์ส (Admin Only)|

### Enrollments
| Method | Endpoint | Description|
|--------|-------------------|---------------------------------------------|
| GET    | /enrollments       | ดึงรายการการลงทะเบียน|
| POST   | /enrollment       | ลงทะเบียนผู้ใช้ในคอร์ส|
| DELETE | /enrollment/:id   | ลบการลงทะเบียน|

## 🔹 Parameter

### Users
GET /users
Parameters:
- page (number, optional) – หน้าเริ่มต้น (default = 1)
- limit (number, optional) – จำนวนรายการต่อหน้า (default = 10)
- name (string, optional) – ค้นหาจากชื่อหรือนามสกุล
- course_id (number, optional) – คอร์สที่ต้องการหา

GET /user/:id
Path Parameters:
- id (number, required) – รหัสผู้ใช้

POST /user
Body Parameters:
- email (string, required) – อีเมล
- password (string, required) – รหัสผ่าน
- role (string, required) – admin | trainer | student
- first_name (string, required) – ชื่อ
- last_name (string, required) – นามสกุล
- phone (string, optional) – เบอร์โทร
- address (string, optional) – ที่อยู่
- user_name (string, required) – ผู้ทำรายการ

PUT /user/:id
Path Parameters:
- id (number, required) – รหัสผู้ใช้
Body Parameters (ส่งเฉพาะที่ต้องการแก้ได้):
- email (string, optional)
- password (string, optional)
- role (string, optional)
- first_name (string, optional)
- last_name (string, optional)
- phone (string, optional)
- address (string, optional)
- user_name (string, required) – ผู้ทำรายการ

DELETE /user/:id
Path Parameters:
- id (number, required) – รหัสผู้ใช้

---

### Courses
GET /courses
Parameters:
- page (number, optional) – default = 1
- limit (number, optional) – default = 10
- title (string, optional) – ค้นหาจากชื่อคอร์ส
- trainer_id (number, optional) – ดึงเฉพาะคอร์สของ trainer

GET /course/:id
Path Parameters:
- id (number, required) – รหัสคอร์ส

POST /courses (Admin Only)
Body Parameters:
- title (string, required) – ชื่อคอร์ส
- description (string, optional) – รายละเอียดคอร์ส
- trainer_id (number, required) – trainerของคอร์ส
- start_date(date, required) - วันเริ่มต้น course
- end_date(date, required) - วันสิ้นสุด course
- isAdmin(boolean, required) - เป็น admin = 1, ไม่เป็น admin = 0
- user_name (string, required) - ผู้ทำรายการ

PUT /course/:id (Admin Only)
Path Parameters:
- id (number, required)
Body Parameters:
- title (string, optional)
- description (string, optional)
- trainer_id (number, optional)
- start_date(date, required)
- end_date(date, required)
- isAdmin(boolean, required)
- user_name (string, required)

DELETE /course/:id (Admin Only)
Path Parameters:
- id (number, required)
Body Parameters:
- isAdmin(boolean, required)

---

### Enrollments

GET /enrollments
Parameters:
- page (number, optional) – default = 1
- limit (number, optional) – default = 10
- user_id (number, optional) – ดึงเฉพาะนักเรียนคนหนึ่ง
- course_id (number, optional) – ดึงเฉพาะคอร์ส
- trainer_id (number, optional) – ดึงเฉพาะคอร์สของผู้สอน

POST /enrollment
Body Parameters:
- user_id (number, required) – นักเรียน
- course_id (number, required) – คอร์สที่ต้องการลงทะเบียน
- user_name (string, required) – ผู้ทำรายการ

DELETE /enrollment/:id
Path Parameters:
- id (number, required) – enrollment_id

## รูปตัวอย่างการใช้งาน API อยู่่ใน folder photo ใน rar
## 🔹 Feedback
- ต้องใช้ VPN ในการเชื่อม DB
- น่าจะต้องให้อธิบาย database
- ให้พัฒนา Service สำหรับระบบจัดการหลักสูตรอบรม โดยประกอบด้วย 4 table อาจทำให้นึกว่ามี table อยู่แล้ว
- การส่งงานยังไม่เคลียร์เท่าไหรว่าส่งยังไง
- Filtering / Searching ต่างกันอย่างไร
- เวลาการทำใช้เวลาประมาณ 5-6 ชม 





