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

##### 200 - OK
Used to when your request is understanding, and you will receive what you request.

```http
GET /users/a57b8a4
```

```http
# response header
Status Code: 200 - OK
```

[200 - OK](https://http.cat/200)

```js
// response body
{
    name: 'Darlan', 
    id: 'a57b8a4'
}
```