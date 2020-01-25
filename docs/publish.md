# Publish

Publish is a feature that gives you possibility to publish various device content to any topic (preceded by `/<username>`). In the
backround this function sends data to the IoTaaP MQTT server.

## Listening endpoint

Listening endpoint for all topics for the specific user is:

`/<username>/#`

`#` - gives you a subscription to everything except for topics that start with `$`