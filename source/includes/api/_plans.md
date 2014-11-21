# Plans

## Get all Plans

> To retrieve all plans, use the following code:

```ruby
access.get("/api/plans").parsed
```

```shell
curl https://travelenvy.com/api/plans?access_token=your_token
```

> The above code returns the following json:

```json
{"plans":[
	{
		"id":181,
		"title":"Honeymoon in Kenya \u0026 the Seychelles",
		"days":3,
		"summary":"",
		"people":3,
		"countries":"Kenya \u0026 Usa",
		"country_codes":"us gb",
		"total_cost":"0.0",
		"saves_count":2,
		"featured":false,
		"publish":true,
		"sightseeing":false,
		"food":false,
		"romance":false,
		"family":false,
		"art_design":false,
		"outdoors":false,
		"partying":false,
		"relaxing":false,
		"shopping":false,
		"big_group":false,
		"event":false,
		"music":false,
		"hidden_gems":false,
		"authentic_local":false,
		"created_at":"2013-11-10T23:20:53.186Z",
		"updated_at":"2014-11-15T18:43:07.672Z",
		"start_date":null,
		"end_date":null,
		"start_loc":"",
		"end_loc":"",
		"creator_id":1,
		"cover_photo_url":"https://media-cache-ak0.pinimg.com/736x/d3/f9/5a/d3f95a8a7efede55cf4e0808403fa07b.jpg",
		"stops":{
			"0":{"city":"Santa Monica","nights":1}
		},
		"_links":{
			"self":{"href":"/api/plans/181"},
			"saving_users":{"href":"/api/saved_plans?plan=181"},
			"plan_places":{"href":"/api/plan_places?plan=181"},
			"travelers":{"href":"/api/travelers?plan=181"}
	},{
		...
	}
]}
```

This endpoint returns all plans (ie itineraries)

<aside class="warning">If you're not using an administrator API key, note that some plans will return 403 Forbidden if they are hidden for admins or their owners only.  If the user is not a traveler on the plan, certain private fields will also not be returned (start/end location, dates) </aside>

### HTTP Request

`GET https://travelenvy.com/api/plans`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
plans | false | A comma separated list of plan ids to return

### Response

Attribute | Description
--------- | -----------
id | Plan ID
creator_id | user that created this plan
title | Title of the plan
days | Number of days in the plan
summary | brief description / summary of the plan
people | Number of people traveling on the plan
countries | countries visited in the plan
country_codes | 2-letter iso codes of countries visited in the plan
total_cost | Sum of estimated costs of the plan
saves_count | number of users saving the plan to their passport
featured | boolean as to whether the plan is marked as featured
publish | boolean, whether the plan is marked as a draft or published
sightseeing | boolean, if this plan focuses on sightseeing
food | boolean, if this plan focuses on food
romance | boolean, if this plan focuses on romance
family | boolean, if this plan focuses family
art_design | boolean, if this plan focuses on art and design
outdoors | boolean, if this plan focuses on outdoors
partying | boolean, if this plan focuses on partying
relaxing | boolean, if this plan focuses on relaxing
shopping | boolean, if this plan focuses on shopping
big_group | boolean, if this plan is focused around a big group
event | boolean, if this plan is focused around an event
music | boolean, if this plan focuses on music
hidden_gems | boolean, if this plan focuses on hidden gems
authentic_local | boolean, if this plan focuses on authentic local spots
created_at | datetime this plan was created
updated_at | datetime this plan was last updated
start_date | (private) start date of the plan, private to travelers on the plan
end_date | (private) end date of the plan, private to travelers on the plan
start_location | (private) start location of the plan, private to travelers on the plan
end_location | (private) end location of the plan, private to travelers on the plan
cover_photo_url | src of the main image for this plan    
stops | A hash of the stops in this plan.  Ordered chronologically, with the city name and nights spent at each stop
_links | An array of href links to retrieve the associated objects of this plan ("self" the plan's href, "saving_users" all users saving this plan, "plan_places" the items featured in this plan, "travelers" the users traveling on this plan )


## Get a Specific Plan

> To retrieve a specific plans, use the following code:

```ruby
access.get("/api/plans/183").parsed
```

```shell
curl https://travelenvy.com/api/plans/183?access_token=your_token
```

> The above code returns the following json:

```json

{"plan":{
	"id":183,
	"title":"Lorem ipsum",
	"days":10,
	"summary":null,
	"people":4,
	"countries":null,
	"country_codes":"",
	"total_cost":"0.0",
	"saves_count":0,
	"featured":false,
	"publish":true,
	"sightseeing":false,
	"food":false,
	"romance":false,
	"family":false,
	"art_design":false,
	"outdoors":false,
	"partying":false,
	"relaxing":false,
	"shopping":false,
	"big_group":false,
	"event":false,
	"music":false,
	"hidden_gems":false,
	"authentic_local":false,
	"created_at":"2014-11-21T01:04:28.087Z",
	"updated_at":"2014-11-21T01:04:29.635Z",
	"start_date":null,
	"end_date":null,
	"start_loc":null,
	"end_loc":null,
	"creator_id":499,
	"cover_photo_url":"http://media-cache-ak0.pinimg.com/236x/a6/01/d4/a601d41865bb1693e2633ebca49846a0.jpg",
	"stops":{},
	"_links":{
		"self":{"href":"/api/plans/183"},
		"saving_users":{"href":"/api/saved_plans?plan=183"},
		"plan_places":{"href":"/api/plan_places?plan=183"},
		"travelers":{"href":"/api/travelers?plan=183"}
	},
	"travelers":[
		{
			"id":79,
			"user_id":1,
			"plan_id":183,
			"can_edit":true,
			"status":null,
			"created_at":"2014-05-28T05:27:12.019Z",
			"updated_at":"2014-10-21T19:43:12.036Z"
			,"owner":true
		}
	],
	"plan_places":[
		{
			"id":358,
			"plan_id":183,
			"sortable_type":"TransportLeg",
			"sortable_id":143,
			"position":16,
			"day":1,
			"time":null,
			"chosen_category":null,
			"description":null,
			"note":null,
			"is_private":false,
			"cost":null,
			"cost_multiplier":"per person",
			"currency":"USD",
			"est_price_cents":null,
			"est_price_currency":"USD",
			"booked":null,
			"start_img":null,
			"created_at":"2013-11-15T00:07:39.530Z",
			"updated_at":"2013-11-15T00:07:39.530Z",
			"item":{
				"id":143,
				"plan_id":183,
				"transport_type":"flight",
				"origin_code":"OCH",
				"origin_address":null,
				"origin_city":"",
				"dest_code":null,
				"dest_address":null,
				"dest_city":"Miami Beach, FL",
				"provider":null,
				"duration":null,
				"price":null,
				"month":null,
				"dep_date":null,
				"arrive_date":null,
				"dep_time":null,
				"arrive_time":null,
				"link_to_book":null,
				"booked":null,
				"created_at":"2013-11-15T00:07:39.510Z",
				"updated_at":"2013-11-15T00:07:41.925Z",
				"currency":"USD",
				"dep_timezone":null,
				"dep_utc_offset":null,
				"arrive_timezone":null,
				"arrive_utc_offset":null
			},
			"nights":null,
			"_links":{
				"self": { href: "/api/plan_places/358" },
				"tip": { href: "/api/tips?plan_place=358" },
				"photo": { href: "/api/photos/" }
			},
			"tip":null,
			"photo":null
		},{
			"id":886,
			"plan_id":183,
			"sortable_type":"Place",
			"sortable_id":270,
			"position":48,
			"day":null,
			"time":null,
			"chosen_category":null,
			"description":null,
			"note":null,
			"is_private":false,
			"cost":null,
			"cost_multiplier":null,
			"currency":"USD",
			"est_price_cents":5000,
			"est_price_currency":"USD",
			"booked":false,
			"start_img":null,
			"created_at":"2014-04-07T16:12:52.275Z",
			"updated_at":"2014-05-12T20:24:04.749Z",
			"item":{
				"id":270,
				"name":"The Purple Pig",
				"category":"restaurant",
				"address":"500 N Michigan Ave, Chicago, IL, United States",
				"city_state":"Chicago",
				"country":"us",
				"zip":"60608",
				"phone":"+1 312-464-1744",
				"email":null,
				"website":"http://thepurplepigchicago.com/",
				"added_by":1,
				"created_at":"2014-03-28T23:48:47.813Z",
				"updated_at":"2014-08-16T17:18:45.775Z",
				"price":"2.0",
				"lat":"41.89111",
				"lng":"-87.62447",
				"airports":"CHI, MDW",
				"train_station":null,
				"photos_count":10,
				"continent_id":1,
				"saves_count":1,
				"featured":false,
				"most_pop_photo_id":1629,
				"neighborhood":null,
				"summary":null
			},
			"nights":null,
			"_links":{
				"self":"/api/plan_places/886",
				"tip":"/api/tips?plan_place=886",
				"photo":"/api/photos/"
			},
			"tip":null,
			"photo":null
		}
	]}
}

```

This endpoint retrieves a specific plan.

### HTTP Request

`GET https://travelenvy.com/api/plans/<ID>`

<aside class="warning">If you're not using an administrator API key, note that some plans will return 403 Forbidden if they are hidden for admins or their owners only.  If the user is not a traveler on the plan, certain private fields will also not be returned (start/end location, dates) </aside>

### Response

Same as the index "Get all Plans" response, with the addition of an array of travelers, and plan_places (grouped by day, ordered by position) and their corresponding items. 


## Create a Plan

> To create a plans, use the following code:

```ruby
access.post("/api/plans?plan[title]=New%20Plan").parsed
```

```shell
curl https://travelenvy.com/api/plans?plan[title]=New%20Plan&access_token=your_token
```

This endpoint creates a new plan for the current user.

### HTTP Request

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
title | true | Title of the plan
days | false |  Number of days in the plan
summary | false | brief description / summary of the plan
people | false | Number of people traveling on the plan
countries | false | countries visited in the plan
start_date | false | (private) start date of the plan, private to travelers on the plan
end_date | false | (private) end date of the plan, private to travelers on the plan
start_location | false | (private) start location of the plan, private to travelers on the plan
end_location | false | (private) end location of the plan, private to travelers on the plan
cover_photo | src of the main image for this plan.  Either use this or "main_photo" to upload
main_photo | photo file to upload as the main image for this plan.  Either use this or "cover_photo"
sightseeing | false | boolean, if this plan focuses on sightseeing
food | false | boolean, if this plan focuses on food
romance | false | boolean, if this plan focuses on romance
family | false | boolean, if this plan focuses family
art_design | false | boolean, if this plan focuses on art and design
outdoors | false | boolean, if this plan focuses on outdoors
partying | false | boolean, if this plan focuses on partying
relaxing | false | boolean, if this plan focuses on relaxing
shopping | false | boolean, if this plan focuses on shopping
big_group | false | boolean, if this plan is focused around a big group
event | false | boolean, if this plan is focused around an event
music | false | boolean, if this plan focuses on music
hidden_gems | false | boolean, if this plan focuses on hidden gems
authentic_local | false | boolean, if this plan focuses on authentic local spots

### Response

Status | Description
------ | -----------
201 | Successfully Created

## Update a Specific Plan

> To update a plans, use the following code:

```ruby
access.put("/api/plans/25?plan[title]=New%20Plan").parsed
```

```shell
curl https://travelenvy.com/api/plans/25?plan[title]=New%20Plan&access_token=your_token
```

### HTTP Request

`PUT https://travelenvy.com/api/plans/<ID>?<PARAMS>`

<aside class="warning">If you're not using an administrator API key, note that this will return 403 Forbidden unless the current user is an editor of this plan.</aside>

### URL Parameters

Look at creating a plan to see what attributes can be updated.

<aside class="warning">Note that non-admin users can only update plans that they have edit permissions for. A NEW COPY OF THE PLAN IS CREATED and saved to the current_user if they update a plan for which they don't have edit rights. </aside>

### Response

Status | Description
------ | -----------
204 | Successfully updated
201 | A new plan was successfully created, saved to the current user, and updated with the given params

## Delete a Specific Plan

> To delete a plan, use the following code:

```ruby
access.delete("/api/plans/25").parsed
```

```shell
curl -X DELETE https://travelenvy.com/api/plans/25?access_token=your_token
```

### HTTP Request

`DELETE https://travelenvy.com/api/plans/<ID>`

<aside class="warning">If you're not using an administrator API key, note that plans not owned by the current user will return 403 Forbidden.</aside>

Status | Description
------ | -----------
204 | Successfully deleted
403 | Unauthorized: the user did not create this plan and therefore cannot delete it