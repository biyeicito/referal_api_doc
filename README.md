# Referral API Documentation

## Base URL
```
https://api.example.com/v1/referrals
```

---

## Endpoints

### 1. Create a referral code
**POST** `/create-code`

#### Request Body
```json
{
  "codeName": "string",
  "commission": "number"
}
```

#### Response
```json
{
  "success": true,
  "codeId": "string",
  "message": "Referral code created successfully."
}
```

---

### 2. Delete a referral code
**DELETE** `/delete-code/{codeId}`

#### Path Parameters
- `codeId` (string): ID of the code to delete.

#### Response
```json
{
  "success": true,
  "message": "Referral code deleted successfully."
}
```

---

### 3. Edit a referral code
**PUT** `/edit-code/{codeId}`

#### Path Parameters
- `codeId` (string): ID of the code to edit.

#### Request Body
```json
{
  "codeName": "string",
  "commission": "number"
}
```

#### Response
```json
{
  "success": true,
  "message": "Referral code updated successfully."
}
```

---

### 4. Add a user to a referral code
**POST** `/add-user`

#### Request Body
```json
{
  "codeId": "string",
  "userId": "string"
}
```

#### Response
```json
{
  "success": true,
  "message": "User successfully added to the referral code."
}
```

---

### 5. Edit a user in a referral code
**PUT** `/edit-user`

#### Request Body
```json
{
  "userId": "string",
  "newCodeId": "string"
}
```

#### Response
```json
{
  "success": true,
  "message": "User successfully transferred to the new referral code."
}
```

---

### 6. Remove a user from a referral code and move to default
**DELETE** `/remove-user`

#### Request Body
```json
{
  "userId": "string"
}
```

#### Response
```json
{
  "success": true,
  "message": "User removed from the code and moved to the default code."
}
```

---

### 7. Get referral code details
**GET** `/get-code/{codeId}`

#### Path Parameters
- `codeId` (string): ID of the code to retrieve.

#### Response
```json
{
  "success": true,
  "code": {
    "codeName": "string",
    "commission": "number",
    "owner": "string",
    "creationDate": "YYYY-MM-DD",
    "users": [
      {
        "userId": "string",
        "name": "string"
      }
    ]
  }
}
```

---

