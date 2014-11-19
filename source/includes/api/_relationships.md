#Relationships

##Get all Relationships

```shell
```

```ruby
```

```json
{ relationships: [
  {
    "id":2,
    "follower_id":1,
    "followed_id":4,
    "created_at":"2013-10-07T18:09:10.533Z",
    "updated_at":"2013-10-07T18:09:10.533Z",
    "follower_name":"Scottie Ryan",
    "followed_name":"Mackenzie Willms",
    "_links":{
      "self":"/api/relationships/2",
      "follower":"/api/users?user=2",
      "followed":"/api/users?user=2"
    }
  },
  {
    "id":3,
    "follower_id":1,
    "followed_id":5,
    "created_at":"2013-10-07T18:09:10.535Z",
    "updated_at":"2013-10-07T18:09:10.535Z",
    "follower_name":"Scottie Ryan",
    "followed_name":"Brian Cummings",
    "_links":{
      "self":"/api/relationships/3",
      "follower":"/api/users?user=3",
      "followed":"/api/users?user=3"
    }
  }
]}
```

This endpoint returns all relationships (user who are following other users)

### HTTP Request

`GET https://travelenvy.com/api/relationships`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
relationships | false | A comma separated list of relationship ids by which to filter.  If not present, returns all relationships.
follower | false | Filters relationships by the given user id.  Returns relationships where the given user id is the follower
followed | false | Filters relationships by the given user id.  Returns relationships where the given user id is the followed user

### Response
Parameter | Description
--------- | -----------
id | Relationship ID
follower_id | ID of the user following
followed_id | ID of the user being followed
created_at | datetime relationship created
updated_at | datetime relationship last updated
follower_name | Name of the user following
followed_name | Name of the user being followed
_links | array of hrefs that point to associated objects (here: "self" relationship object, "follower" user object, "followed" user object)

## Get a specific Relationship

### HTTP Request
`GET https://travelenvy.com/api/relationships/2`

### Response
Same as above when requesting all relationships

## Create a Relationship

The endpoint to create a new relationship

<aside class="notice">Users can only create relationships where they are the follower.  The follower_id is set automatically based on the current_user token. </aside>

### HTTP Request
`POST https://travelenvy.com/api/relationships`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
followed_id | true | The user id of the user to follow

### Response

Status Code | Case
----------- | ----
201 | Successfully created

## Destroy a Relationship

The endpoint to destroy a specific relationship

<aside class="warning">Only admins and users who are the follower in a relationship can destroy it.</aside>

### HTTP Request
`DELETE https://travelenvy.com/api/relationships/2`

### Response

Status Code | Case
----------- | ----
403 | User is not authorized (the user is not the follower or an admin)
204 | Successfully deleted