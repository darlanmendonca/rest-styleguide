## Urls (resources)

Technically, called resources, because each url need provide an access to resource. But simplifying, they are urls :D


If you read a url and dont understand, or if you can't remember in your mind, you probably didn't choose a good name. 
Each url need be clear, to easy understanding. Take care to named your resources, they are the hearth of your API. 

```http
# should do something with users
/users
```

```http
# should do something with a user identified by id 233 
/users/233 
```

```http
# should make something with books of user 223
/users/223/books
```

```http
# should do something with partners
/partners
```

```http
# should do something with products
/products
```

## params (of url)

In many implementations, you will define a url, where part of this is a variable value. We call this as parameter, or just param. 
For e.g., in url /users/233, the value 233 is a value passed to a param. The definitiion of this in code, is something like this:


```
# this url has a param called id
/users/:id
```

## query string

Every time, you will need pass variables to url, but they variables dont be required. Think about pagination by example. In below url, we can get a list of users, but we wish divide list in pages, each page need have to max 10 itens, and we want second page. With query string, we can this make anything like:


```http
/users?page=2&limit=10
```

Note, differente from url params, query strings dont be required in url, you pass when you need. And the advantage of their, is make a resource, in this case, users, have a different behavior on reply us.


see next, [methods](https://github.com/darlanmendonca/rest-styleguide/blob/master/methods.md)