# IoTaaP_HAPI Class Reference

## Constructor

**IoTaaP_HAPI()**  - Construct a new IoTaaP_HAPI object.
#### Parameters

- **fwVersion** Current firmware version (it is used for triggering OTA Update)

## Functions

| **Function**           | **Type** | **Description**                                                                   |
| ---------------------- | -------- | --------------------------------------------------------------------------------- |
| configure              | int      | Configure IoTaaP Cloud connection                                                 |
| devicePublish          | int      | Publishes payload to the device topic                                             |
| publish                | int      | Publishes payload to the topic. Root topic (username) will be automatically added |
| subscribe              | int      | Subscribe to a specific topic. Root topic (username) will be added automatically  |
| unsubscribe            | int      | Unsubscribe from the specific topic                                               |
| apiLoop*               | void     | API function that will publish IoTaaP input states                                |
| callbackInnerFunction* | void     | Inner function to be used for remote API-like output controller                   |
| enableUpdates          | void     | Enables automatic updates (enabled by default)                                    |
| disableUpdates         | void     | Disables automatic updates (enabled by default)                                   |
| checkUpdate            | void     | Checks if new firmware version is available on the server                         |

!!! info "* - WIP"
    **callbackInnerFunction** function is still in alpha phase and should not be used in production code

    **apiLoop** 'send states' feature is still under heavy development and should not be enabled in production code (parameter is set to false by default)