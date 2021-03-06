---
title: "Module Details: connflood (v3)"
---

## The "connflood" Module

### Description

This module throttles excessive connections to the server.

### Configuration

To load this module use the following `<module>` tag:

```xml
<module name="connflood">
```

#### `<connflood>`

The `<connflood>` tag defines settings about how the connflood module should behave. This tag can only be defined once.

Name     | Type     | Default Value                          | Description
-------- | -------- | -------------------------------------- | -----------
bootwait | Duration | 2m *(since 3.4)*<br>10s *(3.0 to 3.3)* | The duration to wait after starting up before connections should be throttled.
maxconns | Number   | *None*                                 | The maximum number of connections to allow before throttling.
period   | Duration | *None*                                 | The duration after which the connection counter is reset.
timeout  | Duration | *None*                                 | The duration to disallow connections for after passing the throttling threshold.
quitmsg  | Text     | *None*                                 | The message to quit throttled users with.

##### Example Usage

```xml
<connflood bootwait="2m"
           maxconns="3"
           period="30s"
           timeout="30s"
           quitmsg="Throttled">
```

#### `<connect>`

This module extends [the core `<connect>` tags](/3/configuration#connect) with the following fields:

Name         | Type    | Default Value | Description
------------ | ------- | ------------- | -----------
useconnflood | Boolean | yes           | [**New in v3.9.0!**](/3/change-log/#inspircd-390) Whether to throttle users in this class when excessive connections are being made to the server.

##### Example Usage

Disables connection flood throttling for users in the BNC class:

```xml
<connect name="BNC"
         ...
         useconnflood="no">
```
