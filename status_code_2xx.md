## Status code - 2xx

Success status, server understand and will make what you want

### 200 - OK
<img src="https://http.cat/200" alt="200 - OK" width="500">

Used to when your request was understood, and you will get what you requested.

```http
GET /users/a57b8a4
```


```http
# response header
Status Code: 200 - OK
```

```js
// response body
{
    name: 'Darlan', 
    id: 'a57b8a4'
}
```

### 201 - Created
<img src="https://http.cat/201" alt="200 - Created" width="500">

Used after to tell if your request create anything in the server. Example below, try create a user

```http
POST /users
```

```js
// request body
{
    name: 'Darlan'
}
```

```http
# response header
Status Code: 201 - Created
```

```js
// response body
{
    id: 'a57b8a4'
}
```

### 204 - Not content
<img src="https://http.cat/204" alt="204 - No content" width="500">

The server understood what you requested, but not have data to be returned. Example, not have users yet.

```http
GET /users
```


```http
# response header
Status Code: 204 - No content
```

```js
// response body
[]
```

### 206 - Partial content
<img src="https://http.cat/206" alt="206 - Partial content" width="500">

Let's suppose our lists by default display max 10 items for response. As we know that there are more elements to be displayed? This status code, is fot that.

```http
GET /users
```


```http
# response header
Status Code: 206 - Partial content
```

```js
// response body
[
    {
        id: 'a57b8a4',
        name: 'Darlan'
    },
    // nine items max 
]
```