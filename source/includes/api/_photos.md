#Photos

##Get all Photos

> To get all photos, use the following code:

```shell
  curl https://travelenvy.com/api/photos?access_token=your_token
```

```ruby
access.get("/api/photos").parsed
```

> The above returns the following json:

```json
{"photos":[
  {
    "id":3459,
    "alt":"The Rose Hotel - Venice - Los Angeles, CA",
    "place_id":478,
    "source":"http://www.yelp.com/biz/the-rose-hotel-los-angeles",
    "added_by":1,
    "src":"/tmp/assets/photos/3459/medium/ls.jpg?1414520565",
    "_links":{
      "self":{"href":"/api/photos/3459"},
      "place":{"href":"/api/places/478"}
    }
  },{
    "id":3458,
    "alt":"Marina del Rey Hotels - Hilton Garden Inn Los Angeles Marina Del ...",
    "place_id":478,
    "source":"http://hiltongardeninn3.hilton.com/en/hotels/california/hilton-garden-inn-los-angeles-marina-del-rey-LAXDRGI/",
    "added_by":1,
    "src":"http://hiltongardeninn3.hilton.com/resources/media/gi/LAXDRGI/en_US/img/shared/full_page_image_gallery/main/GI_extday_698x390_FitToBoxSmallDimension_Center.jpg",
    "_links":{
      "self":{"href":"/api/photos/3458"},
      "place":{"href":"/api/places/478"}
    }
  }
]}
```

This endpoint returns all photos

### HTTP Request

`GET https://travelenvy.com/api/photos`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
photos | false | A comma separated list of photo ids by which to filter.  If not present, returns all photos.
place | false | Filters photos by the given place id.  Returns photos for the place.

### Response

Attribute | Description
--------- | -----------
id | photo ID
src | The url of the photo location to be used in an image tag
alt | The alt text for the photo
source | The url of the website page the photo was found on
added_by | ID of the user who added the photo
place_id | ID of the place the photo corresponds to
_links | array of hrefs that point to associated objects (here: "self", "place")

## Get a specific photo

> To get a specific photo, use the following code:

```shell
  curl https://travelenvy.com/api/photos?id=1216&access_token=your_token
```

```ruby
access.get("/api/photos/358").parsed
```

> The above returns the following json:

```json
{"photo": {
  "id":3458,
  "alt":"Marina del Rey Hotels - Hilton Garden Inn Los Angeles Marina Del ...",
  "place_id":478,
  "source":"http://hiltongardeninn3.hilton.com/en/hotels/california/hilton-garden-inn-los-angeles-marina-del-rey-LAXDRGI/",
  "added_by":1,
  "src":"http://hiltongardeninn3.hilton.com/resources/media/gi/LAXDRGI/en_US/img/shared/full_page_image_gallery/main/GI_extday_698x390_FitToBoxSmallDimension_Center.jpg",
  "_links":{
    "self":{"href":"/api/photos/3458"},
    "place":{"href":"/api/places/478"}
  }
}
```

### HTTP Request
`GET https://travelenvy.com/api/photos/<ID>`

### Response
Same as above when requesting all photos

## Create a photo

> To create a photo, use the following code:

```shell
  curl --data "photo[place_id]=98&photo[src]=source_url" https://travelenvy.com/api/photos?access_token=your_token
```

```ruby
access.post("/api/photos?photo[place_id]=98&photo[src]=source_url").parsed
```

The endpoint to create a new photo

### HTTP Request
`POST https://travelenvy.com/api/photos?<PARAMS>`

### URL Parameters

Parameters | Required | Description
--------- | -------- | -----------
photo[src] | The url of the photo file (ex: http://www.hotelsite.com/assets/img145.jpg).  Either us this or "upload" per create
photo[upload] | the photo file to upload.  Either us this or "src" per create
photo[alt] | The alt text for the photo
photo[source] | The url of the website page the photo was found on
photo[place_id] | ID of the place the photo corresponds to

### Response

Status | Description
------ | -----------
201 | Successfully created

## Update a photo

> To update a photo, use the following code:

```shell
  curl --data "photo[alt]=Hotel" https://travelenvy.com/api/photos/1215?access_token=your_token
```

```ruby
access.post("/api/photos/1215?photo[place_id]=98&photo[alt]=Hotel").parsed
```

The endpoint to update a photo

### HTTP Request
`PUT https://travelenvy.com/api/photos/<ID>?<PARAMS>`


### URL Parameters

Parameter | Required | Description
--------- | -------- | -----------
photo[src] | The url of the photo file (ex: http://www.hotelsite.com/assets/img145.jpg).  Either us this or "upload" per create
photo[upload] | the photo file to upload.  Either us this or "src" per create
photo[alt] | The alt text for the photo
photo[source] | The url of the website page the photo was found on
photo[place_id] | ID of the place the photo corresponds to
photo[flag] | If the photo should be marked for removal (because it is ugly, inaccurate or inappropriate)

### Response

Status Code | Case
----------- | ----
204 | Successfully updated

## Destroy a photo

> To delete a photo, use the following code:

```shell
  
```

```ruby
access.delete("/api/photos/1215")
```

The endpoint to destroy a specific photo

<aside class="warning">Only admins and users who created the photo can destroy it.</aside>

### HTTP Request
`DELETE https://travelenvy.com/api/photos/1215`

### Response

Status Code | Case
----------- | ----
403 | User is not authorized (the user did not create the photo or is not an admin)
204 | Successfully deleted