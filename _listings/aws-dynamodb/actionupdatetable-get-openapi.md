---
swagger: "2.0"
x-collection-name: AWS DynamoDB
x-complete: 0
info:
  title: Amazon DynamoDB API Update Table
  version: 1.0.0
  description: Modifies the provisioned throughput settings, global secondary indexes,
    or DynamoDB Streams settings for a given table.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=UpdateTable:
    get:
      summary: Update Table
      description: Modifies the provisioned throughput settings, global secondary
        indexes, or DynamoDB Streams settings for a given table.
      operationId: updateTable
      x-api-path-slug: actionupdatetable-get
      parameters:
      - in: query
        name: AttributeDefinitions
        description: An array of attributes that describe the key schema for the table
          and indexes
        type: string
      - in: query
        name: GlobalSecondaryIndexUpdates
        description: An array of one or more global secondary indexes for the table
        type: string
      - in: query
        name: ProvisionedThroughput
        description: The new provisioned throughput settings for the specified table
          or index
        type: string
      - in: query
        name: StreamSpecification
        description: Represents the DynamoDB Streams configuration for the table
        type: string
      - in: query
        name: TableName
        description: The name of the table to be updated
        type: string
      responses:
        200:
          description: OK
      tags:
      - Tables
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---