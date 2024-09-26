# PhantasticFoto API Docs #

## Retrieve an album ##

Returns data about a collection of images.

**GET** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to retrieve.

## Retrieve a list of albums ##

Returns a full list of albums.

**GET** `https://example.com/api/v1/album`

## Update an album ##

**PUT** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to update.

## Delete an album ##

**DELETE** `https://example.com/api/v1/album/{album ID}`

where {album ID} is the ID of the album to delete.

## Create an album ##

**POST** `https://example.com/api/v1/album`.

## Print an album ##

**POST** `https://example.com/api/v1/album/{album ID}/print`

where {album ID} is the ID of the album to print.
