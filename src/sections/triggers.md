# Triggers # {#triggers}

The Solid Protocol [[!SOLID]] requires an LDP container's state is modified when certain HTTP events occur on a contained resource. Thus, an HTTP event on a resource can trigger a [=Solid server=] to transmit a [PREP] notification on that resource or its container or both.

A [=Solid server=] implementing the [SUPER] on an LDP Resource SHOULD send a [PREP] notification to a [=Solid client=] listening in on the said resource and/or its container, when a request with one of the following [[RFC9110#section-9|HTTP methods]] generates a response with any of the following [[RFC9110#section-15|HTTP status codes]]:

<table class="numbered auto">
  <caption> Notification Triggers
  <tr>
    <th rowspan=2> Request Method
    <th rowspan=2> Response Status
    <th colspan=2 class="center"> Notify
  <tr>
    <th class="center"> Resource
    <th class="center"> Container
  <tr>
    <td rowspan=2>
      <code> [[RFC9110#section-9.3.4|PUT]] <br>
      <code> [[RFC5789#section-2|PATCH]] <br>
    <td>
      <code> [[RFC9110#section-15.3.1|200 (OK)]] <br>
      <code> [[RFC9110#section-15.3.5|204 (No Content)]] <br>
      <code> [[RFC9110#section-15.3.6|205 (Reset Content)]]
    <td class="tick">
      &check;
    <td class="tick">
      &check;
  <tr>
    <td>
      <code> [[RFC9110#section-15.3.2|201 (Created)]] <br>
    <td>
    <td class="tick">
      &check;
  <tr>
    <td rowspan=2>
      <code> [[RFC9110#section-9.3.3|POST]]
    <td>
      <code> [[RFC9110#section-15.3.1|200 (OK)]] <br>
      <code> [[RFC9110#section-15.3.5|204 (No Content)]] <br>
      <code> [[RFC9110#section-15.3.6|205 (Reset Content)]]
    <td class="tick">
      &check;
    <td class="tick">
      &check;
  <tr>
    <td>
      <code> [[RFC9110#section-15.3.2|201 (Created)]]
    <td class="tick">
      &check;
  <tr>
    <td>
      <code> [[RFC9110#section-9.3.5|DELETE]]
    <td>
      <code> [[RFC9110#section-15.3.1|200 (OK)]] <br>
      <code> [[RFC9110#section-15.3.5|204 (No Content)]] <br>
    <td class="tick">
      &check;
    <td class="tick">
      &check;
</table>

## Don't Jump the Gun ## {#trigger-timing}

A [=Solid server=] MUST NOT transmit a [PREP] notification to a [=Solid client=] before a response has been sent to the user agent that initiated the request that triggered the said notification.
