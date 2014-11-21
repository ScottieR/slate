#Tips

##Get all Tips

> To get all tips, use the following code:

```shell
  curl https://travelenvy.com/api/tips?access_token=your_token
```

```ruby
access.get("/api/tips").parsed
```

> The above returns the following json:

```json
{"tips":[
  {
    "id":1216,
    "user_id":1,
    "place_id":98,
    "plan_place_id":null,
    "content":"go before the lines get long around 9pm",
    "created_at":"2014-11-20T19:53:27.804Z",
    "updated_at":"2014-11-20T19:53:27.804Z"
  },{
    "id":1215,
    "user_id":12,
    "place_id":95,
    "plan_place_id":1468,
    "content":"great for #burgers",
    "created_at":"2014-11-15T18:44:13.411Z",
    "updated_at":"2014-11-15T18:44:13.411Z"
  }
]}
```

This endpoint returns all tips

### HTTP Request

`GET https://travelenvy.com/api/tips`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
tips | false | A comma separated list of tip ids by which to filter.  If not present, returns all tips.
user | false | Filters tips by the given user id.  Returns tips the user created.
place | false | Filters tips by the given place id.  Returns tips for the place.
plan_place | false | Filters tips by the given plan_place id.  Returns the plan_place specific tip.

### Response

Attribute | Description
--------- | -----------
id | Tip ID
user_id | ID of the user who created the tip
place_id | ID of the place the tip corresponds to
plan_place_id | ID of the specific plan_place the tip corresponds to
content | tip tip's content
created_at | datetime tip created
updated_at | datetime tip last updated
_links | array of hrefs that point to associated objects (here: "self", "place", "plan_place", and "user")

## Get a specific Tip

> To get a specific tip, use the following code:

```shell
  curl https://travelenvy.com/api/tips?id=1216&access_token=your_token
```

```ruby
access.get("/api/tips/1216").parsed
```

> The above returns the following json:

```json
{"tip": {
  "id":1216,
  "user_id":1,
  "place_id":98,
  "plan_place_id":null,
  "content":"go before the lines get long around 9pm",
  "created_at":"2014-11-20T19:53:27.804Z",
  "updated_at":"2014-11-20T19:53:27.804Z"
}}
```

### HTTP Request
`GET https://travelenvy.com/api/tips/<ID>`

### Response
Same as above when requesting all tips

## Create a Tip

> To create a tip, use the following code:

```shell
  curl --data "tip[place_id]=98&tip[content]=great%20burger" https://travelenvy.com/api/tips?access_token=your_token
```

```ruby
access.post("/api/tips?tip[place_id]=98&tip[content]=great%20burger").parsed
```

The endpoint to create a new tip

### HTTP Request
`POST https://travelenvy.com/api/tips?<PARAMS>`

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
tip[place_id] | true | The id of the place the tip refers to
tip[plan_place_id] | false | The id of the plan_place the tip is attached to
tip[content] | false | The content of the tip.  If empty, the tip will not be created but no error is thrown.

### Response

Status | Description
------ | -----------
201 | Successfully created

## Update a Tip

> To update a tip, use the following code:

```shell
  curl --data "tip[content]=an%20even%20better%20burger" https://travelenvy.com/api/tips/1215?access_token=your_token
```

```ruby
access.post("/api/tips/1215?tip[place_id]=98&tip[content]=great%20burger").parsed
```

The endpoint to update a tip

### HTTP Request
`PUT https://travelenvy.com/api/tips/<ID>?<PARAMS>`

<aside class="warning">Only admins and users who created the tip can update it.</aside>

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
tip[place_id] | true | The id of the place the tip refers to
tip[plan_place_id] | false | The id of the plan_place the tip is attached to
tip[content] | false | The content of the tip.  If empty, the tip will not be created but no error is thrown.

### Response

Status Code | Case
----------- | ----
204 | Successfully updated
403 | Unauthorized: the current user did not create this tip

## Destroy a Tip

> To delete a tip, use the following code:

```shell
  
```

```ruby
access.delete("/api/tips/1215")
```

The endpoint to destroy a specific tip

<aside class="warning">Only admins and users who created the tip can destroy it.</aside>

### HTTP Request
`DELETE https://travelenvy.com/api/tips/<ID>`

### Response

Status Code | Case
----------- | ----
403 | User is not authorized (the user did not create the tip or is not an admin)
204 | Successfully deleted