# SAIRC-Documentation
## Auth routes

### Register
	POST http://127.0.0.1:8000/api/v1/auth/register

Request
JSON body params
1. `name` 
	Name of the user
	- must be a valid alphabetic name
2. `email`
	- must be a valid email address
3. `password`
	- must be a valid string 

`Auth routes needs clarification`

----

## user-routes
1. `GET http://127.0.0.1:8000/api/v1/users/{id}`

	Request
  
	```bash
  
	curl --request GET \
	  --url http://127.0.0.1:8000/api/v1/users/3 \
	  --header 'Content-Type: application/json' \
	  --header 'application/json: application/json' \
    
	```
	Response
	- json response containing the user details
	```json
	{
		"id": 3,
		"name": "Domenica Gibson MD",
		"email": "rolando.monahan@example.com",
		"email_verified_at": "2022-12-12T07:43:23.000000Z",
		"deleted_at": null,
		"created_at": "2022-12-12T07:43:23.000000Z",
		"updated_at": "2022-12-12T07:43:23.000000Z"
	}
	```

2.  `PUT http://127.0.0.1:8000/api/v1/users/{id}`

	Request
  
```bash
	curl --request PUT \
  --url http://127.0.0.1:8000/api/v1/users/3 \
  --header 'Content-Type: application/json' \
  --header 'application/json: application/json' \
  --data '{"name":"hi","email":"test@test.com"}'
  
```
Response
- `1` if operation in successful
```json
	1
```

----
## feed-routes
1. `GET http://127.0.0.1:8000/api/v1/feeds/{id}`

	Request
		get feed with `id` 1
```bash
  
	curl --request GET \
  --url http://127.0.0.1:8000/api/v1/feed/1 \
  --header 'Content-Type: application/json' \
  --header 'application/json: application/json'
  
```
	Response
	- json response containing the feed details
  
```json
	{
	"id": 1,
	"feed_heading": "Tom got a small piece of pie.",
	"username": "Maximus ",
	"image_path": "https:\/\/picsum.photos\/200\/300",
	"content": "Tom got a small piece of pie.",
	"user_id": 1,
	"created_at": "2022-12-13T18:46:05.000000Z",
	"updated_at": "2022-12-13T18:46:07.000000Z"
	}
```
  
2. `POST http://127.0.0.1:8000/api/v1/feeds/`
	Request
		creates feeds with the provided json data 
3. `PUT http://127.0.0.1:8000/api/v1/feeds/`
	updates feed with json data
4. `DELETE http://127.0.0.1:8000/api/v1/feeds/`
	deletes feed with given id

----
## comment-routes

1. `GET http://127.0.0.1:8000/api/v1/comment/{id}`
	returns comment with the specified id
2. `POST http://127.0.0.1:8000/api/v1/comment/`
	creates comment with the provided json data 
3. `PUT http://127.0.0.1:8000/api/v1/comment/{id}`
	updates comment with json data
4. `DELETE http://127.0.0.1:8000/api/v1/comment/`
	deletes comment with given id

## mail 
1. `GET http://127.0.0.1:8000/api/v1/mail/`
	Not implimeted

---

## jobs 
1.  `GET http://127.0.0.1:8000/api/v1/jobs/`
	Returns all jobs
2.  `GET http://127.0.0.1:8000/api/v1/storeJobs/`
	stores jobs using data from the  json request body

---
## experience 
1. `GET http://127.0.0.1:8000/api/v1/experience/`
	Returns work experience
---
## suggestions 
1. `GET http://127.0.0.1:8000/api/v1/suggestions/`
	return suggestions
----
## followers
1. `GET http://127.0.0.1:8000/api/v1/follow/`
	create user following
2. `GET http://127.0.0.1:8000/api/v1/followers/pending/`
	return list of pending follower requests
3. `GET http://127.0.0.1:8000/api/v1//follower/request/`
	accepts follower request
4. `GET http://127.0.0.1:8000/api/v1/follower/denied/`
	denies follower request

---
 ## profiles
 1. `POST http://127.0.0.1:8000/api/v1/profile`
	 returns profile with specified id 
   
   # Notices API

##### GET:  `http://127.0.0.1:8000/api/v1/notice`
	returns all the notices that are present on the notices table
```json
[
    {
        "id": 1,
        "heading": "Super Notice",
        "content": "This is a very important notice and follow it ",
        "image": "notice.jpg",
        "user_id": 2,
        "created_at": "2023-01-13T13:32:46.000000Z",
        "updated_at": null
    },
    {
        "id": 2,
        "heading": "IMportant Notices3",
        "content": "This is notice 3 and follow 3",
        "image": "images3.jpg",
        "user_id": 3,
        "created_at": "2023-01-13T13:33:39.000000Z",
        "updated_at": null
    }
]
```

##### GET:  `http://127.0.0.1:8000/api/v1/notice/{id}`
	returns the specific notice where notice id equals the given params.

##### POST: `http://127.0.0.1:8000/api/v1/notice`
	returns the notice that has been just saved.

##### PUT: `http://127.0.0.1:8000/api/v1//notice/{id}`
	finds the user with the id and updates the fields of the specific notice.

##### DELETE: `http://127.0.0.1:8000/api/v1//notice/{id}`
	finds the user with the id and delete the notice with the idf(id of notice and not user), it is not working till now.
---


# Notifications API

##### GET: `http://127.0.0.1:8000/api/v1/notification`
	return all the notifications in the notifications table:
```JSON
[
    {
        "id": 1,
        "name": "Notifications Name",
        "url": "Notifications URL",
        "user_id": 2,
        "created_at": "2023-01-13T14:46:33.000000Z",
        "updated_at": "2023-01-13T14:46:35.000000Z"
    },
    {
        "id": 2,
        "name": "Notifications 3 ",
        "url": "Notifications3 ",
        "user_id": 3,
        "created_at": "2023-01-13T14:47:12.000000Z",
        "updated_at": "2023-01-13T14:47:14.000000Z"
    }
]
```
##### GET:  `http://127.0.0.1:8000/api/v1/notification/{id}`
	returns the specific notifications where notifications id equals the given params.

##### POST: `http://127.0.0.1:8000/api/v1/notification`
	returns the notification that has been just saved.

##### PUT: `http://127.0.0.1:8000/api/v1//notification/{id}`
	finds the user with the id and updates the fields of the specific notification.

##### DELETE: `http://127.0.0.1:8000/api/v1//notification/{id}`
	finds the user with the id and delete the notification with the id(id of notification not user), it is not working till now.
