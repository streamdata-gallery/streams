---
swagger: "2.0"
x-collection-name: Instructure
x-complete: 0
info:
  title: Instructure Canvas Groups API Group activity stream
  description: Group activity stream.
  termsOfService: https://www.canvaslms.com/policies/api-policy
  version: v1
host: canvas.instructure.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /courses/{course_id}/activity_stream:
    get:
      summary: Course activity stream
      description: Course activity stream.
      operationId: course-activity-stream
      x-api-path-slug: coursescourse-idactivity-stream-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Activity
      - Stream
  /courses/{course_id}/activity_stream/summary:
    get:
      summary: Course activity stream summary
      description: Course activity stream summary.
      operationId: course-activity-stream-summary
      x-api-path-slug: coursescourse-idactivity-streamsummary-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Activity
      - Stream
      - Summary
  /groups/{group_id}/activity_stream:
    get:
      summary: Group activity stream
      description: Group activity stream.
      operationId: group-activity-stream
      x-api-path-slug: groupsgroup-idactivity-stream-get
      responses:
        200:
          description: OK
      tags:
      - Groups
      - Group
      - Id
      - Activity
      - Stream
  /groups/{group_id}/activity_stream/summary:
    get:
      summary: Group activity stream summary
      description: Group activity stream summary.
      operationId: group-activity-stream-summary
      x-api-path-slug: groupsgroup-idactivity-streamsummary-get
      responses:
        200:
          description: OK
      tags:
      - Groups
      - Group
      - Id
      - Activity
      - Stream
      - Summary
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