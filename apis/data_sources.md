---
title: Data Sources API
description: APIs to manage data sources and data entries
layout: default
parent: APIs
nav_order: 2
---

Sure, here's an updated version of the documentation for the datasource APIs with examples in curl code and a table for the parameters:

## Data Sources API

### Create Data Source

To create a new data source, send a `POST` request to `https://trypromptly.com/api/datasources`.

**Request:**
```curl
curl -X POST \
     -H "Authorization Token <PROMPTLY_TOKEN>" \
     -H "Content-Type: application/json" \
     -d '{"name": "TestPDF", "type": 3}' \
     https://trypromptly.com/api/datasources
```

| Parameter | Type   | Description               |
| --------- | ------ | ------------------------- |
| name      | string | The name of the data source.|
| type      | int    | The type of the data source. Valid values: 1 (text), 2 (url), 3 (file), 4 (pdf). |

**Response:**

```
{
    "name": "TestPDF",
    "type": {
        "id": 3,
        "name": "PDF",
        "description": "PDF files"
    },
    "uuid": "e8ea333c-1f88-4373-9cb8-4b1da6d7252c",
    "size": 0,
    "created_at": "2023-05-04T02:39:58.202043Z",
    "updated_at": "2023-05-04T02:39:58.206461Z"
}
```

### Delete Data Source

To delete an existing data source, send a `DELETE` request to `https://trypromptly.com/api/datasources/{uuid}`.

**Request:**

```curl
curl -X DELETE \
     -H "Authorization Token <PROMPTLY_TOKEN>" \
     https://trypromptly.com/api/datasources/e8ea333c-1f88-4373-9cb8-4b1da6d7252c
```

| Parameter | Type   | Description                    |
| --------- | ------ | ------------------------------ |
| uuid      | string | The UUID of the data source to be deleted. |

**Response:**

```
{
    "success": true
}
```

### List Data Sources

To list all available data sources, send a `GET` request to `https://trypromptly.com/api/datasources`.

**Request:**

```curl
curl -X GET \
     -H "Authorization Token <PROMPTLY_TOKEN>" \
     https://trypromptly.com/api/datasources
```

**Response:**

```
[
    {
        "name": "TestPDF",
        "type": {
            "id": 3,
            "name": "PDF",
            "description": "PDF files"
        },
        "uuid": "e8ea333c-1f88-4373-9cb8-4b1da6d7252c",
        "size": 0,
        "created_at": "2023-05-04T02:39:58.202043Z",
        "updated_at": "2023-05-04T02:39:58.206461Z"
    },
    {
        "name": "TestText",
        "type": {
            "id": 1,
            "name": "Text",
            "description": "Textual data"
        },
        "uuid": "3cf3ef92-3da0-46d8-8d62-5377e87cb5d5",
       ...
    }
]
```

Sure, here's an example documentation for data entries API including add_dataentry and delete_dataentry:

## Data Entries API

This API allows you to add and delete data entries to a specific data source.

### Authentication

The API requires `promptly_token` authentication header.

### Add Data Entry

Adds a new data entry to the specified data source. The `entry_data` parameter varies based on the data source type. 

#### Endpoint

```
POST https://trypromptly.com/api/datasources/<data_source_uuid>/entries
```

#### Request

```bash
curl -X POST \
  -H 'Content-Type: application/json' \
  -H 'Authorization Token <PROMPTLY_TOKEN>' \
  -d '{
        "entry_data": {
            "name": "<entry_name>",
            "content": "<entry_content>",
            "url": "<entry_url>",
            "file": "<entry_file_base64_encoded>"
        }
    }' \
  https://trypromptly.com/api/datasources/<data_source_uuid>/entries
```

#### Request Parameters

| Parameter | Required | Type   | Description |
|-----------|----------|--------|-------------|
| `entry_data` | Yes | Object | Object containing data entry. Valid keys depend on data source type. |
| `name` | Yes (for text type) | String | Name of the entry. |
| `content` | Yes (for text type) | String | Content of the entry. |
| `url` | Yes (for URL type) | String | URL of the entry. |
| `file` | Yes (for file/PDF type) | String | Base64-encoded file data. |

#### Response

On successful addition, returns HTTP status code `201 Created`.

### Delete Data Entry

Deletes the specified data entry from a data source.

#### Endpoint

```
DELETE https://trypromptly.com/api/datasources/<data_source_uuid>/entries/<entry_uuid>
```

#### Request

```bash
curl -X DELETE \
  -H 'Authorization Token <PROMPTLY_TOKEN>' \
  https://trypromptly.com/api/datasources/<data_source_uuid>/entries/<entry_uuid>
```

#### Request Parameters

| Parameter | Required | Type   | Description |
|-----------|----------|--------|-------------|
| `entry_uuid` | Yes | String | UUID of the data entry to delete. |

#### Response

On successful deletion, returns HTTP status code `204 No Content`.