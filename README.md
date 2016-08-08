# Rest

The purpose of this repo, is guide developers, to follow (really) a Restful API.

The spec of Rest is:

## Resources (urls)

Think in resources, as our urls. Each url need be clear, to easy understanding. Take care to named your resources, they are the hearth of your API. 

If you read a url and dont understand, or if you dont can remember in your mind, you probably didn't choose a good name.

Are examples of resources:

```js
'/users' // should do something with users
'/users/233' // should do something with a user identified by id 233 
'/users/223/books' // should make something with books of user 223
'/partners' // should do something with partners
'/products' // should do something with products
```

## Params

In many implementations, you will define a resource(url), where part of this is a variable value. We call this parameter, or just param. For e.g., in resource /users/233, the value 233 is a value passed to a param id. The definitiion of this in code, is something like this:

```js
'/users/:id' // this url has a param called id
```

## Verbs(actions)

Verbs just be http methods. You can think of them as 'actions'.
Actions, because these define what you want to do. Below you find what each method is used in Restful API's


#### GET
Just read data, used for read list of single object. for e.g, when you want retrieve a list of users, or data from a single user.

Example of get list of users:

```http
GET /users
```

```js
// response 
[
    {name: 'Lorem', id: a57b8a4},
    {name: 'Lero', id: an97a94},
    {name: 'Leroy', id: n23sb23},
];
```

Example of get single user:

```http
GET /users/an97a94
```

```js
// response 
{
    name: 'Lero', 
    id: an97a94
},
```


#### POST
Used to create new things, e.g, create a new user, or add a new item to a entity, e.g., add a new book to a user

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


```js
'PATCH' // used to update partial data from a entity, e.g., update the lastname of an user, or just a email.

'PUT' // used to update all data from a entity

'DELETE' // to remove a entire entity, for e.g., remove the user from system.

'OPTIONS' // return what methods are supported by resource, e.g. 'is the document deletable?'
```

And below, complete examples, of requests:

```js
'GET /users' // return a list of users

'GET /users/:id' // return data of a single user

'POST /users' // create a user

'PATCH /users/:id' // update partial data of a user

'PUT /users/:id' // update entire data of a user

'DELETE /users/:id' // delete a user

// check what methods are supported to a resource
'OPTIONS /users'
'OPTIONS /users/:id'
```

## Status Code

Status code, be a important part from server response. With their, we can check what server understand about our request. Status code can be found in header of request.

Basically, we can classify status codes in groups, where each group be:

```
100, 101 - meta stuff, don't worry about it
2xx - success
3xx - redirection, further action may be needed
4xx - client error, user screw up
5xx - server error, server screw up
```

[See more](https://github.com/darlanmendonca/rest/wiki/Status-Code-2xx)


