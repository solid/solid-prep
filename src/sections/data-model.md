# Data Model # {#data-model}

The core notification data is expressed with the Activity Streams [[ACTIVITYSTREAMS-VOCABULARY]] and [Solid Notifications](https://www.w3.org/ns/solid/notifications) [[!SOLID-NOTIFICATIONS]] vocabularies.

## Properties ## {#notification-properties}

A [PREP] notification from an LDP Resource on a [=Solid server=] MUST have the following properties:

<dl>

  <dt id="notification-property-id"><code>*id* &lt;xs:string></code>
  <dd> an opaque identifier for the notification. Can be used to set `Last-Event-ID` in a subsequent [PREP] notifications request.

  <dt id="notification-property-type"><code>*type* &lt;as:Activity></code>
  <dd> the [[ACTIVITYSTREAMS-VOCABULARY#activity-types|type of activity]] that triggered the notification.

  <dt id="notification-property-published"><code>*published* &lt;xs:dateTime></code>
  <dd> the date and time of the notification.

</dl>

A [PREP] notification from an LDP Resource on a [=Solid server=] SHOULD have the following properties:

<dl>

  <dt id="notification-property-state"><code>*state* &lt;xs:string></code>
  <dd> an opaque identifier for the last known state of the resource.

</dl>

## Extended Content ## {#extended-content}

A [=Solid server=] MAY augment the [[JSON-LD11#the-context|JSON-LD Context]] [[JSON-LD11]] definition and extend the content of notifications.

NOTE: See examples of [[ACTIVITYSTREAMS-CORE#example-using-multiple-vocabularies|using multiple vocabularies]] in the Activity Streams [[ACTIVITYSTREAMS-CORE]] specification.

<div class="advisement">
  <div class="marker">Implementation Guidance</div>
  [=Solid clients=] are encouraged to be aware that anything can be included in the notification. Clients might want to take suitable precautions when ascertaining the veracity of the contents.
</div>
