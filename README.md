# Token Authentication Lab

Demo project về **JWT/Token-based Authentication** với Node.js + MongoDB.  
Ứng dụng minh họa các bước đăng ký, đăng nhập và truy cập profile với token.

---

## How to run
```bash
npm install
node app.js
```
⚠️ Lưu ý: MongoDB phải chạy trước (local hoặc docker).  
Ứng dụng mặc định chạy ở: [http://localhost:3000](http://localhost:3000)

---

## Endpoints & How to test (POSTMAN)

### Register
POST `http://localhost:3000/register`  
Body JSON:
```json
{ "username": "bob", "password": "12345" }
```
Expected: User registered, redirect `/login`  
![register](public/results/register.png)

---

### Login
POST `http://localhost:3000/login`  
Body JSON:
```json
{ "username": "bob", "password": "12345" }
```
Expected: Login success, redirect `/profile`  
![login](public/results/login.png)

---

### Profile (No Token)
GET `http://localhost:3000/profile`  
Expected: Không có token → Không truy cập được  
![profile_no_token](public/results/profile_no_token.png)

---

### Profile (With Token)
GET `http://localhost:3000/profile` kèm token  
Expected: Hiển thị thông tin user trong profile page  
![profile_with_token](public/results/profile_with_token.png)

---

### Logout
GET `http://localhost:3000/logout`  
Expected: Session destroyed, redirect `/login`  
![logout](public/results/logout.png)

---

## Screenshots
(Ảnh nằm trong thư mục `public/results/` đã commit)

---

## Commit & Push
```bash
git add .
git commit -m "Add README with usage instructions + screenshots"
git push origin main
```
