swagger: "2.0"
x-collection-name: MySpace Developers
x-complete: 1
info:
  title: My Space
  description: create-apps-and-games-within-the-myspace-platform--monetize-through-advertising-and-virtual-goods-
  version: 1.0.0
host: api.myspace.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /stream/subscription/@all:
    delete:
      summary: Delete Stream Subscription All
      description: Deletes all subscriptions.
      operationId: stream.subscription._all.delete
      x-api-path-slug: streamsubscriptionall-delete
      parameters:
      - in: query
        name: format
        description: Determines the format of the response
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription
      - '@all'
    get:
      summary: Get Stream Subscription All
      description: Retrieves all subscriptions.
      operationId: stream.subscription._all.get
      x-api-path-slug: streamsubscriptionall-get
      parameters:
      - in: query
        name: format
        description: Determines the format of the response
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription
      - '@all'
  /stream/subscription/{subscriptionId}:
    delete:
      summary: Delete Stream Subscription Subscriptionid
      description: Deletes a subscription.
      operationId: stream.subscription.subscriptionId.delete
      x-api-path-slug: streamsubscriptionsubscriptionid-delete
      parameters:
      - in: query
        name: format
        description: Determines the format of the response
      - in: path
        name: subscriptionId
        description: The subscriptions identifier
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription
      - SubscriptionId
    put:
      summary: Put Stream Subscription Subscriptionid
      description: Updates a subscription.
      operationId: stream.subscription.subscriptionId.put
      x-api-path-slug: streamsubscriptionsubscriptionid-put
      parameters:
      - in: query
        name: Content-Type
        description: Specifies Content Type
      - in: header
        name: Content-Type
        description: Specifies Content Type
      - in: query
        name: format
        description: Determines the format of the response
      - in: path
        name: subscriptionId
        description: The subscriptions identifier
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription
      - SubscriptionId
    get:
      summary: Get Stream Subscription Subscriptionid
      description: Retrieves a subscription.
      operationId: stream.subscription.subscriptionId.get
      x-api-path-slug: streamsubscriptionsubscriptionid-get
      parameters:
      - in: query
        name: format
        description: Determines the format of the response
      - in: path
        name: subscriptionId
        description: The subscriptions identifier
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription
      - SubscriptionId
  /stream/subscription:
    post:
      summary: Post Stream Subscription
      description: Creates a subscription.
      operationId: stream.subscription.post
      x-api-path-slug: streamsubscription-post
      parameters:
      - in: query
        name: Content-Type
        description: Specifies Content Type
      - in: header
        name: Content-Type
        description: Specifies Content Type
      - in: query
        name: format
        description: Determines the format of the response
      responses:
        200:
          description: OK
      tags:
      - Stream
      - Subscription