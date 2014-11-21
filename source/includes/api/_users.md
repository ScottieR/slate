# Users

## Get All Users

```ruby
#follow authentication steps to get the "access" object

 access.get("/api/users").parsed
```


> The above command returns JSON structured like this:

```json
{"users":[
	{
		"id":108,
		"name":"Helen Amgdighggcag",
		"blurb":null,
		"gender":"female",
		"location":null,
		"latitude":null,
		"longitude":null,
		"followers_count":0,
		"followed_users_count":0,
		"saved_places_count":0,
		"saved_plans_count":0,
		"invitation_limit":5,
		"created_at":"2014-01-10T05:34:04.055Z",
		"updated_at":"2014-04-08T02:49:46.485Z",
		"profile_img":"/tmp/assets/users/108/original/picture.?1396925385",
		"_links":{
			"self":{"href":"/api/users/108"},
			"notification_settings":{"href":"/api/source_urls?place=108"},
			"saved_places":{"href":"/api/saved_places?user=108"},
			"saved_plans":{"href":"/api/saved_plans?user=108"},
			"tips":{"href":"/api/tips?user=108"},
			"reservations":{"href":"/api/reservations?user=108"},
			"tops_lists":{"href":"/api/tops_lists?user=108"},
			"followed_users":{"href":"/api/relationships?follower=108"},
			"followers":{"href":"/api/relationships?followed=108"},
			"traveling_plans":{"href":"/api/travelers?user=108"},
			"plans_as_owner":{"href":"/api/travelers?user=108\u0026owner=true"},
			"plans_as_editor":{"href":"/api/travelers?user=108\u0026editor=true"},
			"plans_as_viewer":{"href":"/api/travelers?user=108\u0026editor=false"},
			"places_been":{"href":"/api/saved_places?user=108\u0026been=true"},
			"places_approved":{"href":"/api/saved_places?user=108\u0026approve=true"},
			"places_disapproved":{"href":"/api/saved_places?user=108\u0026approve=false"},
			"places_want_to_go":{"href":"/api/saved_places?user=108\u0026been=false"}
		}
	}
]}
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

## Create User

```shell
curl --data "user[name]=new%20User&user[email]=example@example.com&user[password]=password&user[password_confirmation]=password&user[invitation_token]=038239529075" https://travelenvy.com/api/tips/1215?access_token=your_token
```

```ruby
 access.post("/api/users?user[name]=new%20User&user[email]=example@example.com&user[password]=password&user[password_confirmation]=password&user[invitation_token]=038239529075").parsed
```

This endpoint creates a new user.

### HTTP Request

`GET https://travelenvy.com/api/users?<PARAMS>`

### URL Parameters

Parameter | Description
--------- | -----------
name | The name (first & last) of the new user
email | A valid email address for the user
password | min 6 characters
password_confirmation | re-entered password
invitation_token | the invitation token for the user, appended to their invitation link sent via email

### Response

Status | Description
------ | -----------
201 | Successfully created
403 | Unauthorized: user is already signed in and is not an admin