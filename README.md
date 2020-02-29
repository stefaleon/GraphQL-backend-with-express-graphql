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
