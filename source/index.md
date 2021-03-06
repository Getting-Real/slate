---
title: API Reference

language_tabs:
  - json
  - objc

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Saleswhale API! You can use our API to access Saleswhale API endpoints, which can get information on various sea creatures, kittens, and flurry creatures in our database.

We have language bindings in Shell, Ruby, and Objective-C! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

Let's get started!

# Users

## Get all Users

> The GET request returns JSON structured like this:

```json
{
"users": [
    {
        "id": 2,
        "email": "venus@gettingrail.com",
        "full_name": "Venus Wong",
        "designation": null,
        "username": "venuswong",
        "avatar": {
            "avatar": {
                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/2/163311_10150904439229417_1696384027_n.jpg",
                "thumb": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/2/thumb_163311_10150904439229417_1696384027_n.jpg"
                },
                "medium": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/2/medium_163311_10150904439229417_1696384027_n.jpg"
                }
            }
        },
        "created_at": "2015-02-10T14:23:29.253Z",
        "updated_at": "2015-02-10T14:23:29.253Z"
    },
    {
        "id": 1,
        "email": "gabriel@gettingrail.com",
        "full_name": "Gabriel Lim",
        "designation": null,
        "username": "gabriel",
        "avatar": {
            "avatar": {
                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/lopsgabriel.jpeg",
                "thumb": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/thumb_lopsgabriel.jpeg"
                },
                "medium": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/medium_lopsgabriel.jpeg"
                }
            }
        },
        "created_at": "2015-02-12T10:49:09.097Z",
        "updated_at": "2015-02-12T10:49:09.097Z"
        },
    {
        "id": 3,
        "email": "junxiu92@gmail.com",
        "full_name": "Jun Xiu",
        "designation": null,
        "username": "junxiu",
        "avatar": {
            "avatar": {
                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/3/522113_10204661884160564_4985269855251419777_n.jpg",
                "thumb": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/3/thumb_522113_10204661884160564_4985269855251419777_n.jpg"
                },
                "medium": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/3/medium_522113_10204661884160564_4985269855251419777_n.jpg"
                }
            }
        },
        "created_at": "2015-02-02T07:39:18.305Z",
        "updated_at": "2015-02-02T07:39:18.305Z"
    }]
}
```

This endpoint retrieves all users for the organisation the requesting user is in.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/users`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the requesting user

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
id | The ID of the user.
email | The email_address of the user. Note that this is the profile email that the user uses to sign in, and need not necessarily represent the Gmail email accounts that the user linked with their profile.
full_name | The user's full name
designation | The user's post in the company, be it CEO, Designer or Sales Executive (optional).
username | The username of the user. Usernames are used for @mentioning, and are unique per organisation.
avatar | The profile image of the user. Comes in 3 flavors, normal, thumb and medium.



## Get a User

> The GET request returns JSON structured like this:

```json
{
"user": {
        "id": 1,
        "email": "gabriel@gettingrail.com",
        "full_name": "Gabriel Lim",
        "designation": null,
        "username": "gabriel",
        "avatar": {
            "avatar": {
                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/lopsgabriel.jpeg",
                "thumb": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/thumb_lopsgabriel.jpeg"
                },
                "medium": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/medium_lopsgabriel.jpeg"
                }
            }
        },
        "created_at": "2015-02-12T10:49:09.097Z",
        "updated_at": "2015-02-12T10:49:09.097Z"
    }
}
```

This endpoint retrieves a particular User.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/users/{:id}`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the requesting user
{:id}   | The id parameter of the User that you want to retrieve

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
id | The ID of the user.
email | The email_address of the user. Note that this is the profile email that the user uses to sign in, and need not necessarily represent the Gmail email accounts that the user linked with their profile.
full_name | The user's full name
designation | The user's post in the company, be it CEO, Designer or Sales Executive (optional).
username | The username of the user. Usernames are used for @mentioning, and are unique per organisation.
avatar | The profile image of the user. Comes in 3 flavors, normal, thumb and medium.











# Contacts

## Get all Contacts

> The GET request returns JSON structured like this:

```json
{
"contacts": [
        {
            "id": 9,
            "organisation_id": 1,
            "full_name": "Zoey Nguyen",
            "primary_email": "zoey@methodnow.com",
            "account": {
                "id": 2,
                "company_name": "Method",
                "industry": "Software",
                "description": "Method is a design-centered software company. We make friendly, useful products. We started the company because we believe that technology should be used to solve problems that matter and be enjoyed by everyone. We love the web and working with new technology. Companies we have worked with include Samsung, National Youth Council, Ministry of Education, McKinsey & Company, Ritual and NUS.",
                "created_at": "2015-02-08T21:17:00.322Z",
                "updated_at": "2015-02-08T21:17:00.322Z",
                "organisation_id": 1,
                "saleswhale_company_id": 2749069
            },
            "designation": null,
            "first_added_by_user_id": 1,
            "default_avatar_url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/contact/default_avatar/9/contact-9.png",
            "created_at": "2015-01-16T07:25:21.247Z",
            "updated_at": "2015-02-08T21:17:00.328Z"
            },
        {
            "id": 3,
            "organisation_id": 1,
            "full_name": "Ethan Le Duc Toan",
            "primary_email": "ductoanle@gmail.com",
            "account": null,
            "designation": null,
            "first_added_by_user_id": 1,
            "default_avatar_url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/contact/default_avatar/3/contact-3.png",
            "created_at": "2015-01-16T07:25:21.179Z",
            "updated_at": "2015-01-25T19:59:11.876Z"
        }
   ]
}
```

This endpoint retrieves all Contacts for the organisation the requesting user is in.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/contacts`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the requesting user

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
id | The ID of the user.
organisation_id | The organisation that the contact belongs to.
full_name | The full name of the contact.
primary_email | The primary email address of the contact. This is normally populated by the Gmail Contacts API but can be manually populated too. Very important because this is how we pull and match emails under this contact, and do automated matching of which account they belong to.
account | The account that the contact belongs to. If contact does not belong to an account, then the value is null.
designation | The contact's position, be it CEO, Designer or Sales Executive (optional).
first_added_by_user_id | The contact was first added into the organisation by this user.
default_avatar_url | The default avatar made up of the contact's initials and randomized flat color generated by our server. This should be used if the contact does not have a profile image (coming soon.)



## Get a Contact

> The GET request returns JSON structured like this:

```json
{
"contact": 
        {
            "id": 9,
            "organisation_id": 1,
            "full_name": "Zoey Nguyen",
            "primary_email": "zoey@methodnow.com",
            "account": {
                "id": 2,
                "company_name": "Method",
                "industry": "Software",
                "description": "Method is a design-centered software company. We make friendly, useful products. We started the company because we believe that technology should be used to solve problems that matter and be enjoyed by everyone. We love the web and working with new technology. Companies we have worked with include Samsung, National Youth Council, Ministry of Education, McKinsey & Company, Ritual and NUS.",
                "created_at": "2015-02-08T21:17:00.322Z",
                "updated_at": "2015-02-08T21:17:00.322Z",
                "organisation_id": 1,
                "saleswhale_company_id": 2749069
            },
            "designation": null,
            "first_added_by_user_id": 1,
            "default_avatar_url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/contact/default_avatar/9/contact-9.png",
            "created_at": "2015-01-16T07:25:21.247Z",
            "updated_at": "2015-02-08T21:17:00.328Z",
            "newsfeed": [
                {
                    "id": 5191,
                    "interaction_id": 1521,
                    "comment_count": 0,
                    "comments": [ ],
                    "published_datetime": "2015-02-12T13:35:09.646Z",
                    "verb": "posted_note",
                    "actor": {
                        "actorType": "user",
                        "id": 1,
                        "displayName": "Gabriel Lim",
                        "image": {
                            "thumbnail": {
                                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/thumb_lopsgabriel.jpeg"
                            },
                            "original": {
                                "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/lopsgabriel.jpeg"
                            }
                    },
                    "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/collaborators/1"
                    },
                    "object": {
                        "objectType": "Note",
                        "id": 113,
                        "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/notes/113",
                        "displayName": "This is a note with 1 attachment"
                    },
                    "targets": [
                        {
                            "targetType": "contact",
                            "id": 1,
                            "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/1",
                            "displayName": "Nadine Keller"
                        }
                    ],
                    "privacy": {
                        "default": 0,
                        "allowed_users": [ ]
                    }
                }
            ]
        }
}
```

This endpoint retrieves an individual Contact. The contact's related interactions are included here as well, which is omitted inside the Get all Contacts endpoint.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/contact/{:id}`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the requesting user
{:id}   | The id parameter of the User that you want to retrieve

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
id | The ID of the user.
organisation_id | The organisation that the contact belongs to.
full_name | The full name of the contact.
primary_email | The primary email address of the contact. This is normally populated by the Gmail Contacts API but can be manually populated too. Very important because this is how we pull and match emails under this contact, and do automated matching of which account they belong to.
account | The account that the contact belongs to. If contact does not belong to an account, then the value is null.
designation | The contact's position, be it CEO, Designer or Sales Executive (optional).
first_added_by_user_id | The contact was first added into the organisation by this user.
default_avatar_url | The default avatar made up of the contact's initials and randomized flat color generated by our server. This should be used if the contact does not have a profile image (coming soon.)
newsfeed | The related interactions for this particular contact. Refer to Newsfeed documentation for more information on the sub-properties.






























# Newsfeed

## Get the Newsfeed

> The GET request returns JSON structured like this:

```json
{
"newsfeed_items": [
    {
        "newsfeed_id": 2951,
        "interaction_id": 1242,
        "comment_count": 0,
        "published_datetime": "2015-01-18T09:18:49.936Z",
        "verb": "logged_meeting",
        "actor": {
            "actorType": "user",
            "id": 1,
            "displayName": "Gabriel Lim",
            "image": {
                "thumbnail": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/thumb_lopsgabriel.jpeg"
                },
                "original": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/lopsgabriel.jpeg"
                }
            },
            "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/collaborators/1"
        },
        "object": {
            "objectType": "Event",
            "id": 1,
            "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/events/1",
            "displayName": "Talked about project"
        },
        "targets": [
            {
                "targetType": "contact",
                "id": 180,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/180",
                "displayName": "Chen Sung, Lai"
            },
            {
                "targetType": "contact",
                "id": 491,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/491",
                "displayName": "Ain Ebrahim"
            },
            {
                "targetType": "contact",
                "id": 46,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/46",
                "displayName": "Aizat Omar"
            },
            {
                "targetType": "contact",
                "id": 468,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/468",
                "displayName": "Ahmad"
            },
            {
                "targetType": "contact",
                "id": 493,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/493",
                "displayName": "Ang Ying Xin"
            }
        ],
        "privacy": {
            "default": 0,
            "allowed_users": [ ]
        }
    },
    {
        "newsfeed_id": 2949,
        "interaction_id": 1241,
        "comment_count": 1,
        "published_datetime": "2015-01-18T06:21:53.000Z",
        "verb": "emailed",
        "actor": {
            "actorType": "user",
            "id": 1,
            "displayName": "Gabriel Lim",
            "image": {
                "thumbnail": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/thumb_lopsgabriel.jpeg"
                },
                "original": {
                    "url": "https://saleswhale-reboot-production.s3.amazonaws.com/uploads/user/avatar/1/lopsgabriel.jpeg"
                }
            },
            "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/collaborators/1"
        },
        "object": {
            "objectType": "EmailMessageMetadatum",
            "id": 1381,
            "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/email_message_metadata/1381",
            "displayName": "Hi Marilyn, Could we reschedule the meeting on Thursday to 3.30 pm? Sorry about it as we have"
        },
        "targets": [
            {
                "targetType": "contact",
                "id": 159,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/contacts/159",
                "displayName": "Marilyn Tan Mei Xuan"
            },
            {
                "targetType": "user",
                "id": 2,
                "schema_url": "http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/collaborators/2",
                "displayName": "Venus Wong"
            }
        ],
        "privacy": {
            "default": 0,
            "allowed_users": [ ]
        }
    }]
}
```

This endpoint retrieves the Newsfeed for a particular user.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/newsfeed`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
page       | The page number to retrieve (default - returns 10 newsfeed items)

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
newsfeed_id | The ID of the newsfeed item. Not important, as it's just for reference. (Newsfeed objects are just in-memory hashes for performance.)
interaction_id | The ID of the base interaction item. **Important.** You will be using this to reference comments, stars, privacy and the full body of the interaction.
comment_count | The number of comments on this particular interaction
published_datatime | When the interaction occurred. Use this to show the 'how long ago'. This published_datetime automatically calculates when a task is completed, event/note was logged, and the timestamp of when emails were received.
actor | The person who generated this interaction. This person can be either a contact or a user. Currently contact-generated interactions are only limited to incoming emails.
object | The nature of the interaction, which includes the type, and the body/snippet that you can display, which is referenced in the displayName of the object.
targets | An array of the target of the interactions. For example, people who attended the meeting, people who are receipents of the emails, notes about a contact etc..
privacy | A hash, which has two properties - default and allowed_users. Default is the default privacy setting of the interaction. 0 is everyone can see. 1 is only can see the activity snippet, and 2 is private only to you. In the future, allowed_users will be computed first, then all other users who are not in allowed_users will take the default privacy settings.



# Notes

## Create a Note  

```json
{
  "auth_token" : "Bnykjzgsmza3cGMt9qBV",
  "note" : {
    "body" : "This is a note that contains a whale."
  }
}
```

> The above command returns JSON structured like this:

```json
{
    "status": 1,
    "note": {
        "id": 2,
        "body": "This is a note that contains a whale.",
        "contact_id": 773,
        "created_at": "2014-12-10T14:38:03.081Z",
        "updated_at": "2014-12-10T14:38:03.081Z"
    }
}
```

This endpoint creates a Note.

A Note is a body of text that can be posted by a user, and it must have a Contact reference. This Contact reference refers to the Contact that the Note is about.

A Note can have multiple file attachments.

### HTTP Request

`POST http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/notes`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
note | The following parameters are required - `body` and `contact_id`

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Attach a File Asset

```json
{
  "auth_token" : "Bnykjzgsmza3cGMt9qBV",
  "asset" : form-data
}
```

> The above command returns JSON structured like this:

```json
{
    "status": 1,
    "file_asset": {
        "file_url": "https://saleswhale-reboot-production.s3-us-west-2.amazonaws.com/uploads/file_asset/asset/6/larry_ellison.jpg?AWSAccessKeyId=AKIAJMUB6BJTAHZBBSEQ&Signature=ZpHVkqbKgqy2hybVW4EaOpuLC1s%3D&Expires=1418223687",
        "user": {
            "id": 1,
            "email": "gabriel@gettingrail.com",
            "created_at": "2014-12-09T06:30:34.477Z",
            "updated_at": "2014-12-10T08:17:36.888Z",
            "full_name": "Gabriel Lim",
            "designation": "Whale",
            "organisation_id": 1
        },
        "note": {
            "id": 1,
            "body": "This is a note that contains a whale.",
            "contact_id": 773,
            "primary_owner_id": 1,
            "created_at": "2014-12-10T08:30:46.581Z",
            "updated_at": "2014-12-10T08:30:46.581Z"
        },
        "file_type": "image/jpeg",
        "file_size": 10908
    }
}
```

This endpoint attaches a file asset to a Note. The file asset can be of any content type - the server will parse and have it's own handling logic for certain content type. 

Currently, each individual asset cannot exceed 20MB in size. This may be revised in the future when we have more resources.

<aside class="warning">The Content-Type of the HTTP request in should be multipart/form-data.</aside>

### HTTP Request

`POST http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/v1/notes/{:id}/file_assets`

### URL Parameters

Parameter | Description
--------- | -----------
{:id} | The ID of the Note object to attach the file asset to
auth_token | The authentication token to identify the user
asset | The attached file in `multipart/form-data` format



# Tasks

## Create a Task  

```json
{
  "auth_token" : "Bnykjzgsmza3cGMt9qBV",
  "task" : {
    "body" : "This is a task that contains a whale.",
    "contact_id" : 779,
    "due_date" : "2014-12-10T14:38:03.081Z"
  }
}
```

> The above command returns JSON structured like this:

```json
{
    "status": 1,
    "task": {
        "id": 2,
        "body": "This is a note that contains a whale.",
        "due_date" : "2014-12-10T14:38:03.081Z"
        "contact_id": 773,
        "completed": false,
        "completed_at": nil,
        "primary_owner_id": 11,
        "created_at": "2014-12-10T14:38:03.081Z",
        "updated_at": "2014-12-10T14:38:03.081Z"
    }
}
```

This endpoint creates a Task.

A Task is a to-do added by a user, and it must have a Contact reference. This Contact reference refers to the Contact that the Task is about.

A Task can be assigned to other Users.

### HTTP Request

`POST http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/tasks`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
task | The following parameters are required - `body` and `contact_id` and the following parameters are optional -  `due_date` and `task_assignee_ids`

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Update a Task  

```json
{
  "auth_token" : "Bnykjzgsmza3cGMt9qBV",
  "task" : {
    "completed" : true
  }
}
```

> The above command returns JSON structured like this:

```json
{
    "status": 1,
    "task": {
        "id": 2,
        "body": "This is a task that contains a whale.",
        "contact_id": 773,
        "completed": true,
        "completed_at": "2015-01-26T07:51:52.433Z",
        "primary_owner_id": 11,
        "created_at": "2014-12-10T14:38:03.081Z",
        "updated_at": "2014-12-10T14:38:03.081Z"
    }
}
```

This endpoint updates a Task.

You can change the completed status of the Task here, as well as the due date and body. However, I don't think we want to allow people to change the contact_id of the Task for now, just delete and re-create if that's the case.

### HTTP Request

`PUT http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/tasks/15`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
task | The following parameters are options - `completed` and `due_date`

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>







# Search

## Universal Search for Contacts, Users and Documents

> The GET request returns JSON structured like this:

```json
{
    "status": 1,
    "results": {
        "users": [
            {
                "id": 11,
                "avatar": {
                    "url": "/uploads/user/avatar/11/lopsgabriel.jpeg",
                    "thumb": {
                        "url": "/uploads/user/avatar/11/thumb_lopsgabriel.jpeg"
                    },
                    "medium": {
                       "url": "/uploads/user/avatar/11/medium_lopsgabriel.jpeg"
                    }
                },
                "email": "gab.on.rails@gmail.com",
                "created_at": "2015-01-05T06:09:25.728Z",
                "updated_at": "2015-01-15T08:55:35.690Z",
                "full_name": "Crazy Gab",
                "designation": null,
                "organisation_id": 4,
                "username": "crazygab"
            }
        ],
        "contacts": [
            {
                "id": 788,
                "full_name": "Gabriel Lim",
                "primary_email": "gabriel@gettingrail.com",
                "account_id": null,
                "created_at": "2015-01-15T04:30:38.215Z",
                "updated_at": "2015-01-15T04:30:38.215Z",
                "organisation_id": 4,
                "birthday": null,
                "first_added_by_user_id": 11
            }
        ]
    }
}
```

This endpoint searches for Contacts, Users and eventually Documents with full text search.


### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/search`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
q       | The query string, minimum need at least 1 characters before it will trigger the full-text search
scope   | The scope is either 'all', 'contacts' or 'users'. Default is 'all' if scope parameter not provided

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>




# Interaction

## Create a Comment  

```json
{
  "auth_token" : "Bnykjzgsmza3cGMt9qBV",
  "comment" : {
    "comment_text" : "This is a comment on this interaction."
  }
}
```

> The above command returns JSON structured like this:

```json
{
    "status": 1,
    "comment": {
        "id": 30,
        "comment_text": "This is a comment on this interaction.",
        "interaction_id": 531,
        "user_id": 11,
        "created_at": "2015-01-19T15:39:38.526Z",
        "updated_at": "2015-01-19T15:39:38.526Z"
    }
}
```

This endpoint creates a Comment.

A Comment is text that can be posted by a user on an interaction, and it must have a Interaction reference. The Comment is posted to the particular Interaction the user is commenting on.

### HTTP Request

`POST http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/api/v1/interactions/{:interaction_id}/comments`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user
comment | The following parameters are required - `comment_text`

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>



