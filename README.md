
# GraphQL Essential Training

This repository contains the excercises of the GraphQL Essential Training on LinkedIn Learning.

## Prerequisite

The following applications needs to be installed:
- Node.js
- Yarn
- MongoDB

## Running project

```
yarn start
```

## Queries and Mutations

### Add new items with mutation

```graphql
mutation {
  createFriend(input: {
    firstName: "Agaton"
    lastName: "Sax"
    gender: MALE
    age: 44
  }){
    id
    firstName
    age
  }
}
```

```graphql
mutation {
  createFriend(input: {
    firstName: "Ture"
    lastName: "Sventon"
    gender: MALE
    age: 40
  }){
    id
    firstName
    age
  }
}
```

### Update items with mutation

```graphql
mutation {
  updateFriend(input: {
    id: "5d128f75f6524f6aab902759"
    firstName: "Ture"
    age: 41
  }) {
    firstName
    lastName
    age
  }
}
```

### Query with alias and fragments

```graphql
query {
  one: getOneFriend(id: "5d128f60f6524f6aab902758") {
    ...friendFragment
  }
  second: getOneFriend(id: "5d128f75f6524f6aab902759") {
    ...friendFragment
  }
}

fragment friendFragment on Friend {
  firstName
  lastName
  age
}
```

### Delete item with mutation

```graphql
mutation {
  deleteFriend(id: "5d128f75f6524f6aab902759")
}
```
