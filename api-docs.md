# Students API Documentation

**Base URL:**
"https://69e8ec7b55d62f34797a1249.mockapi.io/api/v1"

**Resource:** users

This API manages student records for Infodev.

## Authentication

This is a mock API created using MockAPI, so no authentication is required.

## Data Model
### Student Object

| Field | Type | Description |
| ----- | ---- | ----------- |
| id    | string | Unique identifier (auto-generated) |
| name  | string | Name of the student |
| email | string | Email address | 
| course | string | Course enrolled |
| createdAt | string | Record creation timestamp

## Endpoints Overview

| Method | Endpoint | Description |
| ------ | -------- | ----------- |
| GET | /users | Fetch all students |
| GET | /users/{id} | Fetch single student |
| POST | /users | Create a new student |
| PUT | /users/{id} | Replace student data |
| PATCH | /users/{id} | Update student partially |
| DELETE | /users/{id} | Delete a student |

## API Endpoints

### Get All Students

**GET** /users

**Description**
Fetches a list of all students.

**Request**
GET /users

#### Response (200 OK)
```json 
[
 {
        "createdAt": "2026-04-22T02:40:12.457Z",
        "name": "Ethel Torphy",
        "avatar": "https://avatars.githubusercontent.com/u/26301444",
        "id": "1"
 }
]
```

### Get Single Student

**GET** /users/{id}

**Description**
Fetch a specific student by ID.

**Path Parameters**

| Parameter | Type | Required | Description |
| ----------| ---- | -------- |------------ |
| id | string | Yes | Student ID | 


#### Request
GET /users/1

#### Response (200 OK)
```json
 {
        "createdAt": "2026-04-22T02:40:12.457Z",
        "name": "Ethel Torphy",
        "avatar": "https://avatars.githubusercontent.com/u/26301444",
        "id": "1"
 }
```

### Create Student

**POST** /users

**Description**
Creates a new student record.

#### Request Body
```json
{
    "name":"Rahul Awasthi",
    "avatar":"https://avatars.githubusercontent.com/u/26301444"
}
```

#### Response (201 Created)
```json
{
    "createdAt": "2026-04-22T05:03:36.686Z",
    "name": "Rahul Awasthi",
    "avatar": "https://avatars.githubusercontent.com/u/26301444",
    "id": "41"
}
```

### Update Student (Full Update)

**PUT** /users/{id}

**Description**
Replaces the entire student record.

#### Request
PUT /users/41

#### Request Body
```json
{
    "name":"Garima Verma",
    "avatar":"https://avatars.githubusercontent.com/u/26301444"
}
```

#### Response (200 OK)
```json
{
    "createdAt": "2026-04-22T05:03:36.686Z",
    "name": "Garima Verma",
    "avatar": "https://avatars.githubusercontent.com/u/26301444",
    "id": "41"
}
```

### Update Student (Partial Update)

**PATCH** /users/{id}

**Description**
Updates specific fields of a student.

#### Request
PATCH /users/41

#### Request Body
```json
{
    "name":"Sonali Kumari"
}
```

#### Response (200 OK)
```json
{
    "createdAt": "2026-04-22T05:03:36.686Z",
    "name": "Sonali Kumari",
    "avatar": "https://avatars.githubusercontent.com/u/26301444",
    "id": "41"
}
```

### Delete Student

**DELETE** /users/{id}

**Description**
Deletes a student record.

#### Request
DELETE /users/41

#### Response (200 OK)
```json
{
    "createdAt": "2026-04-22T05:03:36.686Z",
    "name": "Sonali Kumari",
    "avatar": "https://avatars.githubusercontent.com/u/26301444",
    "id": "41"
}
```

## Error Handling

| Status Code | Description |
| ----------- | ----------- |
| 400 | Bad Request| 
| 404 | Student Not Found | 
| 500 | Internal Server Error |


**Example Error Response**
```json
{
  "error": "Student not found"
}
```

## Testing the API

You can test all endpoints using:
1. Postman
2. Browser (for GET requests)

## Notes
1. This API currently contains 40 student records.
2. IDs are automatically generated.
3. Since it's a mock API, data persistence may vary depending on configuration.

## Conclusion

This Students API provides complete CRUD functionality for managing student data in Infodev. 
