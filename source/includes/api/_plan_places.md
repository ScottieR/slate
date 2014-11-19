# Plan Places

```shell
```

>The above command returns json like this
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
    "tip_id":224,
    "photo_id":644
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

##Get a list of Plan Places


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

### JSON response

An array of plan places with its id and attributes.  Also, each plan place has it's corresponding item (which can be a place, transportation leg, or note).  These items share the same format as a place, transort_leg, or note returns individually (see documentation below).

##Get a Specific Plan Place

This endpoint retrieves a specific plan place (ie item within a plan).

<aside class="warning">If you're not using an administrator API key, note that some plan places will return 403 Forbidden if they are private to admins or the plan's owners and travelers only.</aside>


## Places

## Transportation Legs

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

## Notes

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

#Tops Lists