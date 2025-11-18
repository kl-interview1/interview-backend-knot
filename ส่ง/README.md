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
| GET    | /users/:id      | ดึงรายละเอียดผู้ใช้|
| POST   | /users          | สร้างผู้ใช้|
| PUT    | /users/:id      | แก้ไขผู้ใช้|
| DELETE | /users/:id      | ลบผู้ใช้|

### Courses
| Method | Endpoint          | Description  |
|--------|-----------------|------------------------------------|
| GET    | /courses         | ดึงรายการคอร์ส|
| GET    | /courses/:id     | ดึงรายละเอียดคอร์ส|
| POST   | /courses         | สร้างคอร์ส (Admin Only)|
| PUT    | /courses/:id     | แก้ไขคอร์ส (Admin Only)|
| DELETE | /courses/:id     | ลบคอร์ส (Admin Only)|

### Enrollments
| Method | Endpoint | Description|
|--------|-------------------|---------------------------------------------|
| GET    | /enrollments       | ดึงรายการการลงทะเบียน|
| POST   | /enrollments       | ลงทะเบียนผู้ใช้ในคอร์ส|
| DELETE | /enrollments/:id   | ลบการลงทะเบียน|


## รูปตัวอย่างการใช้งาน API อยู่่ใน folder photo ใน rar

