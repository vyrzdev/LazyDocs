# REST Endpoints for the Access Control WEB API.

### List Roles
Required Permissions:
access_control.role | list

Endpoint:
`/access_control/role/list`

Expected Response:
```json
{
    "roles": [
        {
            "id": "dnd7nsa9023ja29fbms9y4kkl2",
            "name": "foo",
            "pretty_name": "Foo Role"
        },
        {
            "id": "foo",
            "name": "foo2",
            "pretty_name": "Foo Role 2."
        }
    ]
}
```

### Get Role Data
Required Permission:
access_control.role | view

Endpoint:
`/access_control/role/get/<role_id>`

Expected Response:
```json
{
   "name": "foo",
   "pretty_name": "Foo Role"
}
```

### List Permissions
Required Permission:
access_control.permission | list

Endpoint:
`/access_control/permission/list`

URL Parameters:
```
role_id ~ Should be the ID of the RoleRegistration pertaining to the role you want to filter by.
```

Expected Response:
```json
{
    "permissions": [
        {
            "id": "weoihreoihcwfohfeo32",
            "action": "access",
            "resource": {
                "id": "sdfhfuwhfouweouh324124",
                "name": "foo.foo"
            }
        },
        "and so on..."
    ]
}
```


