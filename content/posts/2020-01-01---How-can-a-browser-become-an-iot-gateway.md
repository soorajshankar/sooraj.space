---
title: How can a browser become an IoT Gateway?
date: "2020-01-01T22:00:21.123Z"
template: "post"
draft: false
slug: "how-can-a-browser-become-an-iot-gateway"
category: "WebBLE"
tags:
  - "Web"
  - "IoT"
  - "WebBLE"
description: My thoughts on Web BLE and its use cases. Mainly describing about "How can a browser become an IoT Gateway?" and "BLE for Web Authentication."
socialImage: "/media/hasura/hasura-iot.jpg"
---

# Web Bluetooth

> Thought of explainigh few interesting usecases of Web Bluetooth.

## How can a browser become an IoT Gateway?

May be wondering, usually we all use web browsers to access IoT dashboards. But after reading about the new chrome apis and Web Bluetooth I was thinking about the possibilities of using a Web Browser as an ioT Gateway. but yeah i cannot just say that we all need something to substantiate my idea.

### Web Bluetooth

The [Web Bluetooth API](https://developers.google.com/web/updates/2015/07/interact-with-ble-devices-on-the-web). provides the ability to connect and interact with Bluetooth Low Energy peripherals from a web browser.[Docs](https://webbluetoothcg.github.io/web-bluetooth/)

So from this we are clear that, modern browsers can talk to BLE devices directly. This opens a possibility of seeing web browser as an IoT gateway.

### IoT Gateways

Lets see what is an IoT Gateway in simple words and how a browser can be replaced,
IoT Gateway can

- Communicate with embedded devices and IoT Nodes.
  - BLE - Modern Browsers supports this via Web Bluetooth
- Indirectly talk to the sensors, controllers and other I/O devices
  - BLE - Modern Browsers supports this via Web Bluetooth
- Manage Communications with an IoT cloud

  - Proven, Any browser can do this with a pool of supported protocols.
  - Even GraphQL backend can simply act as an IoT Cloud
  - Most of the IoT clouds are supporting javascript SDK’s.

- Data Read/Write Operations, Commands and service executions.

  - Leveraging BLE services and characteristics.
  - With BLE security layer.

- Pre-Processing, Data clean-up, Data Aggregation

  - Huge data processing, caching and storing are already present in modern PWAs.
  - Modern Browser APIs are capable enough to handle this.

- Handling Protocol Conversion.
  - Let’s consider BLE as device communication medium
  - Huge varieties of cloud communication protocols are implemented and supported in modern browsers.
  - MQTT, HTTPs, CoAP, Web Sockets.
  - Directly connect to Kafka, Message Queues, Data Buffers, Apache NiFi, Azure, AWS, Google Cloud and more.
- Handling Data Buffering.
  - Data buffering in gateway level is mostly limited with an external persistent storage.
  - Latest Chrome File system API can read /write data on to the file system. Just like how a firmware is doing
- Offline storage

  - Local Storage API can also be used to store the offline data till an extend.
  - Web SQL, indexed DB and client-side libraries can be used for local storage
  - Native File system API can be used to dump raw data for future reference
  - Fall back mechanism can be written to ensure the data is either successfully sent to the cloud or stored locally.
  - Connectivity callbacks and event handlers are much simpler within the browser.

- Remote Debugging
  - Remote Debugging and analysis is much much simpler with advanced JavaScript analytics tools
  - Chrome allows remote debugging port, so that you can monitor your gateway more like a server.
- BLE Debugging
  - https://developers.google.com/web/updates/2015/07/interact-with-ble-devices-on-the-web#dev_tips

* Edge Computing (Aggregation, Averaging etc.)
  -JavaScript can do this in all modern web browsers.

  - Complex data structures and algorithms are processed in modern PWA’s
  - Threading, Task Queue and Call Stack is managed by the browser :)

* Anomaly detection

  - High frequency data stream can be passed through a trained ML model for anomaly detection.
  - Libraries like TensorflowJS can be used.
  - Realtime retraining logic can also be written.

* Edge Analytics and Predictions
  - Data stream can be passed through the ML models to predict futuristic output.
  - Predictions can be made using AI & ML libraries like tensorflow JS
  - Retraining and replacing new ML models are possible

IoT gateways are something which connects IoT devices and IoT cloud
