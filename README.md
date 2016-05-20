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

Verbs are the http methods. You can think in their like actions.
Actions because their define what you want do to when you request a resource. Below you find what each method is used in Restful API's

```
GET - just read data, for e.g, when you get a list of users, or data from a single user

POST - used to create new things, for e.g, to create a new user, or add a new item to a entity

PATCH - used to update partial data from a entity, e.g., update the lastname of an user, or just a email.

PUT - used to update all data from a entity

DELETE - to remove a entire entity, for e.g., remove the user from system.

OPTIONS - return what methods are supported by resource, e.g. 'is the document deletable'

```

And below, complete examples, of requests:

```http
return a list of users
GET /users

return data of a single user
GET /users/:id

create a user
POST /users

update partial data of a user
PATCH /users/:id

update entire data of a user
PUT /users/:id

delete a user
DELETE /users/:id

check what methods are supported to a resource
OPTIONS /users
OPTIONS /users/:id
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


