# Nascar Motorsport

## Introduction

**Nascar Motorsport API** is ideal for developers, sports analysts, and NASCAR enthusiasts, delivering detailed insights into various NASCAR events and drivers.

## Authentication

The URL you need to use is the following: `https://nascar-motorsport-api.p.rapidapi.com/`
The API requires the headers listed below:

- **`x-rapidapi-host`**: `nascar-motorsport-api.p.rapidapi.com`
- **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/nascar-motorsport-api/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

## Caching

The API uses caching to store the race results data to enhance performance and reduce the load on the server.

If the data for the requested year and series is already cached, the API will serve the response from the cache.

## Endpoints

The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

### 1. **`GET /photos`**

- **Description**: Retrieves photos of a specific driver with support for pagination.

| Query Parameter  | Type   | Default | Description                                    | Required |
|------------------|--------|---------|------------------------------------------------|----------|
| `driverId`       | string | -       | The ID of the driver                           | Yes      |
| `page`           | string | `1`     | The number of the page to retrieve photos from | No       |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/photos?driverId=4495&page=1', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9841030",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F30%2F1269585583.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9840729",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F30%2F1269582358.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9839744",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F29%2F1269572277.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9839741",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F29%2F1269572272.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9835737",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F29%2F1269431794.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9835736",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F29%2F1269431798.jpg"
  },
  {
    "href": "https://www.espn.com/racing/driver/photos?id=4495&photoId=9835734",
    "imgSrc": "https://a.espncdn.com/combiner/i?img=media%2Fgettyphoto%2F2020%2F08%2F29%2F1269431784.jpg"
  },
  {
    ...
```

### 2. **`GET /stats`**

- **Description**: Retrieves detailed statistics for a specified driver.

| Query Parameter  | Type   | Default | Description                         | Required |
|------------------|--------|---------|-------------------------------------|----------|
| `driverId`       | string | -       | The ID of the driver                | Yes      |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/stats?driverId=4495', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "year": 2017,
    "rank": null,
    "starts": 2,
    "wins": 0,
    "poles": 0,
    "top5": 0,
    "top10": 0,
    "points": 0,
    "avgStart": "0",
    "avgFinish": "34"
  },
  {
    "year": 2018,
    "rank": null,
    "starts": 34,
    "wins": 0,
    "poles": 0,
    "top5": 0,
    "top10": 0,
    "points": 1,
    "avgStart": "0",
    "avgFinish": "32"
  },
  {
    "year": 2019,
    "rank": null,
    "starts": 35,
    "wins": 0,
    ...
```

### 3. **`GET /athlete-info`**

- **Description**: Retrieves detailed information about a specific athlete.

| Query Parameter  | Type   | Default | Description                         | Required |
|------------------|--------|---------|-------------------------------------|----------|
| `athleteId`      | string | -       | The ID of the athlete               | Yes      |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/athlete-info?athleteId=4495', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "id": "4495",
  "uid": "s:2000~a:4495",
  "guid": "278cb608-dc31-c2ed-4336-ded2dc4eff0e",
  "alternateId": "2571435",
  "firstName": "Ross",
  "middleName": "",
  "lastName": "Chastain",
  "fullName": "Ross Chastain",
  "displayName": "Ross Chastain",
  "shortName": "R. Chastain",
  "dateOfBirth": "1992-12-04T08:00Z",
  "link": "https://www.espn.com/racing/driver/_/id/4495/ross-chastain",
  "birthPlace": {
    "city": "Alva",
    "state": "FL"
  },
  "slug": "ross-chastain",
  "headshot": "https://a.espncdn.com/i/headshots/rpm/players/full/4495.png",
  "vehicles": [
    {
      "number": "1",
      "manufacturer": "Chevrolet",
      "chassis": "Chevrolet",
      "engine": "Chevrolet",
      "tire": "Goodyear",
      "team": "TRACKHOUSE RACING TEAM"
    },
    {
      "number": "41",
      ...
```

### 4. **`GET /news`**

- **Description**: Retrieves the latest Nascar news articles with support for pagination.

| Query Parameter  | Type   | Default | Description                                  | Required |
|------------------|--------|---------|----------------------------------------------|----------|
| `page`           | number | `1`     | The page number of news articles to retrieve | No       |
| `perPage`        | string | `15`    | The number of news articles per page         | No       |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/news?page=1&perPage=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "news": {
    "page": 1,
    "perPage": 20,
    "resultsCount": 20,
    "feed": [
      {
        "id": 42038973,
        "headline": "Reddick wins at Homestead, gives Jordan shot at NASCAR title",
        "byline": "",
        "description": "Tyler Reddick went high and overtook Ryan Blaney on the final turn to win at Homestead-Miami on Sunday to secure a spot in NASCAR's winner-take-all finale in Arizona in two weeks.",
        "nowId": "1-42038973",
        "premium": "",
        "related": [],
        "url": "https://www.espn.com/racing/nascar/story/_/id/42038973/reddick-wins-homestead-gives-jordan-shot-nascar-title",
        "categories": [
          {
            "id": 27981,
            "description": "NASCAR",
            "type": "league",
            "sportId": 2020,
            "leagueId": 2020,
            "league": {
              "id": 2020,
              "description": "NASCAR",
              "links": {
                "web": {
                  "leagues": {
                    "href": "https://www.espn.com/racing/nascar/"
                  }
                  ...
```

### 5. **`GET /current-scoreboard`**

- **Description**: Retrieves the most recent scoreboard data.

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/current-scoreboard', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "sports": [
    {
      "id": "2000",
      "uid": "s:2000",
      "guid": "a5f9ac6b-82e3-3891-a17a-ea2d693b8331",
      "name": "Motor Sports",
      "slug": "racing",
      "logos": [
        {
          "href": "https://a.espncdn.com/combiner/i?img=/redesign/assets/img/icons/ESPN-icon-NASCAR.png",
          "alt": "",
          "rel": [
            "full",
            "default"
          ],
          "width": 500,
          "height": 500
        }
      ],
      "leagues": [
        {
          "id": "2040",
          "uid": "s:2000~l:2040",
          "name": "IndyCar Series",
          "abbreviation": "IRL",
          "shortName": "IRL",
          "slug": "irl",
          "tag": "irl",
          "isTournament": false,
          ...
```

### 6. **`GET /scoreboard`**

- **Description**: Retrieves the scoreboard data for the specified year, with optional filters for month and day.

| Query Parameter | Type   | Default | Description                             | Required |
|-----------------|--------|---------|-----------------------------------------|----------|
| `year`          | string | -       | The year of the scoreboard (YYYY)       | Yes      |
| `month`         | string | `null`  | The month of the scoreboard (MM)        | No       |
| `day`           | string | `null`  | The day of the scoreboard (DD)          | No       |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/scoreboard?year=2024', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "scoreboard": [
    {
      "id": "202403100104",
      "uid": "s:2000~l:2040~e:202403100104",
      "date": "2024-03-10T16:00Z",
      "name": "Grand Prix of St. Petersburg",
      "shortName": "Grand Prix of St. Petersburg",
      "season": {
        "year": 2024,
        "type": 2,
        "slug": "regular-season"
      },
      "competitions": [
        {
          "id": "202403100104",
          "uid": "s:2000~l:2040~e:202403100104~c:202403100104",
          "date": "2024-03-10T16:00Z",
          "timeValid": true,
          "recent": false,
          "competitors": [
            {
              "id": "5581",
              "uid": "s:2000~a:5581",
              "type": "athlete",
              "order": 1,
              "winner": true,
              "athlete": {
                "fullName": "Pato O'Ward",
                "displayName": "Pato O'Ward",
                ...
```

### 7. **`GET /race-report`**

- **Description**: Retrieves the race report for a specific race.

| Query Parameter | Type   | Default | Description                         | Required |
|-----------------|--------|---------|-------------------------------------|----------|
| `raceId`        | string | -       | The ID of the race                  | Yes      |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/race-report?raceId=202302054248', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "report": {
    "racestrip": {
      "name": "Clash at The Coliseum",
      "shortName": "Clash at The Coliseum",
      "date": "2023-02-06T01:00Z",
      "season": 2023,
      "circuit": {
        "countryFlag": {
          "href": "https://a.espncdn.com/i/teamlogos/countries/500/usa.png",
          "alt": "USA",
          "rel": [
            "country-flag"
          ]
        }
      },
      "broadcasts": [
        {
          "type": {
            "id": "1",
            "shortName": "TV",
            "longName": "Television",
            "slug": "television"
          },
          "media": {
            "id": "148",
            "callLetters": "FOX",
            "name": "FOX",
            "shortName": "FOX",
            "slug": "fox",
            ...
```

### 8. **`GET /race-results`**

- **Description**: Retrieves the race results for a specific driver and year.

| Query Parameter | Type   | Default | Description                         | Required |
|-----------------|--------|---------|-------------------------------------|----------|
| `driverId`      | string | -       | The ID of the driver                | Yes      |
| `year`          | string | `2023`  | The year of the race (YYYY)         | No       |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/race-results?driverId=810&year=2024', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "date": "9/15",
    "race": "Grand Prix of Nashville",
    "place": 24,
    "start": 4,
    "laps": 0,
    "points": 198
  },
  {
    "date": "9/1",
    "race": "Grand Prix of Milwaukee Race 2",
    "place": 10,
    "start": 4,
    "laps": 64,
    "points": 250
  },
  {
    "date": "8/31",
    "race": "Grand Prix of Milwaukee Race 1",
    "place": 2,
    "start": 5,
    "laps": 9,
    "points": 250
  },
  {
    "date": "8/25",
    "race": "Grand Prix of Portland",
    "place": 1,
    "start": 2,
    ...
```

### 9. **`GET /results`**

- **Description**: Retrieves the race results for the specified year and series.

| Query Parameter | Type   | Default | Description                         | Required |
|-----------------|--------|---------|-------------------------------------|----------|
| `year`          | number | -       | The year of the races (YYYY)        | Yes      |
| `series`        | number | `1`     | The desired series¹                 | No       |

¹ The series parameter can have the following values: 1 -> NASCAR Cup Series | 2 -> NASCAR Xfinity Series | 3 -> NASCAR Truck Series

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/results?year=2024', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "date": "Sat, Feb 3",
    "name": "Clash at The Coliseum",
    "track": "Los Angeles Memorial Coliseum",
    "raceId": "202402034248",
    "winner": {
      "id": "747",
      "name": "Denny Hamlin",
      "link": "https://www.espn.com/racing/driver/_/id/747/denny-hamlin",
      "car": "Toyota"
    },
    "poleWinner": {
      "id": "747",
      "name": "Denny Hamlin",
      "link": "https://www.espn.com/racing/driver/_/id/747/denny-hamlin",
      "car": "Toyota"
    }
  },
  {
    "date": "Thu, Feb 15",
    "name": "Duel #1",
    "track": "Daytona International Speedway",
    "raceId": "202402150044",
    "winner": {
      "id": "4577",
      "name": "Tyler Reddick",
      "link": "https://www.espn.com/racing/driver/_/id/4577/tyler-reddick",
      "car": "Toyota"
    },
    ...
```

### 10. **`GET /standing-drivers`**

- **Description**: Retrieves driver standings for a specific year.

| Query Parameter | Type   | Default | Description                         | Required |
|-----------------|--------|---------|-------------------------------------|----------|
| `year`          | string | -       | The desired year                    | Yes      |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/standings-drivers?year=2024', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "standings": {
    "season": 2024,
    "seasonType": 2,
    "entries": [
      {
        "athlete": {
          "id": "5632",
          "uid": "s:2000~a:5632",
          "displayName": "Álex Palou",
          "abbreviation": "PAL",
          "name": "Álex Palou",
          "shortName": "Á. Palou",
          "flag": {
            "href": "https://a.espncdn.com/i/teamlogos/countries/500/esp.png",
            "alt": "Spain",
            "rel": [
              "country-flag"
            ]
          }
        },
        "stats": [
          {
            "name": "rank",
            "displayName": "Rank",
            "shortDisplayName": "RK",
            "description": "Rank",
            "abbreviation": "RK",
            "type": "rank",
            "value": 1,
            ...
```

### 11. **`GET /schedule`**

- **Description**: Retrieves the schedule data for the specified year.

| Query Parameter | Type   | Default | Description                         | Required |
|-----------------|--------|---------|-------------------------------------|----------|
| `year`          | string | -       | The desired year                    | Yes      |

Example request:

```javascript
fetch('https://nascar-motorsport-api.p.rapidapi.com/schedule?year=2023', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nascar-motorsport-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "raceId": "202302054248",
    "date": "Sun, Feb 58:00 PM ET",
    "name": "Clash at The Coliseum",
    "track": "Los Angeles Memorial Coliseum",
    "tv": "FOX",
    "startingGrid": "http://www.espn.com/racing/grid/_/raceId/202302054248/series/sprint",
    "raceResults": "http://www.espn.com/racing/raceresults?raceId=202302054248&series=sprint"
  },
  {
    "raceId": "202302160044",
    "date": "Thu, Feb 167:00 PM ET",
    "name": "Duel #1",
    "track": "Daytona International Speedway",
    "tv": "FS1",
    "startingGrid": "http://www.espn.com/racing/grid/_/raceId/202302160044/series/sprint",
    "raceResults": "http://www.espn.com/racing/raceresults?raceId=202302160044&series=sprint"
  },
  {
    "raceId": "202302160045",
    "date": "Thu, Feb 168:45 PM ET",
    "name": "Duel #2",
    "track": "Daytona International Speedway",
    "tv": "FS1",
    "startingGrid": "http://www.espn.com/racing/grid/_/raceId/202302160045/series/sprint",
    "raceResults": "http://www.espn.com/racing/raceresults?raceId=202302160045&series=sprint"
  },
  {
    "raceId": "202302190001",
    ...
```

## Error Handling

The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |

