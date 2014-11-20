# Plans

## Get all Plans

```ruby
```

```shell
```

```json
```

This endpoint returns all plans (ie itineraries)

<aside class="warning">If you're not using an administrator API key, note that some plans will return 403 Forbidden if they are hidden for admins or their owners only.</aside>

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

This endpoint retrieves a specific plan.

### HTTP Request

`GET https://travelenvy.com/api/plans/<ID>`

<aside class="warning">If you're not using an administrator API key, note that some plans will return 403 Forbidden if they are hidden for admins or their owners only.</aside>


## Update a Specific Plan

### HTTP Request

`PUT https://travelenvy.com/api/plans/<id>`

<aside class="warning">If you're not using an administrator API key, note that this will return 403 Forbidden unless the current user is an editor of this plan.</aside>

### Query Parameters

### Response


## Delete a Specific Plan

### HTTP Request

`DELETE https://travelenvy.com/api/plans/<id>`

<aside class="warning">If you're not using an administrator API key, note that plans not owned by the current user will return 403 Forbidden.</aside>

### Query Parameters

### Response