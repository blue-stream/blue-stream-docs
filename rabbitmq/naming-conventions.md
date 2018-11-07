# RabbitMQ

## Exchange
Currently we use 1 exchange named `application` with `topic` type

## Pattern
Pub/Sub | Observable pattern is used

## Details
Every microservice has queue per required action.
Each microservice can subscribe and publish to multiple queues.
Each queue contains messages of only <b>one</b> job type.

## Naming Conventions

Every event will have the following structure: `entity.action.status`

* Entity - name of entity

* Statuses
    * succeeded
    * failed
    * pending

* Queues
    * nameOfMicroservice-action-queue
