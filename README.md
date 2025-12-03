md

# API DOCUMENTATION

## 1. Create user (Create new user - Positive Case)
**TC ID :** TC-API-001  
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Methode :** POST
**Authorization :** Bearer Token 
**Description :** Create a new user with correct data
## Request
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "Nugratest@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 201 Created
- Response JSON :
```json
{
    "id": 8274763,
    "name": "Nugra",
    "email": "Nugratest@gmail.com",
    "gender": "male",
    "status": "active"
}
```

## 2. Create user (Different email - Positive Case)
**TC ID :** TC-API-002 
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user with correct data and different email
## Request 
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "TestQwiik@gmail.com",
    "status": "Active"
}
```
## Expected result
- Status : 201 Created
- Response JSON :
```json
{
    "id": 8274790,
    "name": "Nugra",
    "email": "TestQwiik@gmail.com",
    "gender": "male",
    "status": "active"
}
```

## 3. Create user (Same email - Negative Case)
**TC ID :** TC-API-003
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user with same email
## Request 
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "TestQwiik@gmail.com",
    "status": "Active"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "email",
        "message": "has already been taken"
    }
]
```

## 4. Create user (All field blank - Negative Case)
**TC ID :** TC-API-004
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user, but do not fill in each column
## Request 
```json
{
    "name": "",
    "gender": "",
    "email": "",
    "status": ""
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "email",
        "message": "can't be blank"
    },
    {
        "field": "name",
        "message": "can't be blank"
    },
    {
        "field": "gender",
        "message": "can't be blank, can be male of female"
    },
    {
        "field": "status",
        "message": "can't be blank"
    }
]
```

## 5. Create user (Wrong Token - Negative Case)
**TC ID :** TC-API-005
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user, but i fill the wrong token
## Request 
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "TestQwiik@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 401 Unauthorized
- Response JSON :
```json
{
    "message": "Invalid token"
}
```

## 6. Create user (Wrong email format - Negative Case)
**TC ID :** TC-API-006
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user, but i fill the email with wrong format 
## Request 
```json
{
    "name": "Adam",
    "gender": "Male",
    "email": "nugratest",
    "status": "active"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "email",
        "message": "is invalid"
    }
]
```
## 7. Create user (input status other than active/inactive - Negative Case)
**TC ID :** TC-API-007
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user, but i fill the status other than active/inactive
## Request
```json
{
    "name": "Adam",
    "gender": "Male",
    "email": "agratest@gmail.com",
    "status": "off"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "status",
        "message": "can't be blank"
    }
]
```

## 8. Create user (input gender besides male/female - Negative Case)
**TC ID :** TC-API-008
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user, but i fill the gender besides male/female
## Request
```json
{
    "name": "Adam",
    "gender": "agender",
    "email": "agratest@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "gender",
        "message": "can't be blank, can be male of female"
    }
]
```

## 9. Get list user (List all user - Positive Case)
**TC ID :** TC-API-009
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users
**Method :** GET
**Authorization :** Bearer Token  
**Description :** Get list all user already registered, with correct data
## Request 
- No request body

## Expected result
- Status : 200 OK
- Response JSON :
```json
[
    {
        "id": 8274860,
        "name": "Adam",
        "email": "gratest@gmail.com",
        "gender": "male",
        "status": "inactive"
    },
    {
        "id": 8274790,
        "name": "Nugra",
        "email": "TestQwiik@gmail.com",
        "gender": "male",
        "status": "active"
    },
    {
        "id": 8274763,
        "name": "Nugra",
        "email": "Nugratest@gmail.com",
        "gender": "male",
        "status": "active"
    },
    {
        "id": 8274727,
        "name": "Adam",
        "email": "Bugratest@gmail.com",
        "gender": "male",
        "status": "inactive"
    },
    {
        "id": 8274682,
        "name": "Nugra QA",
        "email": "testerQAQwiik@example.com",
        "gender": "male",
        "status": "active"
    },
    {
        "id": 8260027,
        "name": "Devi Guneta",
        "email": "devi_guneta@spinka.test",
        "gender": "female",
        "status": "active"
    },
    {
        "id": 8260024,
        "name": "Atreyi Kapoor",
        "email": "kapoor_atreyi@johnson.test",
        "gender": "female",
        "status": "inactive"
    },
    {
        "id": 8260023,
        "name": "Birjesh Banerjee",
        "email": "banerjee_birjesh@stiedemann-cole.test",
        "gender": "female",
        "status": "active"
    },
    {
        "id": 8260021,
        "name": "Kannan Gupta",
        "email": "kannan_gupta@stehr.example",
        "gender": "female",
        "status": "inactive"
    },
    {
        "id": 8260020,
        "name": "Ojaswini Chaturvedi",
        "email": "ojaswini_chaturvedi@rowe.example",
        "gender": "female",
        "status": "active"
    }
]
```

## 10. Get user (User detail - Positive Case)
**TC ID :** TC-API-010
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** GET
**Authorization :** Bearer Token  
**Description :** Get user detail, by ID user
## Request 
- No request body
- Path parameter {id} : 8274763

## Expected result
- Status : 200 OK
- Response JSON :
```json
{
    "id": 8274763,
    "name": "Nugra",
    "email": "Nugratest@gmail.com",
    "gender": "male",
    "status": "active"
}
```

## 11. Get list user (List user wrong token  - Negative Case)
**TC ID :** TC-API-011
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/
**Method :** GET
**Authorization :** Bearer Token  
**Description :** Get list user detail, but i fill a wrong token
## Request 
- No request body

## Expected result
- Status : 401 Unauthorized
- Response JSON :
```json
{
    "message": "Invalid token"
}
```

## 12. Get detail user (user detail with wrong ID - Negative Case)
**TC ID :** TC-API-012
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** GET
**Authorization :** Bearer Token  
**Description :** Get user detail, but i fill wrong ID
## Request 
- No request body
- Path parameter {id} : 123

## Expected result
- Status : 404 Not Found
- Response JSON :
```json
{
    "message": "Resource not found"
}
```

## 13. Get detail user (user detail with wrong Token - Negative Case)
**TC ID :** TC-API-013
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** GET
**Authorization :** Bearer Token  
**Description :** Get data user detail, but i fill with wrong token
## Request 
- No request body
- Path parameter {id} : 8274763

## Expected result
- Status : 401 Unauthorized
- Response JSON :
```json
{
    "message": "Invalid token"
}
```

## 14. PUT update user (Update user - Positive Case)
**TC ID :** TC-API-014
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user with correct data 
## Request 
- No request body
```json
{
    "name": "NugraTest",
    "email": "NugraQwiik@example.com",
    "status": "active"
}
```

## Expected result
- Status : 200 OK
- Response JSON :
```json
{
    "email": "NugraQwiik@example.com",
    "name": "NugraTest",
    "status": "active",
    "id": 8274763,
    "gender": "male"
}
```

## 15. PUT update user (Update user - Positive Case)
**TC ID :** TC-API-015
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, with correct data 
## Request 
- No request body
```json
{
    "name": "NugraTest",
    "email": "NugraQwiik@example.com",
    "status": "active"
}
```

## Expected result
- Status : 200 OK
- Response JSON :
```json
{
    "email": "NugraQwiik@example.com",
    "name": "NugraTest",
    "status": "active",
    "id": 8274763,
    "gender": "male"
}
```

## 16. PUT update user (Update user with wrong ID - Negative Case)
**TC ID :** TC-API-016
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, with correct data 
## Request 
- No request body
```json
{
    "name": "NugraTest",
    "email": "NugraQwiik@example.com",
    "status": "active"
}
```

## Expected result
- Status : 404 Not Found
- Response JSON :
```json
{
    "message": "Resource not found"
}
```

## 17. PUT update user (Update user but all field is blank/empty - Negative Case)
**TC ID :** TC-API-017
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, but i fill empty all field 
## Request 
- No request body
```json
{
    "name": "",
    "gender": "",
    "email": "",
    "status": ""
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "email",
        "message": "can't be blank"
    },
    {
        "field": "name",
        "message": "can't be blank"
    },
    {
        "field": "gender",
        "message": "can't be blank, can be male of female"
    },
    {
        "field": "status",
        "message": "can't be blank"
    }
]
```

## 18. PUT update user (Update user but wrong token - Negative Case)
**TC ID :** TC-API-018
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, but i fill a wrong token
## Request 
- No request body
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "ASQAQwiik@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 401 Unauthorized
- Response JSON :
```json
{
    "message": "Invalid token"
}
```

## 19. PUT update user (Update user but empty token - Negative Case)
**TC ID :** TC-API-019
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, but im not fill the token
## Request 
- No request body
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "ASQAQwiik@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 404 Not Found
- Response JSON :
```json
{
    "message": "Resource not found"
}
```

## 20. PUT update user (Update user but email is not format - Negative Case)
**TC ID :** TC-API-020
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, but i fill the email is not accord with format
## Request 
- No request body
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "ASQAQwiik",
    "status": "active"
}
```
## Expected result
- Status : 404 Not Found
- Response JSON :
```json
[
    {
        "field": "email",
        "message": "is invalid"
    }
]
```

## 21. PUT update user (Update user but status active/not active - Negative Case)
**TC ID :** TC-API-021
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token  
**Description :** Update data user, but i fill the status besides active or not active
## Request 
- No request body
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "ASQAQwiik@gmail.com",
    "status": "off"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "status",
        "message": "can't be blank"
    }
]
```

## 22. Put user (update gender besides male/female - Negative Case)
**TC ID :** TC-API-022
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** PUT
**Authorization :** Bearer Token 
**Description :** Update gender user, but i fill the gender besides male/female
## Request
```json
{
    "name": "Adam",
    "gender": "transgender",
    "email": "iaugratest12@gmail.com",
    "status": "active"
}
```
## Expected result
- Status : 422 Unprocessable Entity
- Response JSON :
```json
[
    {
        "field": "gender",
        "message": "can't be blank, can be male of female"
    }
]
```

## 23. Delete user (Delete user with match ID - Positive Case)
**TC ID :** TC-API-023
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** DELETE
**Authorization :** Bearer Token 
**Description :** Delete user, with match ID
## Request 
- No request body
- Path parameter {id} : 8274763

## Expected result
- Status : 204 No Content
- Response JSON : 

## 24. Delete user (Delete user with wrong ID - Negative Case)
**TC ID :** TC-API-024
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** DELETE
**Authorization :** Bearer Token 
**Description :** Delete user, but i fill with wrong ID
## Request 
- No request body
- Path parameter {id} : 8274763

## Expected result
- Status : 204 No Content
- Response JSON : 
```json
{
    "message": "Resource not found"
}
```

## 25. Delete user (Delete user with wrong token - Negative Case)
**TC ID :** TC-API-025
**Hosting :** https://gorest.co.in
**Endpoint :** /public/v2/users/{id}
**Method :** DELETE
**Authorization :** Bearer Token 
**Description :** Delete user, but i fill with wrong ID
## Request 
- No request body
- Path parameter {id} : 8274763

## Expected result
- Status : 401 Unauthorized
- Response JSON : 
```json
{
    "message": "Invalid token"
}
```
