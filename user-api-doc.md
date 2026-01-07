# 🚦 User Management API Reference

Welcome to the Belinda Martina User Management API. This documentation provides all the information required to integrate with our user and authentication services.

> **Base URL:** `https://api.belindamartina.com/v1`

---

## 🔐 Authentication

This API uses **JWT (JSON Web Tokens)** for secure access. Most endpoints require an active session token to be passed in the request header.

### Obtaining a Token
To get an access token, send your credentials to the `/auth/login` endpoint.

### Using the Token
Include the token in the `Authorization` header using the `Bearer` schema:

```http
Authorization: Bearer <your_jwt_token_here>
```

## 👥 User Endpoints

### 1. Register Account
`POST /users/register`

Initialize a new user account. This is a public endpoint.

**Request Body (JSON):**
| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `username` | `string` | Yes | Unique handle (3-20 characters). |
| `email` | `string` | Yes | A valid, unique email address. |
| `password` | `string` | Yes | Minimum 8 characters, alphanumeric. |

**Example Request:**
```json
{
  "username": "belinda_dev",
  "email": "hello@belindamartina.com",
  "password": "SecurePassword123!"
}
```

### 2. User Login
`POST /auth/login`

response (200 OK):
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 86400
}
```

## 🌍 Localization & I18n

This API supports multi-language responses for error messages.
* **Header:** `Accept-Language`
* **Supported Locales:** `en` (English), `id` (Indonesian)

---

## ❌ Error Handling

| Status Code | Meaning | Description |
| :--- | :--- | :--- |
| `200` | Success | Request completed successfully. |
| `401` | Auth Error | Invalid or expired token. |
| `429` | Rate Limit | Too many requests. |

**Error Response Body:**
```json
{
  "error_code": "AUTH_EXPIRED",
  "message": "Sesi Anda telah berakhir. Silakan masuk kembali.",
  "request_id": "req_88291"
}
```

##📏 Rate Limiting
To ensure system stability, we limit requests to:
*100 requests per minute per IP address.
*Exceeding this will return a 429 Too Many Requests status.
