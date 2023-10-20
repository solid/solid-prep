# Activity Mapping # {#activity-mapping}

A [=Solid server=] implementing the [PROTOCOL] on an LDP Resource MUST set the activity [type](#notification-property-type) for a [PREP] notification based on the triggering request as follows:

## LDP Resource ## {#activity-mapping-ldp-resource}

When the [PREP] notification is triggered by a request on the resource with one of the following [[RFC9110#section-9|HTTP methods]]:

<table class="numbered">
  <caption> Activity Mapping for LDP Resources
  <thead>
    <tr>
      <th> Request Method
      <th> Activity Type
  <tbody>
    <tr>
      <td><code> [[RFC9110#section-9.3.4|PUT]]
      <td rowspan="3"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]
    <tr>
      <td><code> [[RFC5789#section-2|PATCH]]
    <tr>
      <td><code> [[RFC9110#section-9.3.3|POST]]
    <tr>
      <td><code> [[RFC9110#section-9.3.5|DELETE]]
      <td><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-delete|as:Delete]]
</table>

## Existing Resource in LDP Container ## {#activity-mapping-existing-resource-ldp-container}

When the [PREP] notification is triggered by a request on a contained resource with one of the following [[RFC9110#section-9|HTTP methods]]:

<table class="numbered">
  <caption> Activity Mapping for LDP Containers when contained resources change
  <thead>
    <tr>
      <th> Request Method
      <th> Activity Type
  <tbody>
    <tr>
      <td><code> [[RFC9110#section-9.3.4|PUT]]
      <td rowspan="3"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]
    <tr>
      <td><code> [[RFC5789#section-2|PATCH]]
    <tr>
      <td><code> [[RFC9110#section-9.3.3|POST]]
    <tr>
      <td><code> [[RFC9110#section-9.3.5|DELETE]]
      <td><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-remove|as:Remove]]
</table>
<br/>

## New Resource in LDP Container ## {#activity-mapping-new-resource-ldp-container}

When the [PREP] notification is triggered by a request to create a new resource inside that container (resource) with one of the following [[RFC9110#section-9|HTTP methods]]:

<table class="numbered">
  <caption> Activity Mapping for LDP Containers when contained resources are created
  <thead>
  <tr>
    <th> Request Method
    <th> Activity Type
<tbody>
    <tr>
      <td><code> [[RFC9110#section-9.3.4|PUT]]
      <td rowspan="2"><code> [[ACTIVITYSTREAMS-VOCABULARY#dfn-add|as:Add]]
    <tr>
      <td><code> [[RFC5789#section-2|PATCH]]
</table>
