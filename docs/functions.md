# IoTaaP HAPI Firmware functions

### configure()
Configure IoTaaP Cloud connection
#### Parameters

 - **deviceID** - Device ID from IoTaaP Cloud
 - **deviceToken** - Device Token from IoTaaP Cloud
 - **mqttServer** - IoTaaP Cloud MQTT server instance
 - **mqttUsername** - MQTT Username from IoTaaP Cloud
 - **mqttPassword** - MQTT Password from IoTaaP Cloud
 - **groupID** - (optional) Group ID from IoTaaP Cloud
 - **groupToken** - (optional) Group Token from IoTaaP Cloud

#### Returns
- `(int)` Returns 0 if successfull

!!! warning "Standalone device VS Group device"
    If groupID and groupToken parameters are defined deviceID parameter will be ignored since all devices will have the same firmware and same deviceID. If *devicePublish* function is still used it will publish to the same device topic. User must implement handling in order to differentiate devices in a group. *publish* function can be
    used to publish data to custom topics.

### devicePublish()
Publishes payload to the device topic

!!! info "Topic name"
    Your topic must start **without** `/`.

#### Parameters

- **payload** - Payload data (recomended: JSON format)
- **uTopic** - Topic to publish data to

#### Returns
- `(int)` Returns 0 if successfull

!!! info "Publishing topic"
    If `devicePublish()` method is used in your firmware it will publish given data to the following topic:

    `/<username>/devices/<device-id>/<topic>`

    In the IoTaaP Console - Device details, you will see messages published to any given `<topic>`.

    `/<username>/devices/<device-id>/#` is the listening endpoint of the IoTaaP console.

    `#` - gives you a subscription to everything except for topics that start with `$`

### publish()
Publish is a feature that gives you possibility to publish various device content to any topic (preceded by `/<username>`).

!!! info "Root topic"
    Root topic (username) will be added automatically. Your topic must start **without** `/`.

#### Parameters

- **payload** - Payload data (recomended: JSON format)
- **uTopic** - Topic to publish data to

#### Returns
- `(int)` Returns 0 if successfull

!!! info "Listening endpoint"
    Listening endpoint for all topics for the specific user is:

    `/<username>/#`

    `#` - gives you a subscription to everything except for topics that start with `$`

### subscribe()
Subscribe to a specific topic. 

!!! info "Root topic"
    Root topic (username) will be added automatically. Your topic must start **with** `/`.

#### Parameters

- **uTopic** - Topic to subscribe to

#### Returns
- `(int)` Returns 0 if successfull

### unsubscribe()
Unsubscribe from a specific topic. 

!!! info "Root topic"
    Root topic (username) will be added automatically. Your topic must start **with** `/`.

#### Parameters

- **uTopic** - Topic to unsubscribe from

#### Returns
- `(int)` Returns 0 if successfull

### apiLoop()
Function that will handle connection to the IoTaaP Cloud. It should be placed under loop() or in a separate thread.
This function keeps MQTT connection alive, publishes current device status and checks for OTA Updates. Default OTA Update check time is 30 seconds. Status info is published every 500 milliseconds.

!!! warning "Work in progress"
    'Send states' feature is still under heavy development and should not be enabled in production code (parameter is set to false by default)

#### Parameters

- **sendStates** - Enable sending input states to the topic: `/<username>/devices/<device-id>/states`

### callbackInnerFunction()
Inner function to be used for remote API-like output controller. Function should be placed at the top of the MQTT callback function.

!!! warning "Work in progress"
    **callbackInnerFunction** function is still in alpha phase and should not be used in production code

#### Parameters

- **topic** - Callback topic parameter (pass `topic` parameter from the MQTT callback function)
- **message** - Callback message parameter (pass `message` parameter from the MQTT callback function)
- **length** - Callback length parameter (pass `length` parameter from the MQTT callback function)