# Joan Sleep - Fullstack assignment #01

## Introduction
Joan is a meeting room assistant which enables user to book the room on the fly or check the schedule. Since we want it to be very power efficient we would like to extend it's battery life by putting it to sleep when not needed. User has a personal dashboard to setup this and some other features for the device.

We want him/her to be able to select which days in a week and from/to time Joan displays meeting information and when is the time to sleep. If a user selects `Monday`,`Tuesday`,`Friday`,`Saturday` (days of week) and time period from `07:00` to `19:00`, this would mean that device should be running __between 7:00-19:00 on Monday, 7:00-19:00 on Tuesday, 7:00-19:00 on Friday and 7:00-19:00 on Saturday every week__.

## Task
Create a dockerized web application, that will be capable of:
- retrieving current sleep schedule settings
- storing sleep schedule settings
- displaying current sleep status of the device (sleep or awake)

## Submission
Assignment should be submitted by providing a link to accessible `git` repository or `compressed archive`.

### 1. Storage
You can store sleep schedule settings in `MySQL` or `Postgres` database. There are no special requirements for DB schema.

### 2. Backend
Backend can be in latest version of `Django` or `Flask`. It should expose the following http endpoints:

---
Main page that displays sleep settings form.
```
GET / 
Content-Type: text/html; charset=utf-8
```
---
A page that displays if device should currently be awake or asleep.
```
GET /status/
Content-Type: text/html; charset=utf-8
```
---
REST endpoint that returns current sleep schedule settings.
```
GET /api/settings/
Content-Type: application/json; charset=utf-8

{
    days:[1,2,3,4],
    from:'07:30',
    to:'19:00'
}
```
---
REST endpoint that stores sleep schedule settings. 

- `days` - day of week as defined in __ISO 8601__ (array of numbers)
- `from` - hour from in __hh:mm__ format (string)
- `to` - hour from in __hh:mm__ format (string)

Endpoint should validate that:
- `days` contains valid numbers
- `days` contains at least one valid day of week
- `from` and `to` are in valid format
- `to` is larger than `from`

```
PUT /api/settings/
Content-Type: application/json; charset=utf-8

{
    days:[1,2,3,4],
    from:'07:30',
    to:'19:00'
}

# Returns:

HTTP 204 for success
HTTP 400 for validation error
```
---
REST endpoint that returns current sleep status and time until next change (in seconds).

```
GET /api/status/
Content-Type: application/json; charset=utf-8

# device is currently sleeping and will awake in 60 seconds
{
    sleep:true,
    for:60
}

# device is currently awake and will go to sleep in 10 minutes
{
    sleep:false,
    for:600
}

# device is currently awake and will never go to sleep
{
    sleep:false,
    for:null
}
```

### 3. Frontend
Frontend should be in form of SPA using latest version of `React`, `Angular` or `Vue`. There are no special requirements for the design (can be simple checkboxes, dropdowns and buttons). It should have 2 distinct pages:

- `/` main page that displays sleep settings form. It must also contain a link to `/status/` page.
- `/status/` a page that displays if device should currently be awake or asleep. This can be in form of a simple text or using a visual indicator (colors, images, etc.). It must also contain a link to `/` page.

Frontend should communicate with backend using `/api/...` REST endpoints.

### 4. Docker
Web application and database should run inside separate docker containers. Create `Dockerfile` that bundles web application and `docker-compose.yml` file that runs all needed containers. 
Apart from having `docker` and `docker-compose` installed, there should be no special installation requirements on host machine.

Entire app should run by executing:
```
docker-compose up
``` 
Application should be browsable on `http://localhost:8000/`
