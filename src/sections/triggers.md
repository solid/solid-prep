# Triggers # {#triggers}

A [=Solid server=] implementing the [SUPER] on an LDP Resource SHOULD send a [PREP] notification when the state of the said resource is modified.

A [=Solid server=] MUST NOT transmit a [PREP] notification before the resource has been modified and a confirmation (if necessary) has been sent to (but might not have been received by) the agent that initiated the resource modification.

<div class="advisement">
  <div class="marker">Implementation Guidance</div>

  <p>The Solid Protocol [[SOLID]] requires an LDP container's state is modified when certain HTTP events occur on a contained resource. Thus, an HTTP event on a resource can trigger a [=Solid server=] to transmit a [PREP] notification on that resource or its container or both.

  <p>It follows that a [=Solid server=] ought to send [PREP] notification(s) on an resource and/or its container, when a request with one of the following [[RFC9110#section-9|HTTP methods]] generates a response with any of the following [[RFC9110#section-15|HTTP status codes]]:

  <table class="numbered auto">
    <caption> HTTP Notification Triggers
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
  <br/>

  <p>Additionally, a [=Solid server=] ought to send [PREP] notification(s) on an resource and/or its container when modified at a later time as result of HTTP request that generates a <code>[[RFC9110#section-15.3.3|202 (Accepted)]]</code> status code.

  <p>A [=Solid server=] needs to ensure that a [PREP] notification is not transmitted before a response has been sent to the user agent that initiated the HTTP request that triggered the said notification.

</div>
