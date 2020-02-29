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
