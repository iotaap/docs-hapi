# HAPI Publish

HAPI Publish is a feature that gives you possibility to publish various device content to the predefined topics, and
track your messages through IoTaaP console.

## Publishing topic

If `hapiPublish()` method is used in your firmware it will publish given data to the following topic:

`/<username>/devices/<device-id>/<topic>`

In the IoTaaP Console - Device details you will see messages published to any given `<topic>`.

`/<username>/devices/<device-id>/#` is the listening endpoint of the IoTaaP console.

`#` - gives you a subscription to everything except for topics that start with `$`