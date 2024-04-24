# GraphQL
https://graphql.org/learn/

## Introduction to GraphQL
GraphQL is made up of two parts:
* A query language used to get information from servers
* A program that runs on a server (called a "GraphQL service") that provides data to GraphQL clients

A GraphQL service is made up of types and fields that specify the data available, and a set of functions for each field on each type that specify how to get the data.

([Example Source](https://graphql.org/learn/))

Data Structure (Types & Fields):
```graphql
type Query {
  me: User
}

type User {
  id: ID
  name: String
}
```

Data Access (Functions):
```graphql
function Query_me(request) {
  return request.auth.user
}

function User_name(user) {
  return user.getName()
}
```

This allows GraphQL to be used independently of the database or language used on the server.