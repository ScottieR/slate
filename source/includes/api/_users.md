# Users

## Get All Users

```ruby
#follow authentication steps to get the "access" object

 access.get("/api/users").parsed
```


> The above command returns JSON structured like this:

```json
[

]
```

This endpoint retrieves all users.

### HTTP Request

`GET https://travelenvy.com/api/users`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
users | false | A comma separated list of user ids by which to filter (ex: "users=1,5,7").  If not present, returns all users.
tastemakers | false | Boolean that if set to true, will return only users who are tastemakers.
query | false | A string to users by (name, location, interests)
near | false | Returns users (who have provided their primary location) within 20 miles of the given location (valid entries include city, lat/long, etc)


## Get a Specific User

```ruby
#follow authentication steps to get the "access" object

 access.get("/api/places/95").parsed
```

> The above command returns JSON structured like this:

```json
{
  TODO
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://travelenvy.com/api/user/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve
