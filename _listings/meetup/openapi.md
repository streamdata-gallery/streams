swagger: "2.0"
x-collection-name: Meetup
x-complete: 1
info:
  title: Meetup
  version: 1.0.0
host: api.meetup.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2/event_comments:
    ws:
      summary: WebSockets Event Comments Stream
      description: |-
        For browsers that support it, [WebSockets](http://dev.w3.org/html5/websockets/) is a more
        efficient alternative to the long-polling stream. This is a **push only** endpoint and will discard
        any messages received from the client after the socket is open.

        Because browser support for WebSockets is limited, we recommend that you consume this stream
        through the [must.js](https://github.com/meetup/must.js#readme) client, which can fallback to long-polling.
      operationId: streams
      x-api-path-slug: 2event-comments-ws
      parameters:
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: event_id
        description: Limit notifications to a specific event id
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Return recent Event Comments with an mtime greater than the supplied
          time, in milliseconds since the epoch
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Comments
  /2/photos:
    ws:
      summary: WebSocket Photo Stream
      description: |-
        For browsers that support it, [WebSockets](http://dev.w3.org/html5/websockets/) is a more
        efficient alternative to the long-polling stream. This is a **push only** endpoint and will discard
        any messages received from the client after the socket is open.

        Because browser support for WebSockets is limited, we recommend that you consume this stream
        through the [must.js](https://github.com/meetup/must.js#readme) client, which can fallback to long-polling.
      operationId: streams
      x-api-path-slug: 2photos-ws
      parameters:
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Return recent photos with an mtime greater then the supplied
          time, in millisends since the epoch
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
      - Albums
  /2/rsvps:
    ws:
      summary: WebSockets RSVP Stream
      description: |-
        For browsers that support it, [WebSockets](http://dev.w3.org/html5/websockets/) is a more
        efficient alternative to the long-polling stream. This is a **push only** endpoint and will discard
        any messages received from the client after the socket is open.

        Because browser support for WebSockets is limited, we recommend that you consume this stream
        through the [must.js](https://github.com/meetup/must.js#readme) client, which can fallback to long-polling.
      operationId: streams
      x-api-path-slug: 2rsvps-ws
      parameters:
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: event_id
        description: Limit notifications to a specific event id
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Return recent RSVPs with an mtime greater than the supplied time,
          in milliseconds since the epoch
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Streaming
      - Websockets
  /2/open_events:
    get:
      summary: OpenEvents
      description: Searches for recent and upcoming public events hosted by Meetup
        groups. Its search window  is the past one month through the next three months,
        and is subject to change. Open Events is optimized to search for current events
        by location, category, topic, or text, and only lists Meetups that have **3
        or more RSVPs**. The number or results returned with each request is not guaranteed
        to be the same as the page size due to secondary filtering. If you're looking
        for a particular event or events within a particular group, use the standard
        [Events](/meetup_api/docs/2/events/) method.
      operationId: events
      x-api-path-slug: 2open-events-get
      parameters:
      - in: query
        name: and_text
        description: Changes the interpretation of the text field from ORd terms to
          ANDd terms
        type: string
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: category
        description: Return events in the specified category or categories specified
          by commas
        type: string
      - in: query
        name: city
        description: A valid city
        type: string
      - in: query
        name: country
        description: A valid country code
        type: string
      - in: query
        name: fields
        description: Request that additional fields (separated by commas) be included
          in the output
        type: string
      - in: query
        name: lat
        description: A valid latitude, limits the returned group events to those within
          radius miles
        type: string
      - in: query
        name: limited_events
        description: Include limited event information for private groups that wish
          to expose only a small amount of information about their events
        type: string
      - in: query
        name: lon
        description: A valid longitude, limits the returned group events to those
          within radius miles
        type: string
      - in: query
        name: radius
        description: Radius, in miles for geographic requests, default 25
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Return events with an mtime greater than the supplied time, in
          milliseconds since the epoch
        type: string
      - in: query
        name: state
        description: If searching in a country with states, a valid 2 character state
          code
        type: string
      - in: query
        name: status
        description: Status may be upcoming, past or both separated by a comma
        type: string
      - in: query
        name: text
        description: Events that contain the given term or terms somewhere in their
          content
        type: string
      - in: query
        name: text_format
        description: Format of the description text, html or plain
        type: string
      - in: query
        name: time
        description: Return events scheduled within the given time range, defined
          by two times separated with a single comma
        type: string
      - in: query
        name: topic
        description: Return events in the specified topic or topics specified by commas
        type: string
      - in: query
        name: zip
        description: A valid US zip code, limits the returned groups to those within
          radius miles
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
  /activity:
    get:
      summary: ActivityFeed
      description: API method for retrieving the activity feed for a member's groups
      operationId: feeds
      x-api-path-slug: activity-get
      parameters:
      - in: query
        name: member_id
        description: Returns activity from this members groups
        type: string
      - in: query
        name: page_start
        description: Starting timestamp for item to return
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Activity
      - Feeds
  /2/categories:
    get:
      summary: Categories
      description: Returns a list of Meetup group categories
      operationId: categories
      x-api-path-slug: 2categories-get
      parameters:
      - in: query
        name: fields
        description: Parameter for requesting optional response properties
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Categories
  /find/upcoming_events:
    get:
      summary: Find Upcoming Events
      description: Returns a list of upcoming events
      operationId: events
      x-api-path-slug: findupcoming-events-get
      parameters:
      - in: query
        name: end_date_range
        description: Return events that start before this date
        type: string
      - in: query
        name: end_time_range
        description: Return events that start before this time
        type: string
      - in: query
        name: excluded_groups
        description: IDs for groups to exclude from the returned events
        type: string
      - in: query
        name: fields
        description: A comma-delimited list of optional fields to populate in the
          response
        type: string
      - in: query
        name: lat
        description: Approximate target latitude
        type: string
      - in: query
        name: lon
        description: Approximate target longitude
        type: string
      - in: query
        name: order
        description: The sort order of returned events
        type: string
      - in: query
        name: page
        description: A target minimum number of events to return in a single page
          of results
        type: string
      - in: query
        name: radius
        description: Radius in miles
        type: string
      - in: query
        name: self_groups
        description: set to include or exclude or only get groups that the member
          belongs to
        type: string
      - in: query
        name: start_date_range
        description: Return events that start after this date
        type: string
      - in: query
        name: start_time_range
        description: Return events that start after this time
        type: string
      - in: query
        name: text
        description: Full text search query
        type: string
      - in: query
        name: topic_category
        description: Numeric topic category identifier for filtering recommendations
          by a topic category
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Search
  /2/concierge:
    get:
      summary: Concierge
      description: Recommends upcoming meetups for the authorized member in a given
        location and in thier groups
      operationId: events
      x-api-path-slug: 2concierge-get
      parameters:
      - in: query
        name: category_id
        description: Comma delimited list of category ids to limit recommendations
          to
        type: string
      - in: query
        name: city
        description: A valid city
        type: string
      - in: query
        name: country
        description: A valid country code
        type: string
      - in: query
        name: fields
        description: Request that additional fields (separated by commas) be included
          in the output
        type: string
      - in: query
        name: lat
        description: A valid latitude, limits the returned group events to those within
          radius miles
        type: string
      - in: query
        name: lon
        description: A valid longitude, limits the returned group events to those
          within radius miles
        type: string
      - in: query
        name: page_token
        description: An opaque string used to page through results
        type: string
      - in: query
        name: radius
        description: Radius, in miles for geographic requests, defaults to the members
          preferred radius or 0
        type: string
      - in: query
        name: self_groups
        description: set to include or exclude groups the authorized member belongs
          to
        type: string
      - in: query
        name: state
        description: If searching in a country with states, a valid 2 character state
          code
        type: string
      - in: query
        name: text_format
        description: Format of the description text, html, plain, or simplehtml
        type: string
      - in: query
        name: time
        description: Return events scheduled within the given time range, defined
          by two times separated with a single comma
        type: string
      - in: query
        name: topic_id
        description: Comma delimited list of topics to help inform recommendation
        type: string
      - in: query
        name: with_friends
        description: Boolean parameter
        type: string
      - in: query
        name: zip
        description: A valid US zip code, limits the returned groups to those within
          radius miles
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events