# VolunteerGo API Documentation

Welcome to the API documentation for **VolunteerGo**, a platform that helps manage social activities and volunteers.

---

##  Base URL

https://api.volunteergo.com/v1


##  Authentication

* API uses token-based authentication.
* Login to receive a token, then include it in the `Authorization` header:

```
Authorization: Bearer your_token_here
```

---

## 📘 Endpoints

### 1. Login

```
POST /login
```

**Request Body:**

```json
{
  "email": "user@example.com",
  "password": "your_password"
}
```

**Response:**

```json
{
  "token": "jwt_token_here",
  "user": {
    "id": 1,
    "role": "volunteer"
  }
}
```

---

### 2. Get All Volunteers

```
GET /volunteers
```

**Response:**

```json
[
  {
    "id": 1,
    "name": "Anna",
    "email": "anna@example.com"
  },
  {
    "id": 2,
    "name": "Budi",
    "email": "budi@example.com"
  }
]
```

---

### 3. Get Volunteer by ID

```
GET /volunteers/{id}
```

**Response:**

```json
{
  "id": 1,
  "name": "Anna",
  "email": "anna@example.com",
  "joined_date": "2024-01-12"
}
```

---

### 4. Get Activities

```
GET /activities
```

**Response:**

```json
[
  {
    "id": 101,
    "title": "Beach Cleanup",
    "date": "2025-08-10"
  },
  {
    "id": 102,
    "title": "Tree Planting",
    "date": "2025-08-15"
  }
]
```

---

### 5. Create Activity

```
POST /activities
```

**Request Body:**

```json
{
  "title": "Food Donation",
  "date": "2025-08-20"
}
```

**Response:**

```json
{
  "id": 103,
  "message": "Activity created successfully."
}
```

---

### 6. Register as Volunteer

```
POST /register
```

**Request Body:**

```json
{
  "name": "New Volunteer",
  "email": "new@example.com",
  "password": "secure_password"
}
```

**Response:**

```json
{
  "id": 3,
  "message": "Registration successful."
}
```

---

## Error Responses

| Code | Message               |
| ---- | --------------------- |
| 400  | Bad Request           |
| 401  | Unauthorized          |
| 404  | Not Found             |
| 500  | Internal Server Error |

---

## Try It Out

Use Postman or curl to test endpoints.

**Curl Example:**

```
curl -X GET https://api.volunteergo.com/v1/activities \
-H "Authorization: Bearer your_token_here"
```

