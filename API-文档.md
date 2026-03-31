# API 文档

## 接口规范

- 基础 URL: `https://api.example.com/v1`
- 认证方式: Bearer Token
- 数据格式: JSON

## 认证

### 获取 Token

```http
POST /auth/login
Content-Type: application/json

{
  "username": "your_username",
  "password": "your_password"
}
```

**响应示例：**

```json
{
  "code": 200,
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIs...",
    "expires_in": 3600
  }
}
```

## 用户接口

### 获取用户信息

```http
GET /users/{id}
Authorization: Bearer {token}
```

**响应示例：**

```json
{
  "code": 200,
  "data": {
    "id": 1,
    "username": "john_doe",
    "email": "john@example.com"
  }
}
```

### 创建用户

```http
POST /users
Authorization: Bearer {token}
Content-Type: application/json

{
  "username": "new_user",
  "email": "new@example.com",
  "password": "secure_password"
}
```

## 错误码

| 错误码 | 说明 |
|--------|------|
| 400 | 请求参数错误 |
| 401 | 未授权 |
| 403 | 禁止访问 |
| 404 | 资源不存在 |
| 500 | 服务器内部错误 |
