---
swagger: "2.0"
x-collection-name: Twilio
x-complete: 0
info:
  title: Twilio SendSMS
  description: SendSMS
  termsOfService: https://www.twilio.com/legal/tos
  version: v1
host: api.twilio.com
basePath: /2010-04-01/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /Accounts/{AccountSid}/SMS/Messages.{format}:
    post:
      summary: SendSMS
      description: SendSMS
      operationId: sendsms
      x-api-path-slug: accountsaccountsidsmsmessages-format-post
      parameters:
      - in: path
        name: AccountSid
        description: The ID for the Twilio account
      - in: path
        name: format
        description: By default, Twilios REST API returns XML
      responses:
        200:
          description: OK
      tags:
      - SMS Messages
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