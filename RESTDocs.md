# Reference documentation

## About

This document is my solution for the final exercise from the **Learn API Technical Writing 2: REST for Writers** course. It includes documenting POST and GET requests for a fictitious dating service platform.

This document doesn't have Authorization section nor it's planned to have one in the future. The note in the Value filed is just added as it would be described in a real document.

### Uploading a Sound File to the current User’s Profile

**POST** `https://api.sounddate.com/profile/sound`

#### POST Headers

| Header name | Description | Required | Value |
|-----------|-------------|----------|-------|
| **Bearer** | Access token | Yes | See *Authorization section* |
| **Content-Type** | Sound file format | No | audio/mpeg, audio/x-wav. Default is audio/mpeg. |
| **Accept** | Response format | No | application/json, application/xml. Default is application/json. |

#### POST body

The POST body is the sound file.<br>
The sound file must be 5 minutes or shorter.

##### POST Sample request

POST `https://api.sounddate.com/profile/sound`

Bearer: {**Access token**}<br>
Content-type: audio/mpeg<br>
Accept: application/json<br>

{ myNewSoundFile.mpeg }

#### POST Response elements

| Element | Description | Type |
|-----------|-------------|----------|
| **id** | The **Id** of the new sound file. | integer |
| **length** | The **length** of the sound file in seconds | float |

##### POST Sample response

````json
{
  id:{Id}
  length: 180.24
}
````

### Retrieving Sound File list for a User

**GET** `https://api.sounddate.com/user/{user id}/profile/sound`<br>
where {user id} is the **Id** of the user whose profile contains the sound file/s.

#### GET Headers

| Header name | Description | Required | Value |
|-----------|-------------|----------|-------|
| **Bearer** | Access token | Yes | See *Authorization section* |
| **Accept** | Response format | No | application/json, application/xml. Default is application/json. |

#### GET Query parameters

| Parameter | Description | Type | Required | Notes |
|-----------|-------------|----------|-------|------|
| **sortOrder** | indicates the result order | string | No |Values: mostRecent, earliest, longest, shortest. Default is mostRecent |

**Note:**

* **mostRecent** sorts most recent to earliest
* **earliest** sorts earliest to most recent
* **shortest** sorts shortest to longest
* **longest** sorts longest to shortest

##### GET Sample request

GET `https://api.sounddate.com/user/12345/profile/sound?sortOrder=earliest`

Bearer: {**Access token**}<br>
Accept: application/json<br>

##### GET response elements

<table>
  <th colspan="2">
    Element
  </th>
  <th>
    Description
  </th>
    <th>
    Type
  </th>
  <tr>
    <td colspan="2">soundFiles</td>
    <td>List of user's sound files</td>
    <td>Array</td>
  </tr>
  <tr>
    <td></td>
    <td>id</td>
    <td><b>Id</b> of the sound file</td>
    <td>integer</td>
  </tr>
  <tr>
    <td></td>
    <td>url</td>
    <td>The URL of the sound file</td>
    <td>string</td>
  </tr>
  <tr>
    <td></td>
    <td>length</td>
    <td>The length of the file in seconds</td>
    <td>float</td>
  </tr>
</table>

##### GET Sample response

````json
{
  "soundFiles": [
    {
    "id": 23456,
    "url": "https://api.sounddate.com/profile/sound/23456.mp3",
    "length": 11.2
    },
    {
    "id": 24559,
    "url": "https://api.sounddate.com/profile/sound/24559.mp3",
    "length": 19.8
    }
  ]
}
````

#### Status Codes and Errors

| Code | Description | Notes |
|-----------|-------------|----------|
| 200 | OK | The request is successful |
| 401 | Unauthorized | Access token is invalid/expired |
| 413 | Content too large | The file for POST method is too long |
