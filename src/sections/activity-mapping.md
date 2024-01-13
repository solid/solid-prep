# Activity Mapping # {#activity-mapping}

A [=Solid server=] sending a [PREP] notification as a result of some activity on an LDP Resource MUST set the [type](#notification-property-type) property as the [[ACTIVITYSTREAMS-VOCABULARY#activity-types|type of activity]] that triggered the notification as specified by the Activity Streams vocabulary [[ACTIVITYSTREAMS-VOCABULARY]].


<div class="advisement">
  <div class="marker">Implementation Guidance</div>

  When an LDP resource is modified by virtue of an HTTP request, the activity type ought to be set as follows:

  1. When the [PREP] notification is triggered by a request on the resource with one of the following [[RFC9110#methods|HTTP methods]]:

    <table class="numbered">
      <caption> Activity Mapping for LDP Resources
      <thead>
        <tr>
          <th> Request Method
          <th> Activity Type
      <tbody>
        <tr>
          <td><code> [[RFC9110#PUT|PUT]]
          <td rowspan="3"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]
        <tr>
          <td><code> [[RFC5789#section-2|PATCH]]
        <tr>
          <td><code> [[RFC9110#POST|POST]]
        <tr>
          <td><code> [[RFC9110#DELETE|DELETE]]
          <td><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-delete|as:Delete]]
    </table>
    <br/>

  2. When the [PREP] notification is triggered by a request on a contained resource with one of the following [[RFC9110#methods|HTTP methods]]:

    <table class="numbered">
      <caption> Activity Mapping for LDP Containers when contained resources change
      <thead>
        <tr>
          <th> Request Method
          <th> Activity Type
      <tbody>
        <tr>
          <td><code> [[RFC9110#PUT|PUT]]
          <td rowspan="3"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]
        <tr>
          <td><code> [[RFC5789#section-2|PATCH]]
        <tr>
          <td><code> [[RFC9110#POST|POST]]
        <tr>
          <td><code> [[RFC9110#DELETE|DELETE]]
          <td><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-remove|as:Remove]]
    </table>
    <br/>

  3. When the [PREP] notification is triggered by a request to create a new resource inside that container (resource) with one of the following [[RFC9110#methods|HTTP methods]]:

    <table class="numbered">
      <caption> Activity Mapping for LDP Containers when contained resources are created
      <thead>
        <tr>
          <th> Request Method
          <th> Activity Type
      <tbody>
        <tr>
          <td><code> [[RFC9110#PUT|PUT]]
          <td rowspan="2"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-add|as:Add]]
        <tr>
          <td><code> [[RFC5789#section-2|PATCH]]
    </table>
