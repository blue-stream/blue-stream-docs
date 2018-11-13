# RabbitMQ

## Connections
For each microservice instance:
- we use 2 connections for (for publish and consume).
  - we use 1 channel for publish messages.
  - we use 1 channel for each consumer.

## Exchange
Currently we use 1 exchange named `application` with these settings:
- type: `topic`
- durable: true

## Queue
We use these settings for queues:
- durable: true 
- ack: true

## Message
We use these settings for messages:
- for subscribe, requeue: false
- no prefetch. if you need you can configure the channel to prefetch
- we use JSON format
- for publish, persistent: true

## Pattern
Pub/Sub | Observable pattern is used

## Details
Every microservice has queue per required action.
Each microservice can subscribe and publish to multiple queues.
Each queue contains messages of only <b>one</b> job type.

## Naming Conventions

Every event will have the following structure: `sourceMicroservice.action.status`

* Entity - name of entity

* Statuses
    * succeeded
    * failed
    * pending

* Queues
    * nameOfMicroservice-action-queue
