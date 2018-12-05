# Events

## Get All Events

```php
$api = new Tiebreak('<api-key>');
$events = $api->getEvents();
```

```javascript
const tiebreak = require('tiebreak');

let api = tiebreak.authorize('<api-key>');
let events = api.events.get();
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 4,
        "created_at": "2013-01-11 23:52:12",
        "updated_at": "2013-01-11 23:52:12",
        "draw_type_id": 4,
        "score_sheet_id": 3,
        "parent_id": 0,
        "name": "February Fight Club",
        "sef_url": "february-fight-club",
        "short_url": "uyfews",
        "starts_at": "2013-02-03 10:00:00",
        "ends_at": "2013-02-03 18:00:00",
        "status": "Complete",
        "active": 1,
        "lat": 52.6399181,
        "lng": -1.1294268,
        "sandbox": 0,
        "deleted_at": null,
        "players_count": 14,
        "meta": [
            {
                "key": "address_1",
                "value": "66B Bedford Street South"
            },
            {
                "key": "city",
                "value": "Leicester"
            },
            {
                "key": "county",
                "value": "Leicestershire"
            },
            {
                "key": "postcode",
                "value": "LE1 3JR"
            },
            {
                "key": "country",
                "value": "United Kingdom"
            },
            {
                "key": "player_limit",
                "value": "24"
            },
            {
                "key": "cover_image",
                "value": "images/fightclub1.jpg"
            },
            {
                "key": "avatar",
                "value": "images/fightclub1-avatar.jpg"
            },
            {
                "key": "scoring",
                "value": "{\"fields\":[\"tb_1\",\"tb_2\",\"tb_3\",\"tb_4\"],\"order\":[\"tb_1 DESC\",\"tb_2 DESC\",\"tb_3 DESC\",\"tb_4 DESC\", \"name ASC\"],\"display\":[\"TP\",\"SOS\",\"CP\",\"VP\"],\"type\":[\"wl\",\"sos\",\"input\",\"input\"],\"names\":[\"TP\",\"SOS\",\"CP\",\"VP\"],\"editfields\":[\"tb_1\",\"tb_2\",\"tb_3\",\"tb_4\"],\"submitfields\":[\"-\",\"-\",\"tb_3\",\"tb_4\"]}"
            },
            {
                "key": "base_code",
                "value": "FFC13"
            },
            {
                "key": "primary_colour",
                "value": "1d3353"
            },
            {
                "key": "secondary_colour",
                "value": "669ac3"
            },
            {
                "key": "registration",
                "value": "1"
            },
            {
                "key": "rules",
                "value": "<ul>\n<li>3rd of February </li>\n<li>4 Games (70mins per game), 7 min turns with one 3 min turn extension</li>\n<li>Two lists - Character Restricted, both lists must be used once. </li>\n<li>No Proxies allowed</li>\n<li>£5 entry fee </li>\n<li>Event will begin at 10am.</li>\n</ul>"
            },
            {
                "key": "venue",
                "value": "Tabletop Tyrant"
            },
            {
                "key": "confirm_fields",
                "value": "[{\"name\":\"list1\",\"type\":\"textarea\",\"display\":\"List 1\"},{\"name\":\"list2\",\"type\":\"textarea\",\"display\":\"List 2\"}]"
            },
            {
                "key": "deadline",
                "value": "2013-02-02 00:00:00"
            },
            {
                "key": "w",
                "value": "1"
            },
            {
                "key": "tiebreak",
                "value": "1"
            }
        ],
        "type": {
            "id": 2,
            "name": "Masters",
            "system_id": 1,
            "draw_type_id": 4,
            "score_sheet_id": 3,
            "defaultscoring": "{\"fields\":[\"tb_1\",\"tb_2\",\"tb_3\",\"tb_4\"],\"order\":[\"tb_1 DESC\",\"tb_2 DESC\",\"tb_3 DESC\",\"tb_4 DESC\", \"name ASC\"],\"display\":[\"TP\",\"SOS\",\"CP\",\"VP\"],\"type\":[\"wl\",\"sos\",\"input\",\"input\"],\"names\":[\"TP\",\"SOS\",\"CP\",\"VP\"],\"editfields\":[\"tb_1\",\"tb_2\",\"tb_3\",\"tb_4\"],\"submitfields\":[\"-\",\"-\",\"tb_3\",\"tb_4\"]}",
            "library": "Masters",
            "w": 1,
            "l": 0,
            "d": 0,
            "random": 1,
            "customscoring": 0,
            "default_type": 0,
            "options": "",
            "scoresheet": "steamroller"
        },
        "system": {
            "id": 1,
            "name": "Warmachine / Hordes",
            "sef_url": "warmachine-hordes",
            "faction_id": 1,
            "manufacturer_id": 1,
            "sequence": 1,
            "image": "warmachine.png",
            "listbuilder": 1,
            "notes": "",
            "listrules": null,
            "active": 1
        },
        "user": {
            "id": 10003,
            "email": "ross.jkm@gmail.com",
            "group_id": 3,
            "first_name": "Ross",
            "last_name": "Knill-Macarthur",
            "created_at": "2012-12-31 16:05:18",
            "updated_at": "2016-06-10 10:35:08",
            "location": "Leicester, United Kingdom",
            "club": "Leicester Phat Cats",
            "sef_url": "ross-knill-macarthur",
            "hideguide": 1,
            "avatar": null,
            "cover": null,
            "email_news": 1,
            "email_balance": 1,
            "email_news_confirmed": 1,
            "optin_date": "2018-05-24 10:12:37",
            "country": "United Kingdom",
            "stripe_token": "",
            "fixed_commission": null,
            "hash": "e162e30a5a4c1e44a7e04fca063c296001f26636ecf384701ae17849a4f83b11",
            "viewing_event": null
        }
    }
]
```

This endpoint retrieves all events matching the parameters passed.

### HTTP Request

`GET http://api.tiebreak.co.uk/v2/events`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
active | true | If set to false events that are not active are returned.
sandbox | false | If set to true only sandbox events will be returned.
deleted | false | If set to true, deleted events will be returned.
parent_id | 0 | If an id is passed, events that are children of the event id passed will be returned.
order | starts_at | The column to order results by.
sort | ASC | The sort order to use.
limit | 10 | The number of results to return.
start | 0 | How many results to skip before returning - used for pagination.
user_id | - | Returns events where the passed user_id is a TO.
starts_after | - | Returns events that start after the given date. `2018-12-05 01:08:00`.
starts_before | - | Returns events that start before the given date. `2018-12-05 01:08:00`.
ends_after | - | Returns events that end after the given date. `2018-12-05 01:08:00`.
ends_before | - | Returns events that end before the given date. `2018-12-05 01:08:00`.
type_id | - | Returns events of a given [Type](#types).
system_id | - | Returns events of a given [System](#systems).
lat | - | Used in conjunction with `lng` and `distance` for  location based searches. Events within the given `distance` from the coordinates passed are returned.
lng | - | Used in conjunction with `lat` and `distance` as described above.
distance | - | Used in conjunction with `lat` and `lng` as described above.
ranked | - | If passed, only ranked events will be returned.
attendee | - | If an id of a [User](#users) is passed, events they are attending will be returned.
