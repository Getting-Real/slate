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


# Newsfeed

## Get the Newsfeed

> The GET request returns JSON structured like this:

```json
{
    "newsfeed": [
        {
            "post_id": 1,
            "post_snippet": "This is a note that contains a whale.",
            "post_owner": {
                "id": 1,
                "email": "gabriel@gettingrail.com",
                "created_at": "2014-12-09T06:30:34.477Z",
                "updated_at": "2014-12-10T08:17:36.888Z",
                "full_name": "Gabriel Lim",
                "designation": "Whale",
                "organisation_id": 1
            },
            "post_type": "note",
            "post_thumbnail": "http://i239.photobucket.com/albums/ff20/Master-Sayien/vader.jpg",
            "note_detail": {
                "note_id": 1,
                "note_body": "This is a note that contains a whale.",
                "group_id": 1,
                "file_assets": [
                    {
                        "file_url": "https://saleswhale-reboot-production.s3-us-west-2.amazonaws.com/uploads/file_asset/asset/4/GadPoint-Logo_120x120.png?AWSAccessKeyId=AKIAJMUB6BJTAHZBBSEQ&Signature=ep7k1EPavud76T1a7gz3GUQhsio%3D&Expires=1418224130",
                        "file_type": "image/png",
                        "file_size": 13308
                    },
                    {
                        "file_url": "https://saleswhale-reboot-production.s3-us-west-2.amazonaws.com/uploads/file_asset/asset/5/StartuplandHowThreeGuysRisked.acsm?AWSAccessKeyId=AKIAJMUB6BJTAHZBBSEQ&Signature=hR4Evw1JIg%2BeaFpAuDyRSyfC6P8%3D&Expires=1418224130",
                        "file_type": "application/octet-stream",
                        "file_size": 1473
                    },
                    {
                        "file_url": "https://saleswhale-reboot-production.s3-us-west-2.amazonaws.com/uploads/file_asset/asset/6/larry_ellison.jpg?AWSAccessKeyId=AKIAJMUB6BJTAHZBBSEQ&Signature=M4lcPwAZFbpkumXxdo9M7LRqaco%3D&Expires=1418224130",
                        "file_type": "image/jpeg",
                        "file_size": 10908
                    }
                ],
                "note_created_at": "2014-12-10T08:30:46.581Z",
                "note_updated_at": "2014-12-10T08:30:46.581Z"
            },
            "timestamp": "2014-12-10T08:30:46.581Z"
        },
        {
            "post_id": 2,
            "post_snippet": "This is a note that contains a whale.",
            "post_owner": {
                "id": 1,
                "email": "gabriel@gettingrail.com",
                "created_at": "2014-12-09T06:30:34.477Z",
                "updated_at": "2014-12-10T08:17:36.888Z",
                "full_name": "Gabriel Lim",
                "designation": "Whale",
                "organisation_id": 1
            },
            "post_type": "note",
            "post_thumbnail": "http://i239.photobucket.com/albums/ff20/Master-Sayien/vader.jpg",
            "note_detail": {
                "note_id": 2,
                "note_body": "This is a note that contains a whale.",
                "group_id": 1,
                "file_assets": [
                ],
                "note_created_at": "2014-12-10T14:38:03.081Z",
                "note_updated_at": "2014-12-10T14:38:03.081Z"
            },
            "timestamp": "2014-12-10T14:38:03.081Z"
        }
    ]
}
```

This endpoint retrieves the Newsfeed for a particular user.

### HTTP Request

`GET http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/v1/newsfeed`

### Query Parameters

Parameter | Description
--------- | -----------
auth_token | The authentication token to identify the user

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

### Response

Attribute | Description
--------- | -----------
post_id | The ID of the newsfeed post
post_snippet| The snippet of the post to be shown in the newsfeed
post_owner | The user who created the post
post_type | A newsfeed post can be a `note`, `event`, `task`, `goal` and etc..
post_thumbnail | A image thumbnail to use as the background of the post, if any
{:type}_detail | The post detail, e.g. note_detail, when the user taps on the post to see more detail modally
timestamp | The timestamp used to display how long ago the post was created in the newsfeed



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
        "group_id": 1,
        "workspace_id": 1,
        "organisation_id": 1,
        "primary_owner_id": 1,
        "created_at": "2014-12-10T14:38:03.081Z",
        "updated_at": "2014-12-10T14:38:03.081Z"
    }
}
```

This endpoint creates a Note.

A Note is a body of text that can be posted by a user, and it must belong to a Group.

A Note can have multiple file attachments.

### HTTP Request

`POST http://saleswhale-v2-env-tcqj2t2dst.elasticbeanstalk.com/v1/groups/{:id}/notes`

### Query Parameters

Parameter | Description
--------- | -----------
{:id} | The ID of the Group to post the Note in
auth_token | The authentication token to identify the user
note | The following parameters are required - `body`

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
            "group_id": 1,
            "workspace_id": 1,
            "organisation_id": 1,
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



