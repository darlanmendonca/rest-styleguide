## Status code - 4xx

Client error (the client is you), anything wrong, not found or not allowed by example

### 400 - Bad Request
<img src="https://http.cat/400" alt="Bad Request" width="500">

Used when client make a request with invalid data, or param. Imagine we have a field called age, that wait for numbers, but user send a string, example:

```http
PUT /users/a57b8a4
```

```js
// request body
{
    name: 'Darlan', 
    age: 'twenty six'
}
```


```http
# response header
Status Code: 400 - Bad Request
```

```js
// response body
{
    message: 'Invalid data',
    errors: [
        age: 'Field age need be a integer number'
    ]
}
```

### 401 - Unauthorized
<img src="https://http.cat/401" alt=Unauthorized" width="500">

Imagine a url that be accessible only to authenticated clients. This method is to say, 'you need be authenticated sir, to access this'.

```http
GET /users/a57b8a4
```


```http
# response header
Status Code: 401 - Unauthorized
```

### 403 - Forbidden
<img src="https://http.cat/403" alt=Forbidden" width="500">

Imagine a user trying get data from another user, but in our application, users just can get your own data. In this case, try access data from another user dont be allow, so this method is to say that.

```http
# trying get data from another users
GET /users/a57b8a3
```


```http
# response header
Status Code: 403 - Forbidden
```

### 404 - Not Found
<img src="https://http.cat/404" alt=Not Found" width="500">

That is classic. Used when the url requested, not be known by server. Not to be confused with data, this status is just for url not found.

```http
# wrong url
GET /userss
```


```http
# response header
Status Code: 404 - Not Found
```

### 409 - Conflict
<img src="https://http.cat/409" alt=Not Found" width="500">

Imagine in our application, the following logic, users have an email, and this email is unique. When a user try signup with an email already used.


```http
POST /users
```

```js
// request body
{
    name: 'Darlan', 
    email: 'me@darlan.com' // email already used by another user
}
```


```http
# response header
Status Code: 409 - Conflict
```

```js
// response body
{
    message: 'Conflict data',
    errors: [
        email: 'Email "me@darlan.com" already used'
    ]
}
```

### 415 - Unsupported Media Type
<img src="https://http.cat/415" alt=Not Found" width="500">

Useful to when a client try upload a file not supported. Example, 

```http
POST /image
```

```js
// request body
{
    file: 'me.mp4', // the supported type is .jpg and .png for example
}
```


```http
# response header
Status Code: 415 - Unsupported Media Type
```

```js
// response body
{
    message: 'They are supported only jpg and png'
}
```