md

# API DOCUMENTATION

--

## 1. Create user (Positive Case)
**TC ID :** TC-API-001  
**Hosting :** https://gorest.co.in
**Endpoint :** '/public/v2/users'
**Methode :** POST
**Authorization :** Bearer Token 
**Description :** Create a new user with correct data
## Request body
```json
{
  "name": "Adam",
  "gender": "Male",
  "email": "iaugratest@gmail.com",
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

## 2. Create user (Different email Positive Case)
**TC ID :** TC-API-002 
**Hosting :** https://gorest.co.in
**Endpoint :** '/public/v2/users'
**Method :** POST
**Authorization :** Bearer Token  
**Description :** Create a new user with correct data and different email
## Request body
```json
{
    "name": "Nugra",
    "gender": "Male",
    "email": "TestQwiik@gmail.com",
    "status": "Active"
}
## Expected result
- Status : 201 Created
- Response JSON :

{
    "id": 8274790,
    "name": "Nugra",
    "email": "TestQwiik@gmail.com",
    "gender": "male",
    "status": "active"
}
