# API Documentation exercise #

## CRUD operations documenting exercise ##

### Retrieve an album ###

Returns data about a collection of images.

**GET** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to retrieve.

### Retrieve a list of albums ###

Returns a full list of albums.

**GET** `https://example.com/api/v1/album`

### Update an album ###

**PUT** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to update.

### Delete an album ###

**DELETE** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to delete.

### Create an album ###

**POST** `https://example.com/api/v1/album`.

### Print an album ###

**POST** `https://example.com/api/v1/album/{album ID}/print`

where {album ID} is the ID of the album to print.

## Query parameters documenting exercise ##

Here is the information on the query parameters from the developer team:

* startDate. The start date for when the bug was created. Format: YYYY-MM-DD.

* endDate. The end date for when the bug was created. Format: YYYY-MM-DD.

* priority. The priority value. (How important is it.) Integer of 1 to 4, where 1 is the highest priority.

* severity. The severity value. (How big the impact is.) Integer of 1 to 4, where 1 is the most severe.

* status. The status of the bug. Valid values: open, closed, duplicate, notabug.

* start. For pagination, the starting index. Zero is the first bug on the list.

* total. For pagination, the total number of bugs to return.

None of these query parameters are required. The default is all.

## Query parameters documented ##

| Parameter name | Description | Type | Required | Notes |
|-----------|-------------|------|----------|-------|
| **startDate** | The start date when the bug was created | date | No | Format: **YYYY-MM-DD**. The default value is earliest recorded bug. |
| **endDate** | The end date when the bug was created | date | No | Format: **YYYY-MM-DD**. The default value is today. |
| **priority** | The importance of the bug | integer | No | Values of **1** to **4** inclusive. 1 is the highest priority. The default returns all priorities. |
| **severity** | How big the bug impact is | integer | No | Values of **1** to **4** inclusive. 1 is the highest severity. The default returns all severities. |
| **status** | The bug status | string | No | Valid values: **open**, **closed**, **duplicate**, **notabug**. The default returns all statuses. |
| **start** | Pagination starting index | integer | No | Starting index value is **0**. The default is 0. |
| **total** | Total number of bugs to be returned | integer | No | Default value is total number of bugs minus the start value. |