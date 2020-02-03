# Websockets

MQTT Websockets are giving you the possibility to access your data using simple, secured websocket interface. 

## Connection

In order to publish and subscribe to your MQTT instance using websockets you have open a connection. We suggest using 
existing modules or libraries for MQTT WSS, but feel free to use your own implementation. 

| Parameter  |                  Value |
| :--------- | ---------------------: |
| Host       |         mqtt.iotaap.io |
| Port       |                   8084 |
| Path       |                  /mqtt |
| Client ID  |                    any |
| Username   | MQTT instance username |
| Password   | MQTT instance password |
| Keep Alive |                     60 |
| SSL        |                    YES |

!!! note "Host"
    Use the host of your MQTT instance (visible under MQTT Instances in IoTaaP console). MQTT host servers
    are generated based on the current load of our physical servers. 

### Example RAW URL

`wss://mqtt4.iotaap.io:8084/mqtt`