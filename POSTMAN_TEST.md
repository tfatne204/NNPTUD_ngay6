# Hướng dẫn test Postman từng bước (server chạy npm start)

## 1. Tạo user (nếu chưa có)
**Method:** POST  
**URL:** `http://localhost:3000/api/v1/users`  
**Headers:** Content-Type: application/json  
**Body raw JSON:**
```
{
  \"username\": \"testuser\",
  \"password\": \"Test123!\",
  \"email\": \"test@example.com\",
  \"role\": \"69b2763ce64fe93ca6985b56\"
}
```
**Response:** Copy **_id** user (VD: 64f...).

**Screenshot 1:** Request + Response.

## 2. Login
**Method:** POST  
**URL:** `http://localhost:3000/api/v1/auth/login`  
**Body raw JSON:**
```
{
  \"username\": \"testuser\",
  \"password\": \"Test123!\"
}
```
**Response:** Copy **token** string.

**Screenshot 2:** Request + token response.

## 3. Test /me  
**Method:** GET  
**URL:** `http://localhost:3000/api/v1/auth/me`  
**Headers:** 
- Authorization: `Bearer [paste_token_day]`
**Response:** User info.

**Screenshot 3.**

## 4. Change password
**Method:** PUT  
**URL:** `http://localhost:3000/api/v1/users/[user_id_tu_buoc1]/change-password`  
**Headers:**
- Authorization: `Bearer [token]`
**Body raw JSON:**
```
{
  \"oldPassword\": \"Test123!\",
  \"newPassword\": \"NewPass123!@\"
}
```
**Response:** {\"message\": \"Đổi password thành công\"}

**Screenshot 4.**

## Lưu ý:
- Server phải `npm start` + log \"connected\".
- Key private.pem public.pem phải có.
- Screenshot 4 ảnh nộp + 2pem + git push.
