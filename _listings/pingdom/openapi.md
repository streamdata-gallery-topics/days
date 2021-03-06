swagger: "2.0"
x-collection-name: Pingdom
x-complete: 1
info:
  title: Traceroute API
  description: the-traceroute-api-
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
host: api.pingdom.com
basePath: /
paths:
  ? |2-

        /api/{version}/summary.hoursofday/{checkid}
  : ? |2-

          get
    : summary: Get Response Time Averages For Each Hour Of The Day
      description: Returns the average response time for each hour of the day (0-23)
        for a specific check over a selected time period. I.e. it shows you what an
        average day looks like during that time period.
      operationId: get-response-time-averages-for-each-hour-of-the-day
      x-api-path-slug: apiversionsummary-hoursofdaycheckid-get
      parameters:
      - in: query
        name: from
        description: Start time of period
        type: <td>integer</td>
      - in: query
        name: probes
        description: Filter to only use results from a list of probes
        type: <td>string</td>
      - in: query
        name: to
        description: End time of period
        type: <td>integer</td>
      - in: query
        name: uselocaltime
        description: If true, use the users local time zone for results (from and
          to parameters should still be specified in UTC)
        type: <td>boolean</td>
      responses:
        "":
          description: ""
        400:
          description: Bad input parameter
        401:
          description: Bad or expired token
        403:
          description: Bad OAuth request (wrong consumer key, bad nonce, expired timestamp
        404:
          description: File or folder not found at the specified path
        405:
          description: Request method not expected (generally should be GET or POST)
        429:
          description: Your app is making too many requests and is being rate limited
        503:
          description: If the response includes the Retry-After header, this means
            your OAuth 1
        507:
          description: User is over Dropbox storage quota
        5xx:
          description: Server error
      tags:
      - Summary