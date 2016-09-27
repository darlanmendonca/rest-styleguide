## status code

Status code, be a important part from server response. With their, we can check what server understand about our request. Status code can be found in header of request.

Basically, we can classify status codes in groups, where each group be:

```
2xx - success status, server understand and will make what you want
3xx - redirection, further action may be needed
4xx - client error (the client is your), anything wrong, not found or not allowed by example.
5xx - an error occur in server
```

I love this reference about http status code, [https://http.cat/](https://http.cat/), and I suggest you to see it.

### 200 - OK
Used to when your request was understood, and you will get what you requested.

```http
GET /users/a57b8a4
```

<img src="https://http.cat/200" alt="200 - OK" width="500">

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

<img src="https://http.cat/201" alt="200 - Created" width="500">

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
The server understood what you requested, but not have data to be returned. Example, not have users yet.

```http
GET /users
```

<img src="https://http.cat/204" alt="204 - No content" width="500">

```http
# response header
Status Code: 204 - No content
```

```js
// response body
[]
```

### 206 - Partial content
Let's suppose our lists by default display max 10 items for response. As we know that there are more elements to be displayed? This status code, is fot that.

```http
GET /users
```

<img src="https://http.cat/206" alt="206 - Partial content" width="500">

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

