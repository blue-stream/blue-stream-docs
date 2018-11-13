# RabbitMQ

## Connections
For each microservice instance:
- 1 connection
  - 1 channel for publishing.
  - 1 channel for each consumer.

## Exchange
- name: `application`
- type: `topic`
- durable: true

## Queue
- durable: true 
- ack: true

## Message
### Subscribe
- No `prefetch` by default (can be configured).
- When rejecting (reject / nack) a message use `requeue: false`
- Use `JSON` format (`JSON.parse`)

### Publish
- Use `JSON` format (`JSON.stringify`)
- Each message should have `persistent: true`

## Pattern
Pub/Sub | Observable pattern is used

## Details
Every microservice has queue per required action.
Each microservice can subscribe and publish to multiple queues.
Each queue contains messages of only <b>one</b> job type.

## Naming Conventions

Every event will have the following structure: `sourceMicroservice.action.status`

* Statuses
    * succeeded
    * failed

* Queues
    * nameOfMicroservice-action-queue
