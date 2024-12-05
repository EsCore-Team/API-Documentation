# API-Documentation
This repository contains comprehensive documentation for the EsCore Application, including a complete guide to using the API

## User Register   
**POST**: `https://escore-app.et.r.appspot.com/api/register`  

**Request Body**
```json
{
    "fullName": "string",
    "email": "string",
    "password": "string"
}
```

**Response Success**
```json
{
    "error": false,
    "message": "User registered successfully!"
}
```

**Response Failed**

```json
{ 
    "error": true,
    "message": "Internal server error!",
}
```

## User Login   
**POST**: `https://escore-app.et.r.appspot.com/api/login`  

**Request Body**
```json
{
    "email": "string",
    "password": "string"
}
```

**Response Success**
```json
{
    "error": false,
    "message": "Success logged in!",
    "loginResult": {
        "userId": "string",
        "email": "string"
        "fullName": "string"
        "token": "string"
    }
}
```

**Response Failed**

```json
{ 
    "error": true,
    "message": "Internal server error!",
}
```

## History Prediction   
**GET**: `https://escore-app.et.r.appspot.com/api/history/:email`  

**Response Success**
```json
{
    "error": false,
    "message": "History predictions retrieved successfully!",
    "email": "string"
    "predictions": [
        {
          "id": "string",
          "title": "string",
          "essay": "string",
          "createdAt": "2024-12-05T14:56:13.606Z",
          "predicted_result": {
            "score": "string",
            "suggestion": "string"
          }
        }
    ]
}
```

**Response Failed**

```json
{ 
    "error": true,
    "message": "Internal server error!",
}
```

## Essay Prediction   
**POST**: `https://backend-ml-g4eq4oioha-et.a.run.app/predict`  

**Request Body**
```json
{
    "user_email": "string",
    "title": "string",
    "essay": "string"
}
```

**Response Success**
```json
{
    "error": false,
    "message": "Essay has been predicted!",
    "user_email": "string",
    "result": {
        "title": "string",
        "essay": "string"
        "createdAt": "timestamp"
        "predicted_result": {
            "score": "string"
            "suggestion": "string"
        }
    }
}
```

**Response Failed**

```json
{ 
    "error": true,
    "message": "An error occurred while processing the request!",
}
```



