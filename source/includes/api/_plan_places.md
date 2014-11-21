# Plan Places

##Get a list of Plan Places

> To Get a list of plan_places use the following code:

```shell
  curl https://travelenvy.com/api/plan_places?access_token=your_token
```

```ruby
access.get("/api/plan_places").parsed
```

> The above command returns JSON structured like this:

```json
{"plan_places":[
  {
    "id":658,
    "plan_id":235,
    "sortable_type":"Place",
    "sortable_id":101,
    "position":16,
    "day":1,
    "time":null,
    "nights":1,
    "chosen_category":"site",
    "description":null,
    "note":null,
    "is_private":false,
    "cost":null,
    "cost_multiplier":"per person",
    "currency":"USD",
    "est_price_cents":null,
    "est_price_currency":"USD",
    "booked":false,
    "start_img":644,
    "created_at":"2014-01-22T04:20:17.783Z",
    "updated_at":"2014-01-22T04:20:17.783Z",
    "item":{
      "id":101,
      "name":"Hutton Hotel",
      "category":"lodging",
      "address":"1808 West End Avenue, Nashville, TN, United States",
      "city_state":"Nashville",
      "country":"us",
      "zip":"37203",
      "phone":"+1 615-340-9333",
      "email":null,
      "website":"http://www.huttonhotel.com/",
      "added_by":1,
      "created_at":"2013-11-13T03:03:44.159Z",
      "updated_at":"2014-11-14T20:27:50.021Z",
      "price":null,
      "lat":"36.15287",
      "lng":"-86.797082",
      "airports":"Nashville International Airport,Smyrna/Rutherford County Airport Authority,MBT,",
      "train_station":null,
      "photos_count":18,
      "continent_id":null,
      "saves_count":4,
      "featured":false,
      "most_pop_photo_id":644,
      "neighborhood":null,
      "summary":null
    },
    "_links":{
      "self":"/api/plan_places/658",
      "tip":"/api/tips?plan_place=658",
      "photo":"/api/photos/644"
    },
    "tip":{
      "id":224,
      "user_id":1,
      "place_id":101,
      "plan_place_id":658,
      "content":"Admin tip",
      "created_at":"2014-01-22T21:34:50.076Z",
      "updated_at":"2014-01-22T21:35:09.196Z"
      "_links":{
        "self":{"href":"/api/photos/644"},
        "place":{"href":"/api/places/101"},
        "plan_place":{"href":"/api/plan_places/658"},
        "user":{"href":"/api/users/1"}
      }
    },
    "photo":{
      "id":644,
      "place_id":101,
      "src":"/assets/plans/644/medium/Hutton_2BHotel.?1395708306",
      "source":"Google",
      "added_by":1,
      "alt":null,
      "_links":{
        "self":{"href":"/api/photos/644"},
        "place":{"href":"/api/places/101"}
      }
    }
  },{
    "id":452,
    "plan_id":202,
    "sortable_type":"TransportLeg",
    "sortable_id":195,
    "position":16,
    "day":1,
    "time":null,
    "nights":null,
    "chosen_category":null,
    "description":null,
    "note":null,
    "is_private":false,
    "cost":null,
    "cost_multiplier":"total",
    "currency":"USD",
    "est_price_cents":5000,
    "est_price_currency":"USD",
    "booked":false,
    "start_img":null,
    "created_at":"2013-11-25T19:08:56.456Z",
    "updated_at":"2014-05-12T20:24:04.528Z",
    "item":{
      "id":195,
      "plan_id":202,
      "transport_type":"car",
      "origin_code":null,
      "origin_address":null,
      "origin_city":null,
      "dest_code":null,
      "dest_address":null,
      "dest_city":null,
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
      "created_at":"2013-11-25T19:08:56.392Z",
      "updated_at":"2013-11-25T19:08:56.392Z",
      "currency":"USD",
      "dep_timezone":null,
      "dep_utc_offset":null,
      "arrive_timezone":null,
      "arrive_utc_offset":null
    },
    "tip_id":null,
    "photo_id":null
  },{
    "id":431,
    "plan_id":202,
    "sortable_type":"Note",
    "sortable_id":1,
    "position":16,
    "day":1,
    "time":null,
    "nights":1,
    "chosen_category":null,
    "description":null,
    "note":null,
    "is_private":false,
    "cost":null,
    "cost_multiplier":"total",
    "currency":"USD",
    "est_price_cents":null,
    "est_price_currency":"USD",
    "booked":false,
    "start_img":null,
    "created_at":"2013-11-22T03:30:25.551Z",
    "updated_at":"2013-11-22T03:30:25.551Z",
    "item":{
      "id":1,
      "title":"Visit Museums",
      "content":"Head to the Louvre, checking out the street vendors along the Seine on the way",
      "user_id":null,
      "plan_id":null,
      "created_at":"2013-11-22T03:30:25.520Z",
      "updated_at":"2013-11-22T03:34:48.613Z",
      "photo_file_name":null,
      "photo_content_type":null,
      "photo_file_size":null,
      "photo_updated_at":
      null
    },
    "tip_id":null,
    "photo_id":null
  }
]}
```

This endpoints retrieves all plan places (eg: items listed in plans).

###HTTP Request

`GET https://travelenvy.com/api/plan_places`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
plan_places | false | A comma separated list of plan place ids with which to filter the results (ex: "plan_places=48,201")
plan | false | An id for a specific plan for which to pull plan places
type | false | Filters result set by object type.  Valid options are "Place", "TransportLeg", and "Note"
place | false | An id for a specific place to get which plans it is feauted in.  Returns both the plan_place and plan objects

### Response

Attribute | Description
--------- | -----------
id | PlanPlace ID
plan_id | Plan ID
sortable_type | type of plan_place object can be "Place", "TransportLeg", or "Note"
sortable_id | id of the plan_place object
position | position within the day that of this plan_place
day | day in which this plan_place appears
time | start time associated with this plan_place
nights | number of nights spent at this plan_place (only applicable for sortable_type="Place" with place category of "lodging") 
chosen_category | category of the plan_place.  Only applicable for sortable_type="Place".  Defaults to place's category (lodging, restaurant, etc.  See place section)
description | Short lead-in text describing what doing at the Place.  Only applicable for sortable_type="Place".  Ex: "Eat at".
is_private | boolean whether or not this plan_place is marked as private (ie only travelers on this plan can see it).
cost | actual cost of plan_place (cost will be estimated otherwise)
currency | actual cost currency
cost_multiplier | "total", "per person", or "per night".  Defaults based on sortable_type if has not been set.
est_price_cents | estimated price of this plan_place (comes from aggregated Place data and other estimates)
est_price_currency | estimated price currency (from aggregated data)
booked | boolean, whether owner of plan has booked this plan_place
start_img | ID of photo to use for this plan_place
created_at | datetime plan_place was created
updated_at | datetime plan_place was last updated
item[ ] | array of item attributes.  See Place, TransportLeg and Note parameters for reference.
_links[ ] | array of associated items.  Here includes links to associated: Tip, Photo
tip[ ] | array of the associated tip attributes.  See Tip section for details
photo[ ] | array of the associated photo attributes.  See Photo section for details

##Get a Specific Plan Item (aka a plan_place)

This endpoint retrieves a specific plan place (ie item within a plan).

<aside class="warning">If you're not using an administrator API key, note that some plan places will return 403 Forbidden if they are private to admins or the plan's owners and travelers only.</aside>

###HTTP Request

`GET https://travelenvy.com/api/plan_places/<ID>`

## Add an Item to a Plan (aka creating a plan_place)
 You can add a Place, TransportLeg or Note to a Plan.  See the following sections for specifics on creating each.

## Add a Place to a Plan

To add a place to a plan, create a plan_place as shown in Create a Plan Item with sortable_type="Place".  Make sure to provide either sortable_id (which can be a TravelEnvy ID or Google Places reference ID) OR sortable_name.

###HTTP Request

`POST https://travelenvy.com/api/plan_places?<PARAMS>`

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
plan_place[sortable_type] | true | set to "Place" to add a place
plan_place[sortable_id] | false | provide the travelenvy ID or Google reference code of the place, or just provide the name below if not yet on TravelEvny and no google place ID found.
sortable_name | false | The stringified name of the place to be added.  Will be used to create a new Place on TravelEnvy if no Place ID given.  Either this or sortable_id are required to correctly add a Place to a Plan.
plan_place[day] | false | The day number (1...n) to which this item should be added. If > plan's days, plan's day count increases to this value.  If nil, item is added to the "options to consider" for the plan
plan_place[position] | false | The position (1...n) within the plan day that this item should appear.  If left blank, item will be added to the end of the day.
plan_place[time] | false | Time at which to add the item
plan_place[description] | false | Brief lead-in description for the item, which when displayed will be followed by the place name.  For example, "Eat at".
plan_place[booked] | false | whether the plan owner has booked this item yet
plan_place[cost] | false | the actual cost associated with this item
plan_place[cost_multiplier] | false | How to tally this cost.  Valid values are "total", "per night", and "per person".  If not provide, default is based on the place's type & category (for example, a Place of category "lodging" defaults to "per night", while a "restaurant" defaults to "per person")
plan_place[start_img] | false | The ID of the photo to show for this place.  If nil, a default photo will be chosen
plan_place[chosen_category] | false | If the item is a Place, the user can change its categorization (for instance if the Place is "lodging" but within the plan the user is going for drinks, category can be set to "bar" for this plan item)
plan_place[nights] | false | Number of nights staying.  This is only used when chosen_category is "lodging".
plan_place[private] | false | Boolean that determines whether users not traveling on this plan can see this item.  Default is false (publicly viewable)
closest | false | ID of the plan_place to insert this item after.  Use instead of the "position" parameter if easier (ex: in drag and drop sorting).
plan_place[tip][content] | false | New tip that should be created for this item and shown in this plan.  Will also show on corresponding Place's page.

<aside class="notice">See "Adding an Item to a Plan" for all additional parameter options.  Note: Users can only create plan_places for plans which they are an editor.  </aside>

### Response

Status Code | Case
----------- | ----
201 | Successfully created
403 | Unauthorized: current user is not an editor of this plan


## Adding a Transportation Leg to a Plan

{"transport_legs":[
  {
    "id":195,
    "plan_id":202,
    "transport_type":"car",
    "origin_code":null,
    "origin_address":null,
    "origin_city":null,
    "dest_code":null,
    "dest_address":null,
    "dest_city":null,
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
    "created_at":"2013-11-25T19:08:56.392Z",
    "updated_at":"2013-11-25T19:08:56.392Z",
    "currency":"USD",
    "dep_timezone":null,
    "dep_utc_offset":null,
    "arrive_timezone":null,
    "arrive_utc_offset":null
  }
]}

### HTTP Request

`POST https://travelenvy.com/api/plan_places?<PARAMS>`

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
plan_place[sortable_type] | true | set to "TransportLeg" to add a transportation leg
plan_place[sortable_id] | false | provide the ID of the transport_leg (it must have previously been created, see "Creating a TransportLeg")
plan_place[day] | false | The day number (1...n) to which this item should be added. If > plan's days, plan's day count increases to this value.  If nil, item is added to the "options to consider" for the plan
plan_place[position] | false | The position (1...n) within the plan day that this item should appear.  If left blank, item will be added to the end of the day.
plan_place[time] | false | Time at which to add the item
plan_place[description] | false | Brief lead-in description for the item, which when displayed will be followed by the place name.  For example, "Eat at".
plan_place[booked] | false | whether the plan owner has booked this item yet
plan_place[cost] | false | the actual cost associated with this item
plan_place[cost_multiplier] | false | How to tally this cost.  Valid values are "total", "per night", and "per person".  If not provide, default is "per person" for tranaportation legs
plan_place[private] | false | Boolean that determines whether users not traveling on this plan can see this item.  Default is false (publicly viewable)
closest | false | ID of the plan_place to insert this item after.  Use instead of the "position" parameter if easier (ex: in drag and drop sorting).

### Response

Status Code | Case
----------- | ----
201 | Successfully created
403 | Unauthorized: current user is not an editor of this plan

## Adding a Note to a Plan

{"notes":[
  {
    "id":1,
    "title":"Visit Museums",
    "content":"Head to the Louvre, checking out the street vendors along the Seine on the way",
    "user_id":null,
    "plan_id":null,
    "created_at":"2013-11-22T03:30:25.520Z",
    "updated_at":"2013-11-22T03:34:48.613Z",
    "photo_file_name":null,
    "photo_content_type":null,
    "photo_file_size":null,
    "photo_updated_at":null
  }
]}


### HTTP Request

`POST https://travelenvy.com/api/plan_places?<PARAMS>`

### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
plan_place[sortable_type] | true | set to "Note" to add a note
plan_place[sortable_id] | false | provide the ID of the note object to be added (it must have previously been created, see "Creating a Note")
plan_place[day] | false | The day number (1...n) to which this item should be added. If > plan's days, plan's day count increases to this value.  If nil, item is added to the "options to consider" for the plan
plan_place[position] | false | The position (1...n) within the plan day that this item should appear.  If left blank, item will be added to the end of the day.
plan_place[time] | false | Time at which to add the item
plan_place[description] | false | Brief lead-in description for the item, which when displayed will be followed by the place name.  For example, "Eat at".
plan_place[booked] | false | whether the plan owner has booked this item yet
plan_place[cost] | false | the actual cost associated with this item
plan_place[cost_multiplier] | false | How to tally this cost.  Valid values are "total", "per night", and "per person".  If not provide, default is based on the place's type & category (for example, a Place of category "lodging" defaults to "per night", while a "restaurant" defaults to "per person")
plan_place[private] | false | Boolean that determines whether users not traveling on this plan can see this item.  Default is false (publicly viewable)
closest | false | ID of the plan_place to insert this item after.  Use instead of the "position" parameter if easier (ex: in drag and drop sorting).

### Response

Status Code | Case
----------- | ----
201 | Successfully created
403 | Unauthorized: current user is not an editor of this plan

## Delete an Item from a Plan (aka deleting a plan_place)

### HTTP Request

`DELETE https://travelenvy.com/api/plan_places/<ID>`

### Response

Status Code | Case
----------- | ----
204 | Successfully deleted
403 | Unauthorized: current user is not an editor of this plan
