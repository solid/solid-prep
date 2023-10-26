# Triggers # {#triggers}

The Solid Protocol [[!SOLID]] requires an LDP container's state is modified when certain HTTP events occur on a contained resource. Thus, an HTTP event on a resource can trigger a [=Solid server=] to transmit [PREP] notification on that resource or its container or both.

A [=Solid server=] implementing the [SUPER] on an LDP Resource SHOULD send a [PREP] notification to a [=Solid client=] upon the following triggers:

## Resources and their Containers ## {#triggers-resource-and-their-containers}

When a request sent to the resource or a contained resource within it, with one of the following [[RFC9110#section-9|HTTP methods]] generates a response with any of the following [[RFC9110#section-15|HTTP status codes]]:

<table class="numbered">
  <caption> Notification Triggers (Resources and their Containers)
  <tr>
    <th> Request Method
    <th> Response Status
  <tr>
    <td>
      <code> [[RFC9110#section-9.3.4|PUT]] <br>
      <code> [[RFC5789#section-2|PATCH]] <br>
      <code> [[RFC9110#section-9.3.3|POST]]
    <td>
      <code> [[RFC9110#section-15.3.1|200 (OK)]] <br>
      <code> [[RFC9110#section-15.3.5|204 (No Content)]] <br>
      <code> [[RFC9110#section-15.3.6|205 (Reset Content)]]
  <tr>
    <td>
      <code> [[RFC9110#section-9.3.5|DELETE]]
    <td>
      <code> [[RFC9110#section-15.3.1|200 (OK)]] <br>
      <code> [[RFC9110#section-15.3.5|204 (No Content)]] <br>
</table>

## Container only ## {#triggers-container-only}

When a request sent to (create) a contained resource, with one of the following [[RFC9110#section-9|HTTP methods]] generates a response with any of the following [[RFC9110#section-15|HTTP status codes]]:

<table class="numbered">
  <caption> Notification Triggers (Container only)
  <tr>
    <th> Request Method
    <th> Response Status
  <tr>
    <td>
      <code> [[RFC9110#section-9.3.4|PUT]] <br>
      <code> [[RFC5789#section-2|PATCH]] <br>
    <td>
      <code> [[RFC9110#section-15.3.2|201 (Created)]] <br>
</table>

## Resources only ## {#triggers-resources-only}

When a request sent to the resource with one of the following [[RFC9110#section-9|HTTP methods]] generates a response with any of the following [[RFC9110#section-15|HTTP status codes]]:

<table class="numbered">
  <caption> Notification Triggers (Resource only)
  <tr>
    <th> Request Method
    <th> Response Status
  <tr>
    <td>
      <code> [[RFC9110#section-9.3.3|POST]]
    <td>
      <code> [[RFC9110#section-15.3.2|201 (Created)]]
</table>

## Don't Jump the Gun ## {#trigger-timing}

A [=Solid server=] MUST NOT transmit a [PREP] notification to a [=Solid client=] before a response has been sent to the user agent that initiated the request that triggered the said notification.
