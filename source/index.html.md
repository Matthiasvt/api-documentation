---
title: API DOCU


includes:
  - errors

search: true
---

# Introduction
Welcome to the eve What the Eve API! You can use our API to access What the Eve API endpoints, which can get information on various events, locations, and festivals in our database.



The What the Eve API provides in automatically updated event data. This event data includes;

* Concerts
* Club nights
* Theatre shows
* Dance
* Comedy
* Movies

At the release of this document we provide coverage for the complete Amsterdam metropolitan area or ‘Randstad’ located in the Netherlands. This includes the city regions of Amsterdam, Rotterdam, Utrecht, The Hague. During 2016 we will provide data nationwide.
Our data is automatically updated and directly retrieved from event venue websites. This includes venues as;

* Concert halls
* (Beach-) Clubs
* Theatres
* Cinemas
* Festival grounds
* (Live-music) Bars
* Hotels
* Stadiums

With this API you’re able to retrieve event and venue data based on a multitude of parameters and filter queries.
The API is based on the REST principle. We currently only provide GET endpoints. JSON is returned in all API responses, including errors.
Access to the API is available on request.

# Authentication

For access to the API you’ll need an API-key.
The API-key has to be included in the header of every request:
To authorize, use this code:
 With shell, you can just pass the correct header with each request
curl "https://api.whattheeve.com/v2/events"
  -H "Authorization: Token API_KEY"
Make sure to replace API_KEY with your own API credentials.


> the services:

```ruby
http://eve-dev.datalinks.nl:7370/eve-service-open_search/rest/search
```



> All type of genres and their corresponding ID's




//I don't know if there are any Authorization.
`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Services

## Get All events

>This is the request from events

```code
http://eve-dev.datalinks.nl:7670/eve-service-open_events/rest/events?
```


>This is the response from events


```json
{
  "code": 201,
  "message": "Success",
  "total_count": 1,
  "data":
    "result": [
      {
         "ID": "658974",
         "name": "monday",
         "description": "monday. where dj's, artists, producers, promoters and people who work in the hottest restaurants and bars of amsterdam come together and meet for a drink. they come in and simply just chill, network and party like there's no tuesday! music: oldschool r&b and hip-hop in supperclub and (deep)house classics in apt. make sure you're on the list! www.partyonmonday.com or www.facebook.com/partyonmonday",
         "time": "2016-05-17 18:00:00",
         "endtime": "2016-05-17 19:40:00",
         "imageurl": "",
         "videourl": "https://www.youtube.com/watch?v=LJXkOFXmRLo",
         "video_thumb": "https://img.youtube.com/vi/LJXkOFXmRLo/0.jpg",
         "type": "film",
         "type_ID": "8",
         "cancelled": "0",
         "sold_out": "0",
         "venue_ID": "422",
         "Venue": {
            "ID": "422",
            "name": "Omniversum",
            "street": "President Kennedylaan",
            "street_number": "53",
            "postcode": "2517 JK",
            "city": "Amsterdam",
            "phone": "020 573 05 73",
            "type": "Bioscoop",
            "typeID": "9",
            "imageurl": "http://www.eve.nu/KEEP_ALIVE/images/events/600x500/20150528130601.png",
            "website": "http://concertgebouw.nl/",
            "facebook": "https://www.facebook.com/omniversum",
            "latitude": "52.0892664",
            "longitude": "4.2818149",
            "short_description": "Omniversum is een grootbeeldfilmtheater. De films worden door een geavanceerde techniek op een enorm projectiescherm geprojecteerd. Het scherm heeft...",
            "description": "Omniversum is een grootbeeldfilmtheater. De films worden door een geavanceerde techniek op een enorm projectiescherm geprojecteerd. Het scherm heeft de vorm van een halve bol en loopt half rondom het publiek. Dit koepelscherm is zo groot als een half voetbalveld. Overal om u heen ziet u het beeld van de film. De beleving wordt nog eens extra versterkt door een subliem geluidssysteem. Ronduit Spectaculair dus!"
         }
      },
```

This endpoint retrieves all kittens.

### HTTP Request

` http://eve-dev.datalinks.nl:7670/eve-service-open_events/rest/events?`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page	        |int	    |Page number of event list.
limit	        |int	    |Limit per page. 0 for full list - till a maximum of 1000.
genre	        |int	    |1 - 10 *
min_price	    |int        |Minimum price for an event.
max_price	    |int	    |Maximum price for an event . 0 for free.
from_date	    |timestamp	|From date & time. Format: YYYY-MM-DD HH:MM:SS.
end_date	    |timestamp	|End date & time. Format: YYYY-MM-DD HH:MM:SS.
max_distance	|int	    |maximum distance in kilometers from latitude, longitude position.
latitude	    |string	    |Center latitude for maximum distance.
longitude	    |string	    |Center longitude for maximum distance.
city	        |string	    |The city where the event is.


<aside class="notice">
All type of genres and their corresponding ID's
</aside>
ID | Type |
--------- | -------
1	      |Concert
2	      |Festival
3	      |DJ
4	      |-
5	      |Theater
6	      |Dance
7	      |Cabaret
8	      |Movie
9	      |Other
10	      |Kids




## Get a Specific Event

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

THis endpoint retrieves a specific event.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://api.whattheeve.com/v2/event/:event_id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the event to retrieve




## Search

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```


```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

THis endpoint retrieves a specific location.


### HTTP Request

`GET https://api.whattheeve.com/v2/search?:parameters`

### URL Parameters



Parameter |	Value	|Description
----------|---------|-----------
keyword (required)|string	|String of search keywords (should be at least 3 characters).
page	          |int	    |Page number of event list.
limit	          |int	    |Limit per page. 0 for full list.




## Get a Specific Location

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```



```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```



### HTTP Request

`GET https://api.whattheeve.com/v2/venue/:venue_id`

### URL Parameters

Parameter | Value	   |Description
--------- | -----------|-----------
ID        |int         |The ID of the location to retrieve
page      |int         |page number of event list.
limit	  |int         |limit per page. 0 for full list.