# Device OTA Update

IoTaaP OTA Update gives you the possibility to deploy your new firmware to the
device remotely. 

## Get latest firmware version

Returns the latest firmware version in jSON format. It is used to trigger device update

**URL** : `https://ota.iotaap.io/v1/ota/device/latest/{device-id}`

**Method** : `GET`

**Auth required** : NO

**Path Params**

- {device-id} `(string)`: specific device ID

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

**Condition** : If devices resources are not available at the moment

**Code** : `404 NOT FOUND`

**Content** :

```json
{
    "message": "No such device",
    "error": "<Error information>"
}
```

## Download latest firmware

Returns last firmware.bin

**URL** : `https://ota.iotaap.io/v1/ota/device/download/{device-id}{device-token}`

**Method** : `GET`

**Auth required** : NO

**Path Params**

- {device-id}{device-token} `(string)`: specific device ID and token (no spacing)

### Success Response

**Code** : `200 OK`

**Response example**

- Starts *firmware.bin* download instantly

### Error Response

**Condition** : If devices resources are not available at the moment

**Code** : `404 NOT FOUND`

**Content** :

```json
{
    "message": "No such device",
    "error": "<Error information>"
}
```