# Truly Rest

The purpose of this repo, is guide developers, to follow (really) a Restful API.

The spec of Rest is:

## Resources

Think in resources, as be our urls. Each url need be so clear, to easy compreension. Every developer, need read and understand what the resource offer as entity.

Are examples:

```http
/users
/users/233
/partners
/products
```

Is recommended avoid abreviations, use good names.

## Resource Params
In many implementations, you will define a resource(url), with static content, and in a part, a variable value. We call this, as parameter. For i.e, in resource /users/233, the value 233 is a value to a param. The definitiion of this in code, is anything like this:

```http
/users/:id
where :id is our param
```

Your resource can has what params you need, but, take careful, basically, resources need be easy to remember, try organize your resources with minimalism.

## Verbs

Verbs are http protocols, and you can think about their, like actions. Below, examples of simple operations, like a CRUD (Create, Read, Update, Delete).

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
```

Exists other verbs, like:

```
OPTIONS /users/ - lets you find out what verbs are supported, e.g. 'is the document deletable'
```

## Status Code

Status code, be a part important from server response. With their, we can check what server understand about our request. Status code can be found in header of request.

Basically, we can classify status codes in groups, where each group be:

```
100, 101 - meta stuff, don't worry about it
2xx - success
3xx - redirection, further actio may be needed
4xx - client error, user screw up
5xx - server error, server screw up
```




