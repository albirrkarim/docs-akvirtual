---
title: Platform API
---

## A. Introduction

You can integrate your platform with our platform

We have virtual exhibition platform that can integrated with your platform.

Let me know what you needs, send me message via discord:

Discord username: albirrkarim

## B. How it works

![Overview](./assets/integration_overview.png)
We can integrate our platform.

The image / the video asset will be
stored on your website. So the user will load the assets fast.

Because of the Server Location.

You just send the text about collection (art) detail like:

Name:

Description:

etc...

## C. Steps

1. Sign up

2. Click the `Create Exhibition` Button.

These button will create you example of 1 event, 1 room, 1 form, 4 Collections.

3. See `the form` in [Form Menu](https://akvirtual.id/user/dashboard/forms) to get `form_uuid` token

4. Go to [Integration Setting](https://akvirtual.id/user/dashboard/account/integration) to get `user_uuid` token.

5. Read this docs and make HTTP request

6. Enjoy

## D. HTTP Request

<!-- <details>
  <summary>Show Http Request If Using Laravel</summary>

```php
use Illuminate\Support\Facades\Http;

$response = Http::get('https://api.example.com/data');

if ($response->successful()) {
    $data = $response->json();
    // Process the returned JSON data
} else {
    // Handle the request failure
    $statusCode = $response->status();
    $errorMessage = $response->body();
}
```

</details> -->

### - Get your info and credit available

Method: `GET`

Url: `/user/api/public/integration/{user_uuid}`

<details>
  <summary>Show Example</summary>

For example, your `user_uuid` is `68794b90-4fa2-4b99-9bbb-18b22092d6da`

You will make `GET` request with this URL:

```
https://akvirtual.id/user/api/public/integration/68794b90-4fa2-4b99-9bbb-18b22092d6da
```

Our server will respond with:

```json
{
  "status": true,
  "message": "It works, wellcome to akvirtual.id",
  "user": "AL BIRR SUSANTO",
  "credit": 105
}
```

</details>

### - Get all your rooms

Method: `GET`

Url: `/user/api/public/integration/{user_uuid}/rooms`

<details>
  <summary>Show Example</summary>

Your `user_uuid` is `68794b90-4fa2-4b99-9bbb-18b22092d6da`

You will make `GET` request with this URL:

```
https://akvirtual.id/user/api/public/integration/68794b90-4fa2-4b99-9bbb-18b22092d6da/rooms
```

Our server will respond with:

```json
{
  "current_page": 1,
  "total": 2,
  "last_page": 1,
  "data": [
    {
      "room_id": 9,
      "name": "Room Name 1",
      "description": "Room Description 1",
      "views": 24,
      "status": "publish",
      "created_at": "2023-07-14T09:39:07.000000Z",
      "updated_at": "2023-07-18T03:29:42.000000Z",
      "sum_collections": 2,
      "category": "Category name 1",
      "capacity": 14,
      "room_url": "https://akvirtual.id/eFFC7VM/room-name-1",
      "thumbnail": "https://akvirtual.id/files/a99e05bf-5453-470c-88ce-66c0c092c81b.jpg"
    },
    {
      "room_id": 10,
      "name": "Room Name 2",
      "description": "Room Description 1",
      "views": 0,
      "status": "publish",
      "created_at": "2023-07-18T03:11:14.000000Z",
      "updated_at": "2023-07-18T03:31:14.000000Z",
      "sum_collections": 0,
      "category": "Category name 2",
      "capacity": 14,
      "room_url": "https://akvirtual.id/reMykhR/room-name-2",
      "thumbnail": "https://akvirtual.id/user/storage/roomsThumb/b2c3d5c5-372c-4af3-ab3d-e6d4140bb054.jpg"
    }
  ]
}
```

</details>

### - Store new collection

Method: `POST`

Url: `/user/api/integration/{form_uuid}/collections`

<details>
  <summary>Show Example</summary>

Your `form_uuid` is `dd0f2476-a492-4cf8-b8a7-46a190f95f9e`

You will make `POST` request with this URL:

```
https://akvirtual.id/user/api/public/integration/dd0f2476-a492-4cf8-b8a7-46a190f95f9e/collections
```

Remember you will only send string, with this data collections:

```json
{
  "name": "Collection Name",
  "description": "Collection Description",
  "video": "https://www.youtube.com/watch?v=QQbPIha_MeA",
  "creator": "Jhon",
  "email": "email_name@gmail.com",
  "contact": "623423443234",
  "attachment": "https://your_website.com/files/document.pdf",
  "file": "https://your_website.com/files/poster.png",
  "file_model": "https://your_website.com/files/elephant.glb",
  "file_model_usdz": "https://your_website.com/files/elephant.usdz",
  "room_id": "1"
}
```

Then our server will respond with:

```json
{
  "status":true
}
```

</details>

### - Get detail for some collection

Method: `GET`

Url: `/user/api/integration/{form_uuid}/collections/{collection_id}`

<details>
  <summary>Show Example</summary>

Your `form_uuid` is `dd0f2476-a492-4cf8-b8a7-46a190f95f9e`

You will make `GET` request with this URL:

```
https://akvirtual.id/user/api/public/integration/dd0f2476-a492-4cf8-b8a7-46a190f95f9e/collections/21
```

Our server will respond with:

```json
{
  "status": true,
  "collection": {
    "collection_id": 21,
    "name": "Collection Name",
    "description": null,
    "video": null,
    "creator": "albir",
    "email": null,
    "contact": null,
    "attachment": "https://your_website.com/files/document.pdf",
    "file": "https://your_website.com/files/poster.png",
    "file_model": "https://your_website.com/files/elephant.glb",
    "file_model_usdz": "https://your_website.com/files/elephant.usdz",
    "likes": 0,
    "views": 2,
    "room_id": 9,
    "created_at": "2023-07-15T02:01:51.000000Z",
    "updated_at": "2023-07-16T04:22:50.000000Z"
  }
}
```

</details>

### - Update the collection

Method: `POST`

Url: `/user/api/integration/{form_uuid}/collections/{collection_id}`

<details>
  <summary>Show Example</summary>

Your `form_uuid` is `dd0f2476-a492-4cf8-b8a7-46a190f95f9e`

You will make `POST` request with this URL:

```
https://akvirtual.id/user/api/public/integration/dd0f2476-a492-4cf8-b8a7-46a190f95f9e/collections/21
```

Remember you will only send string, with this data collections:

```json
{
  "name": "Collection Name",
  "description": "Collection Description",
  "video": "https://www.youtube.com/watch?v=QQbPIha_MeA",
  "creator": "Jhon",
  "email": "email_name@gmail.com",
  "contact": "623423443234",
  "attachment": "https://your_website.com/files/document.pdf",
  "file": "https://your_website.com/files/poster.png",
  "file_model": "https://your_website.com/files/elephant.glb",
  "file_model_usdz": "https://your_website.com/files/elephant.usdz",
  "room_id": "1"
}
```

Then our server will respond with:

```json
{
  "status":true
}
```

</details>

### - Delete the collection

Method: `DELETE`

Url: `/user/api/integration/{form_uuid}/collections/{collection_id}`

<details>
  <summary>Show Example</summary>

Your `form_uuid` is `dd0f2476-a492-4cf8-b8a7-46a190f95f9e`

You will make `DELETE` request with this URL:

```
https://akvirtual.id/user/api/public/integration/dd0f2476-a492-4cf8-b8a7-46a190f95f9e/collections/21
```

Then our server will respond with:

```json
{
  "status":true
}
```

</details>

