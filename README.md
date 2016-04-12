# Truly Rest

The purpose of this repo, is guide developers, to follow (really) a Restful API.

The spec of Rest is:

## Resources (urls)

Think in resources, as our urls. Each url need be clear, to easy understanding. Take care to named your resources, they are entities, and a hearth of your API.

Are examples:

```http
/users
/users/233
/users/223/books
/partners
/products
```

## Resource Params

In many implementations, you will define a resource(url), where part of this is a variable value. We call this parameter, or just param. For i.e, in resource /users/233, the value 233 is a value from param id. The definitiion of this in code, is anything like this:

```
/users/:id
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

## Status Code 2xx (Success)

Like title say, 2xx group, report to you, an action successful. Following, you see details about each status.

##### 200 - Ok

Your request are completely successfull, and you will receive data what you want. I.e.

```http
GET /users/123

response
200
{"id": "123", "firstname": "Darlan", "lastname": "Mendonça"}
```

##### 201 - Created

Ok, sucess, and we can create what you requested. In body of response, you will receive too the id of new resource created. 

```http
POST /users

response
201
{"id": "123"}
```

##### 204 - No Content

We understand what you requested, but dont have data in a response to you. I.e.

```http
GET /users

response
204
[]
```

##### 206 - Partial Content

You see in response, just part of an collection.

```http
GET /users?limit=2

response
206
[
  {"id": "123", "firstname": "Darlan", "lastname: 'Mendonça"}
  {"id": "124", "firstname": "Clara", "lastname": "Lúcia"}
]
```


