# Device Status 

This feature gives you the possibility to track your device(s) current state like battery percentage, uptime, firmware version and similar. This feature
is integrated as te core feature of our HAPI library. 

## Publishing device state

By default hardware that uses IoTaaP HAPI library will have Device Status feature enabled. Device will periodically publish its state to the following topic:

`/<username>/devices/<device-id>/status`

!!! danger "Topic usage"
    You should **NOT** use this topic in any other application that will publish information to it, because this can cause 
    your application to break unexpectedly. Any information that is published to this topic will be ignored by the device, except
    when this kind of implementation is done manually.

### Message format

Our HAPI Library uses JSON as the default format for published messages. Status message is predefinded by HAPI Library:

```json
{
    "battery": 78,
    "uptime": 1343,
    "api_version": "1.2.5",
    "fw_version": "2.5.7",
    "sent": 246184551,
    "received": 131,
    "disconnects": 2
}
```

**Message parameters**

- battery `(number)`: current battery percentage (%)
- uptime `(number)`: time since power-up in seconds
- api_version `(string)`: IoTaaP HAPI Library version
- fw_version `(string)`: your firmware version
- sent `(number)`: number of sent messages since power-up
- received `(number)`: number of received messages since power-up
- disconnects `(number)`: number of communication disconnects