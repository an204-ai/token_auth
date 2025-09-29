# Token Authentication Lab

Demo project về **JWT/Token-based Authentication** với Node.js + MongoDB.  
Ứng dụng minh họa các bước đăng ký, đăng nhập và truy cập profile với token.

---

## How to run

```bash
npm install
node app.js
⚠️ MongoDB phải chạy trước (local hoặc docker).

Endpoints & How to test (POSTMAN)
🔹 Register
URL: POST http://localhost:3000/register
Body JSON:
{ "username": "testuser", "password": "12345" }
Expected: User registered, redirect /login
![](public/results/register.png)

🔹 Login
URL: POST http://localhost:3000/login

Body JSON:
{ "username": "testuser", "password": "12345" }
Expected: Login success → nhận được token
![](public/results/login.png)

🔹 Profile (No Token)
URL: GET http://localhost:3000/profile
Header: Không gửi token
Expected: Bị từ chối truy cập (Unauthorized)
![](public/results/profile_no_token.png)

🔹 Profile (With Token)
URL: GET http://localhost:3000/profile
Header: Authorization: Bearer <token>
Expected: Hiển thị thông tin user trong profile page
![](public/results/profile_with_token.png)

Commit & push lên GitHub
bash
Sao chép mã
git init
git add .
git commit -m "Token auth lab"
git remote add origin https://github.com/an204-ai/token_auth
git branch -M main
git push -u origin main
