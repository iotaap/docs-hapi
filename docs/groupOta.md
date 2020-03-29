# Group OTA Update

IoTaaP Group OTA Update gives you the possibility to deploy your new firmware to the
multiple devices remotely. 

## Get latest firmware version

Returns the latest firmware version in jSON format. It is used to trigger devices update

**URL** : `https://ota.iotaap.io/v1/ota/group/latest/{group-id}`

**Method** : `GET`

**Auth required** : NO

**Path Params**

- {group-id} `(string)`: specific group ID

### Success Response

**Code** : `200 OK`

**Response example**

```json
{
"ver": "1.0.1"
}
```

**Response Params**

- ver `(string)`: latest firmware version available

### Error Response

**Condition** : If group resources are not available at the moment

**Code** : `404 NOT FOUND`

**Content** :

```json
{
    "message": "No such group",
    "error": "<Error information>"
}
```

## Download latest firmware

Returns last firmware.bin

**URL** : `https://ota.iotaap.io/v1/ota/group/download/{group-id}{group-token}`

**Method** : `GET`

**Auth required** : NO

**Path Params**

- {group-id}{group-token} `(string)`: specific group ID and token (no spacing)

### Success Response

**Code** : `200 OK`

**Response example**

- Starts *firmware.bin* download instantly

### Error Response

**Condition** : If group resources are not available at the moment

**Code** : `404 NOT FOUND`

**Content** :

```json
{
    "message": "No such group",
    "error": "<Error information>"
}
```