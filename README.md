- Start both dev express server and jsonserver with `npm run concur`

Queries

```
{
  user(id: "43 ") {
    firstName,
    age
  }
}
```

```
{
  user(id: "44 ") {
    firstName,
    age,
    company {id, name, description}
  }
}
```

```
{
  company(id: "1 ") {
    name,
    description
  }
}
```

```
{
  company(id: "2 ") {
    name,
    description ,
    users {id, firstName, company {
      id, name
    } }
  }
}
```

```
{
  c1: company(id: "1 ") {
    name,
    description ,
    users {id, firstName, company {
      id, name
    } }
  }
  c2: company(id: "2 ") {
    name,
    description ,
    users {id, firstName, company {
      id, name
    } }
  }
}
```

```
{
  c1: company(id: "1 ") {
    ...companyDetails
  }
  c2: company(id: "2 ") {
    ...companyDetails
  }
}

fragment companyDetails on Company {
  id
  name
  description
  users { id firstName}
}

----------------- This returns -----------------

{
  "data": {
    "c1": {
      "id": "1",
      "name": "ECorp",
      "description": "Evol Corporation",
      "users": [
        {
          "id": "42",
          "firstName": "maimous"
        },
        {
          "id": "44",
          "firstName": "kangour"
        }
      ]
    },
    "c2": {
      "id": "2",
      "name": "CocaColon",
      "description": "Pablo Escoblabla",
      "users": [
        {
          "id": "43",
          "firstName": "kokokos"
        }
      ]
    }
  }
}
```

```
mutation {
  addUser(firstName: "Another" age:987) {id firstName age}
}

----------------- This returns -----------------

{
  "data": {
    "addUser": {
      "id": "FWa456t",
      "firstName": "Another",
      "age": 987
    }
  }
}
```

```
mutation {
  deleteUser(id:"44") { id }
}

----------------- This returns -----------------

{
  "data": {
    "deleteUser": {
      "id": null
    }
  }
}
```
