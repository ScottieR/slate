# Places

##Get All Places

```ruby
access.get("/api/places").parsed

```shell
curl "http://travelenvy.com/api/places"
  -H "Authorization: [ACCESS_TOKEN]"
```

> The above command returns JSON structured like this:

```json
{"places"=>[
  {
    "id"=>401, 
    "added_by"=>1, 
    "name"=>"The London EDITION", 
    "summary"=>"New hotspot hotel on the edge of London's SoHo neighborhood", 
    "category"=>"lodging", 
    "address"=>"10 Berners Street, London, United Kingdom", 
    "city_state"=>"London", 
    "country"=>"gb", 
    "zip"=>nil, 
    "neighborhood"=>"SoHo", 
    "lat"=>"51.516773", 
    "lng"=>"-0.136334", 
    "email"=>nil, 
    "phone"=>"+44 20 7781 0000", 
    "website"=>"http://www.edition-hotels.marriott.com/london", 
    "price"=>"477.00",
    "currency"=>"USD", 
    "airports"=>"Gatwick Airport,Stansted Airport,London Luton Airport,", 
    "saves_count"=>1, 
    "photos_count"=>10, 
    "continent_id"=>6, 
    "featured"=>false, 
    "created_at"=>"2014-06-27T03:39:36.165Z", 
    "updated_at"=>"2014-07-24T19:18:33.162Z", 
    "most_pop_photo_id"=>2763, 
    "main_photo_url"=>"/tmp/assets/photos/2763/original/520.?1403840443", 
    "saving_user_ids"=>[1], 
    "photo_ids"=>[2763, 2762, 2761, 2760, 2759, 2758, 2757, 2756, 2755, 2754], 
    "source_url_ids"=>[], 
    "plan_ids"=>[255], 
    "tops_list_ids"=>[], 
    "tip_ids"=>[]
  },
  {
    "id"=>477, 
    "added_by"=>1, 
    "name"=>"Bestia", 
    "summary"=>nil, 
    "category"=>"restaurant", 
    "address"=>"2121 E 7th Pl, Los Angeles, CA 90021, United States", 
    "city_state"=>"Los Angeles, California", 
    "country"=>"us", 
    "zip"=>"90021", 
    "neighborhood"=>"Downtown", 
    "lat"=>"34.033717", 
    "lng"=>"-118.229281", 
    "email"=>nil, 
    "phone"=>"+1 213-514-5724", 
    "website"=>"http://www.bestiala.com/", 
    "airports"=>nil, 
    "saves_count"=>1, 
    "photos_count"=>11, 
    "continent_id"=>nil, 
    "featured"=>false, 
    "created_at"=>"2014-10-13T19:25:15.952Z", 
    "updated_at"=>"2014-11-11T00:46:44.670Z", 
    "most_pop_photo_id"=>3449, 
    "price"=>nil, 
    "currency"=>"USD", 
    "main_photo_url"=>"/tmp/assets/photos/3449/original/DSC_0083.jpg?1414519897", 
    "_links":{
        "self":{"href":"/api/places/196"},
        "most_pop_photo":{"href":"/api/photos/1031"},
        "saving_users":{"href":"/api/saved_places?place=196"},
        "photos":{"href":"/api/photos?place=196"},
        "source_urls":{"href":"/api/source_urls?place=196"},
        "tops_lists":{"href":"/api/tops_lists?place=196"},
        "plans":{"href":"/api/plan_places?place=196"},
        "tips":{"href":"/api/tips?place=196"}
    }
]}
```

This endpoints retrieves all places from the TravelEnvy database (ie lodging, restaurants, activities, sites, stores...).

### HTTP Request

`GET https://travelenvy.com/api/places`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
places[ ] | false | An arrays of IDs to filter the place list with, optional
query | false | A search term to query all places. Will return places with similar names, addresses, category and tags as the given query
country | false | 2-letter iso country code, with which to filter places.  Reference: http://www.worldatlas.com/aatlas/ctycodes.htm
near | false | Location as a string (address, city, latitude and longitude, etc).  Will return places within 20 miles of the given location.

<aside class="warning">If you're not using an administrator API key, the "near" parameter will not be available due to 3rd party account quotas.  Set up your own "near" functionality using [Google's Places API](https://developers.google.com/maps/documentation/javascript/places) or the [Geocoder gem](http://www.rubygeocoder.com/).</aside>

### Response
Parameter | Description
--------- | -----------
id | Place ID
added_by | ID of user that first uploaded this place
name | Place's name
summary | One line summary of place, created by TravelEnvy admins
category | Place category (options: lodging, restaurant, city, bar, activity, store, site, other)
address | Full address
city_state | city, state
country | 2-letter iso country code
zip | zip code
neighborhood | neighborhood
lat | latitude
lng | longitude
email | email address
phone | phone number with leading country code
website | main website for place
airports | closest airport codes
saves_count | number of users with this place in their passport
photos_count | number of photos of this place
continent_id | id of the continent (1: North America, 2: Central America, 3: South America, 4: [Empty], 5: Africa, 6: Europe, 7: Middle East, 8: Asia, 9: Australia & Oceania, 10: Caribbean)
featured | boolean, true if TravelEnvy has marked it as a featured place
created_at | timestamp of time/date created
updated_at | timestamp of time/date last updated
most_pop_photo_id | ID of the most popular photo (photo most often chosen as a user's main photo when saving this place)
price | estimated price
currency | currency of the estimated price
main_photo_url | url of the main photo to show for this place (based on the current user's preferences)
_links[ ] | Array of links to access associated objects.  Here is: "self", "most_pop_photo","saving_users", "photos", "source_urls", "tops_lists", "plans", "tips"



## Get a Specific Place

### HTTP Request

`GET https://travelenvy.com/api/places/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the place to retrieve

### Response

Parameter | Description
--------- | -----------
id | Place ID
added_by | ID of user that first uploaded this place
name | Place's name
summary | One line summary of place, created by TravelEnvy admins
category | Place category (options: lodging, restaurant, city, bar, activity, store, site, other)
address | Full address
city_state | city, state
country | 2-letter iso country code
zip | zip code
neighborhood | neighborhood
lat | latitude
lng | longitude
email | email address
phone | phone number with leading country code
website | main website for place
airports | closest airport codes
saves_count | number of users with this place in their passport
photos_count | number of photos of this place
continent_id | id of the continent (1: North America, 2: Central America, 3: South America, 4: [Empty], 5: Africa, 6: Europe, 7: Middle East, 8: Asia, 9: Australia & Oceania, 10: Caribbean)
featured | boolean, true if TravelEnvy has marked it as a featured place
created_at | timestamp of time/date created
updated_at | timestamp of time/date last updated
most_pop_photo_id | ID of the most popular photo (photo most often chosen as a user's main photo when saving this place)
price | estimated price
currency | currency of the estimated price
main_photo_url | url of the main photo to show for this place (based on the current user's preferences)



## Update a Specific Place

### HTTP Request

`PUT https://travelenvy.com/api/places/<id>`

### Query Parameters

### Response


## Delete a Specific Place

### HTTP Request

`DELETE https://travelenvy.com/api/places/<id>`

### Query Parameters

### Response