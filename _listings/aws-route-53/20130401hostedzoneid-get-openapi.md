---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API Get Hosted Zone
  version: 1.0.0
  description: Retrieves the delegation set for a hosted zone, including the four
    name serversassigned to the hosted zone. Send a GET request to the /Amazon Route
    53 APIversion/hostedzone/hosted zone ID             resource.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2013-04-01/delegationset:
    post:
      summary: Create Reusable Delegation Set
      description: Creates a delegation set (a group of four name servers) that can
        be reused by multiplehosted zones. If a hosted zoned ID is specified, CreateReusableDelegationSetmarks
        the delegation set associated with that zone as reusableSend a POST request
        to the /2013-04-01/delegationset resource. The request body must include a
        document with a CreateReusableDelegationSetRequest element.NoteA reusable
        delegation set can't be associated with a private hosted zone/For more information,
        including a procedure on how to create and configure a reusabledelegation
        set (also known as white label name servers), see Configuring White Label
        NameServers.
      operationId: createreusabledelegationset
      x-api-path-slug: 20130401delegationset-post
      parameters:
      - in: body
        name: CallerReference
        description: A unique string that identifies the request, and that allows
          you to retry failedCreateReusableDelegationSet requests without the risk
          of executing theoperation twice
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateReusableDelegationSetRequest
        description: Root level tag for the CreateReusableDelegationSetRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: If you want to mark the delegation set for an existing hosted
          zone as reusable, the IDfor that hosted zone
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
  /2013-04-01/delegationset/Id:
    delete:
      summary: Delete Reusable Delegation Set
      description: Deletes a reusable delegation set. Send a DELETE request to the/2013-04-01/delegationset/delegation
        set ID            resource.Important You can delete a reusable delegation
        set only if there are no associated hostedzones.To verify that the reusable
        delegation set is not associated with any hosted zones, runthe GetReusableDelegationSet
        action and specify the ID of the reusabledelegation set that you want to delete.
      operationId: deletereusabledelegationset
      x-api-path-slug: 20130401delegationsetid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the reusable delegation set you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
    get:
      summary: Get Reusable Delegation Set
      description: Retrieves the reusable delegation set. Send a GET request to the/2013-04-01/delegationset/delegation
        set ID            resource.
      operationId: getreusabledelegationset
      x-api-path-slug: 20130401delegationsetid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the reusable delegation set for which you want to get
          a list of the nameserver
        type: string
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
  /2013-04-01/geolocation?continentcode=ContinentCode&amp;countrycode=CountryCode&amp;subdivisioncode=SubdivisionCode:
    get:
      summary: Get Geo Location
      description: 'Retrieves a single geo location. Send a GET request to the/2013-04-01/geolocation
        resource with one of these options: continentcode |countrycode | countrycode
        and subdivisioncode.'
      operationId: getgeolocation
      x-api-path-slug: 20130401geolocationcontinentcodecontinentcodeampcountrycodecountrycodeampsubdivisioncodesubdivisioncode-get
      parameters:
      - in: path
        name: continentcode
        description: 'Amazon Route 53 supports the following continent codes:                        AF:
          Africa                        AN: Antarctica                        AS:
          Asia                        EU: Europe                        OC: Oceania                        NA:
          North America                        SA: South AmericaLength Constraints:
          Fixed length of 2'
        type: string
      responses:
        200:
          description: OK
      tags:
      - Locations
  ? /2013-04-01/geolocations&amp;maxitems=MaxItems?startcontinentcode=StartContinentCode&amp;startcountrycode=StartCountryCode&amp;startsubdivisioncode=StartSubdivisionCode
  : get:
      summary: List Geo Locations
      description: Retrieves a list of supported geo locations. Send a GET request
        to the/2013-04-01/geolocations resource. The response to this request includes
        aGeoLocationDetailsList element for each location that Amazon Route 53 supports.Countries
        are listed first, and continents are listed last. If Amazon Route 53 supportssubdivisions
        for a country (for example, states or provinces), the subdivisions for thatcountry
        are listed in alphabetical order immediately after the corresponding country.
      operationId: listgeolocations
      x-api-path-slug: 20130401geolocationsampmaxitemsmaxitemsstartcontinentcodestartcontinentcodeampstartcountrycodestartcountrycodeampstartsubdivisioncodestartsubdivisioncode-get
      parameters:
      - in: path
        name: maxitems
        description: (Optional) The maximum number of geolocations to be included
          in the response body forthis request
        type: string
      responses:
        200:
          description: OK
      tags:
      - Locations
  /2013-04-01/healthcheck/HealthCheckId:
    delete:
      summary: Delete Health Check
      description: Deletes a health check. Send a DELETE request to the/2013-04-01/healthcheck/health
        check ID            resource.ImportantAmazon Route 53 does not prevent you
        from deleting a health check even if the health check isassociated with one
        or more resource record sets. If you delete a health check and you don'tupdate
        the associated resource record sets, the future status of the health check
        can't bepredicted and may change. This will affect the routing of DNS queries
        for your DNS failoverconfiguration. For more information, see Replacing and
        Deleting Health Checks in the Amazon Route 53 Developer Guide.
      operationId: deletehealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-delete
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID of the health check that you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
    get:
      summary: Get Health Check
      description: Gets information about a specified health check. Send a GET request
        to the/2013-04-01/healthcheck/health check ID             resource. Formore
        information about using the console to perform this operation, see Amazon
        Route 53 Health Checks and DNS Failover in theAmazon Route 53 Developer Guide.
      operationId: gethealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-get
      parameters:
      - in: path
        name: HealthCheckId
        description: The identifier that Amazon Route 53 assigned to the health check
          when you created it
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
    post:
      summary: Update Health Check
      description: Updates an existing health check.Send a POST request to the /2013-04-01/healthcheck/health
        check ID             resource. Therequest body must include a document with
        an UpdateHealthCheckRequestelement. For more information about updating health
        checks, see Creating, Updating, and DeletingHealth Checks in the Amazon Route
        53 Developer Guide.
      operationId: updatehealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-post
      parameters:
      - in: body
        name: AlarmIdentifier
        description: A complex type that identifies the CloudWatch alarm that you
          want Amazon Route 53 health checkers touse to determine whether this health
          check is healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChildHealthChecks
        description: A complex type that contains one ChildHealthCheck element for
          each healthcheck that you want to associate with a CALCULATED health check
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: EnableSNI
        description: Specify whether you want Amazon Route 53 to send the value ofFullyQualifiedDomainName
          to the endpoint in the client_hellomessage during TLS negotiation
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FailureThreshold
        description: The number of consecutive health checks that an endpoint must
          pass or fail for Amazon Route 53 tochange the current status of the endpoint
          from unhealthy to healthy or vice versa
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FullyQualifiedDomainName
        description: Amazon Route 53 behavior depends on whether you specify a value
          for IPAddress
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want detailed information
        type: string
      - in: body
        name: HealthCheckVersion
        description: A sequential counter that Amazon Route 53 sets to 1 when you
          create a health checkand increments by 1 each time you update settings for
          the health check
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HealthThreshold
        description: The number of child health checks that are associated with a
          CALCULATEDhealth that Amazon Route 53 must consider healthy for the CALCULATED
          health check to beconsidered healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: InsufficientDataHealthStatus
        description: 'When CloudWatch has insufficient data about the metric to determine
          the alarm state, the status that you want Amazon Route 53 to assign to the
          health check:                        Healthy: Amazon Route 53 considers
          the health check to be healthy'
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Inverted
        description: Specify whether you want Amazon Route 53 to invert the status
          of a health check, for example, toconsider a health check unhealthy when
          it otherwise would be considered healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: IPAddress
        description: The IPv4 or IPv6 IP address for the endpoint that you want Amazon
          Route 53 to perform health checks on
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Port
        description: The port on the endpoint on which you want Amazon Route 53 to
          perform health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Regions
        description: A complex type that contains one Region element for each region
          from which you wantAmazon Route 53 health checkers to check the specified
          endpoint
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ResourcePath
        description: The path that you want Amazon Route 53 to request when performing
          health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: SearchString
        description: If the value of Type is HTTP_STR_MATCH orHTTP_STR_MATCH, the
          string that you want Amazon Route 53 to search for in the responsebody from
          the specified resource
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: UpdateHealthCheckRequest
        description: Root level tag for the UpdateHealthCheckRequest parameters
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId/lastfailurereason:
    get:
      summary: Get Health Check Last Failure Reason
      description: If you want to learn why a health check is currently failing or
        why it failed mostrecently (if at all), you can get the failure reason for
        the most recent failure. Send aGET request to the /Amazon Route 53 APIversion/healthcheck/health
        checkID/lastfailurereason resource.
      operationId: gethealthchecklastfailurereason
      x-api-path-slug: 20130401healthcheckhealthcheckidlastfailurereason-get
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want the last failure
          reason
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId/status:
    get:
      summary: Get Health Check Status
      description: Gets status of a specified health check. Send a GET request to
        the/2013-04-01/healthcheck/health check ID/status resource.You can use this
        call to get a health check's current status.
      operationId: gethealthcheckstatus
      x-api-path-slug: 20130401healthcheckhealthcheckidstatus-get
      parameters:
      - in: path
        name: HealthCheckId
        description: If you want Amazon Route 53 to return this resource record set
          in response to a DNS query onlywhen a health check is passing, include the
          HealthCheckId element and specify theID of the applicable health check
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck?marker=Marker&amp;maxitems=MaxItems:
    get:
      summary: List Health Checks
      description: Retrieve a list of your health checks. Send a GET request to the/2013-04-01/healthcheck
        resource. The response to this request includes aHealthChecks element with
        zero or more HealthCheck child elements.By default, the list of health checks
        is displayed on a single page. You can control thelength of the page that
        is displayed by using the MaxItems parameter. You can usethe Marker parameter
        to control the health check that the list beginswith.For information about
        listing health checks using the Amazon Route 53 console, see Amazon Route
        53 Health Checks and DNS Failover.
      operationId: listhealthchecks
      x-api-path-slug: 20130401healthcheckmarkermarkerampmaxitemsmaxitems-get
      parameters:
      - in: path
        name: marker
        description: If the response to a ListHealthChecks is more than one page,
          marker is thehealth check ID for the first health check on the next page
          of results
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/hostedzone:
    post:
      summary: Create Hosted Zone
      description: Creates a new public hosted zone, used to specify how the Domain
        Name System (DNS)routes traffic on the Internet for a domain, such as example.com,
        and its subdomains. ImportantPublic hosted zones can't be converted to a private
        hosted zone or vice versa.Instead, create a new hosted zone with the same
        name and create new resource recordsets.Send a POST request to the /2013-04-01/hostedzone
        resource. The request body must include a documentwith a CreateHostedZoneRequest
        element. The response returns theCreateHostedZoneResponse element containing
        metadata about the hostedzone.Fore more information about charges for hosted
        zones, see Amazon Route 53 Pricing.Note the following:You can't create a hosted
        zone for a top-level domain (TLD).Amazon Route 53 automatically creates a
        default SOA record and four NS records for the zone.For more information about
        SOA and NS records, see NS and SOA Records that Amazon Route 53 Creates for
        a Hosted Zone in the Amazon Route 53 Developer Guide.If your domain is registered
        with a registrar other than Amazon Route 53, you must update thename servers
        with your registrar to make Amazon Route 53 your DNS service. For more information,
        seeConfiguring Amazon Route 53 as your DNSService in the Amazon Route 53 Developer's
        Guide.After creating a zone, its initial status is PENDING. This means that
        itis not yet available on all DNS servers. The status of the zone changes
        to INSYNCwhen the NS and SOA records are available on all Amazon Route 53
        DNS servers. When trying to create a hosted zone using a reusable delegation
        set, specify anoptional DelegationSetId, and Amazon Route 53 would assign
        those 4 NS records for the zone, instead ofallotting a new one.
      operationId: createhostedzone
      x-api-path-slug: 20130401hostedzone-post
      parameters:
      - in: body
        name: CallerReference
        description: A unique string that identifies the request and that allows failedCreateHostedZone
          requests to be retried without the risk of executing theoperation twice
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateHostedZoneRequest
        description: Root level tag for the CreateHostedZoneRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Default
        description: None
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: DelegationSetId
        description: If you want to associate a reusable delegation set with this
          hosted zone, the ID thatAmazon Route 53 assigned to the reusable delegation
          set when you created it
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneConfig
        description: (Optional) A complex type that contains an optional comment about
          your hosted zone
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The name of the domain
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Parent
        description: CreatedHostedZoneRequest
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: VPC
        description: The VPC that you want your hosted zone to be associated with
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
  /2013-04-01/hostedzone/Id:
    delete:
      summary: Delete Hosted Zone
      description: Deletes a hosted zone. Send a DELETE request to the /Amazon Route
        53API version/hostedzone/hosted zone ID             resource.ImportantDelete
        a hosted zone only if there are no resource record sets other than the defaultSOA
        record and NS resource record sets. If the hosted zone contains other resource
        recordsets, delete them before deleting the hosted zone. If you try to delete
        a hosted zone thatcontains other resource record sets, Amazon Route 53 denies
        your request with aHostedZoneNotEmpty error. For information about deleting
        records from yourhosted zone, see ChangeResourceRecordSets.
      operationId: deletehostedzone
      x-api-path-slug: 20130401hostedzoneid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
    get:
      summary: Get Hosted Zone
      description: Retrieves the delegation set for a hosted zone, including the four
        name serversassigned to the hosted zone. Send a GET request to the /Amazon
        Route 53 APIversion/hostedzone/hosted zone ID             resource.
      operationId: gethostedzone
      x-api-path-slug: 20130401hostedzoneid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone for which you want to get a list of
          the name servers in thedelegation set
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
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