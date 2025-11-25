# Sample API Documentation  
A mock API documentation written in Markdown to demonstrate structure, clarity, and technical writing style.

---

# 🚀 Overview
The **Sample User API** allows clients to register users, log in, and retrieve profiles.  
This documentation includes endpoints, request formats, responses, and error handling.

Base URL:
https://api.example.com/v1


---

# 📌 Endpoints

## 1. Register User  
`POST /users/register`

### Request Body
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "123456"
}
```

### Successful Response
```json
{
  "status": "success",
  "message": "User registered successfully."
}
```

## 2. Login
`POST /users/login`

### Request Body
```json
{
  "email": "john@example.com",
  "password": "123456"
}
```

### Successful Response
```json
{
  "token": "abc123xyz"
}
```

## 3. Get User Profile
`GET /users/me`
#### Requires authentication token.
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com"
}
```

---

# 🔧 Error Handling
### Common error response :

```json
{
  "status": "error",
  "message": "Invalid email or password."
}
```
---
# 📑 Notes
- Use HTTPS for all requests.
- Token must be included in Authorization header.
- This document is for demonstration and writing quality only.
