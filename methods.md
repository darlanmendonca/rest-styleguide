## method (action, verbs)

In rest, is called verbs. Verbs just be http methods. They offer a way to reuse a resource, in different ways. 
Think in methods like the definition of action what you want do with resource.

We use all the time, these methods:

- GET
- POST
- PUT
- DELETE
- OPTIONS

Let's see in more details each of these:

### GET
This method is used to get data from server, without make changes in server. For example, get details about an user, or retrieve a list of users.

###### Example of list of users

```http
GET /users
```

```js
// response body
[
    {
        name: 'Darlan', 
        id: 'a57b8a4'
    },
    {
        name: 'Clara', 
        id: 'an97a94'
    },
    {
        name: 'Bob', 
        id: 'n23sb23'
    },
]
```

##### Example of get data from a single user:

```http
GET /users/a57b8a4
```

```js
// response body
{
    name: 'Darlan', 
    id: 'a57b8a4'
}
```


### POST
Used to create new things in/with the server. By example, create a new user, add a new item to a entity, create a user token, etc.

Example of request to create a new user:

```http
POST /users
```

```js
// request body
{
	name: 'Darlan'
}
```

### PUT
Used to change anything in entity. Example, we want change name of user:

```http
PUT /users/a57b8a4
```

```js
// request body
{
	name: 'Darlan Mendonça'
}
```

### DELETE
That is simple, is used to delete completely the data from server. In any cases, the server can make another think, instead delete. They can by example, disallow the entity, adding a key active=false for example. Independent of what server will make, the method what we use, need be the same. Below a example to disallow/delete a user:

```http
DELETE /users/a57b8a4
```

#### OPTIONS
In your application, you probaly have differentes actions to entities. Users can be deleted, but comments not, for example. To see what you can do with a resource, just make a request with method OPTIONS, they will return what you can do with resource. Example:

```http
OPTIONS /users
````

see next, [status code](https://github.com/darlanmendonca/rest-styleguide/blob/master/status_code.md)