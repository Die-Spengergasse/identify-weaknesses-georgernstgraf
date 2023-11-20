[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/OPdcYQCn)
# spgldap2rest

expose ldap auth (simple bind) via a rest api. A permanentely logged in service
user searches for the entered userid in the ldap and tries a simple bind with
the found DN and the provided password. The Rest API answers with either HTTP
200 resp. 401 (unauthorized) and some details in the json answer body.

## Example success

```javascript
POST http://localhost:3000/verify
Content-Type: application/json

{
   "user": "kuderwom",
   "passwd": "Pre?ag3"
}
```

```javascript
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "dn": "CN=kuderwom,ou=bla,ou=blub,DC=example,DC=domain",
  "description": "220657",
  "mail": "5BKIF",
  "auth": true
}
```
