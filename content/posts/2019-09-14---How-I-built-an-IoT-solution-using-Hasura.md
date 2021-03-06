---
title: How I built an IoT solution using Hasura?
date: "2019-09-14T22:40:32.169Z"
template: "post"
draft: false
slug: "iot-solution-using-hasura"
category: "IoT"
tags:
  - "GraphQL"
  - "Hasura"
  - "IoT"
description: "Thought of sharing this experience because I think it can change the traditional thought process of GraphQL and a bit of IoT."
socialImage: "/media/hasura/hasura-iot.jpg"
---

# How I built an IoT solution using Hasura?

> “Thought of sharing this experience because I think it can change the traditional thought process of GraphQL and a bit of IoT."

The most important thing about any IoT application is real-time capabilities, scalability, speed, and security. I have found Hasura is a wonderful tool for bootstrapping a GraphQL based web application with real-time features.

## Why Hasura?
https://twitter.com/HasuraHQ/status/1139185766976954370

This made me think about IoT possibilities of Hasura as I was working on it.
&nbsp;
However, for on-premise IoT & IIoT solutions, we used to design custom server which will have required features of an IoT platform.
Mostly the scalability, thread safety, non-blocking pattern, queueing, etc.
&nbsp;
I found Hasura can be replaced with any of the blocks in the design which I am making.
&nbsp;
When I decided to try Hasura, it was more of a GraphQL teacher to me, It is well documented, Good-Tutorials and sample projects, quick setup and it's production-ready.
>I could set up and write my first mutation in less than one hour (Though I had no much idea about GraphQL that time)

## IoT Solutions — What all we need to think?
High-frequency Data Ingestion
Frequency of requests on a non-blocking IoT system is very much unpredictable and it needs to be balanced using a queueing & buffering system.

An IoT application/platform should be capable to accept high-frequency data ingestion. especially when the edge devices have the offline capabilities we may not be able to predict or limit the number of requests per second.
This high frequent data ingestion should be non-blocking so that we will be able to horizontally scale and queue the system accordingly.

## High-frequency Data Ingestion
Frequency of requests on a non-blocking IoT system is very much unpredictable and it needs to be balanced using a queueing & buffering system.

An IoT application/platform should be capable to accept high-frequency data ingestion. especially when the edge devices have the offline capabilities we may not be able to predict or limit the number of requests per second.
This high frequent data ingestion should be non-blocking so that we will be able to horizontally scale and queue the system accordingly.

## Data Buffering and Queueing
Queuing and data buffering is very important for any IoT solutions, which will make sure that the data is not lost anywhere even when there is high traffic.

For this, I have leveraged Apache-Nifi to buffer and queue the data using an MQTT plugin.
Custom JAVA processor will decrypt the payload and pass on to the next block.
If I use only Hasura as IoT backend (maybe Small IoT solutions) Hasura events can be directly used to trigger microservices and anomaly detection.

## High-speed READ/WRITE

I wrote a simple client which will write data into DB.
Fun with Hasura is, I was able to write this using most of my favorite programming languages.
I could show that Hasura could write ~1000 requests/per second which is pretty decent for a small/medium scale IoT solution ( and it is scalable :) )

## Events, Subscriptions more like AWS services but on-premise :)
When I was writing cloud-based solutions, I could leverage more events and subscriptions on most of the places to make sure nowhere the thread is getting blocked or overloaded.
I could simplify these events and subscriptions using Hasura even in on-premise solutions.

## Current IoT Agents (custom software/firmware which runs on IoT Device)
Unlike the old IoT devices, current IoT devices are smart enough with more processing capabilities, edge analytics, more advanced connectivity, etc.

Gateway — A server which controls & fetch data from the devices using lightweight protocol & connect to the cloud
Usually, when many low footprint devices need to be connected to the cloud, we usually introduce Gateways which is usually smart enough to process and handle any advanced Protocols.
Especially the gateways are pretty much advanced to run any of the general-purpose programming languages.
Though I have used MQTT as the gateway< = >cloud communication protocol, I can try Hasura GraphQL socket connection for small scale IoT Solution (Quick Bootstrap and less Time To Production Startups, think about it ).

## Finally Visualization — The UI
Here is where I could save a lot of time. I have used ReactJS to develop the realtime visualization and admin panel.
Realtime charts & Grids with ReactJS-GraphQL is super cool and super fast.
Health monitoring, visualizing anomalies, asset tracking, and sensor data visualization can be made much faster, real-time and performant using GraphQL.
Moreover, I found a few sample projects on GraphQL mutations, and subscriptions from Hasura Team to develop this faster.

## Conclusion
GraphQL with Hasura can actually act as an IoT server, It can accept requests, write data to DB, manage socket connections, trigger events to microservices or webhooks, detect anomalies by writing a microservice (external).
For medium/high scale applications low profile protocols can be used for IoT data transfer and a Hasura node can be used as the Server for admin panel & data visualization.