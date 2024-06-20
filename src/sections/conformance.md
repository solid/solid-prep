## Classes of Products ## {#classes-of-products}

The [PROTOCOL] identifies the following Classes of Products for conforming implementations. These products are referenced throughout this specification.

<dl>

  : <dfn>Solid Server</dfn>
  :: A *Solid server* that builds on a [[SOLID-PROTOCOL#Server|server]] [[!SOLID-PROTOCOL]] and [[PREP#resource-server|resource server]] [[!PREP]] by defining the behaviour of resources.

  : <dfn>Solid Client</dfn>
  :: A *Solid client* that builds on a [[SOLID-PROTOCOL#Client|client]] [[!SOLID-PROTOCOL]] and [[PREP#application-client|application client]] [[!PREP]].

</dl>

## Interoperability ## {#interoperability}

Interoperability occurs between [Solid Client—Solid Server](#Solid-client—Solid-server-interoperability) as defined by the [PROTOCOL].

<dl>

  : <dfn id="Solid-client—Solid-server-interoperability">Solid Client—Solid Server Interoperability</dfn>
  :: Interoperability of implementations for [=Solid clients=] and [=Solid servers=] is tested by evaluating an implementation’s ability to transmit and receive [PREP] Notifications that conform to [PROTOCOL].

</dl>

## Namespaces ## {#namespaces}

This document uses the following RDF vocabularies and corresponding namespace prefix bindings:

<table class="auto">
  <caption> Prefixes and Namespaces
  <thead>
    <tr>
      <th> Prefix
      <th> Namespace
      <th> Description
  <tbody>
    <tr>
      <td> <code>xs
      <td> <samp>http://www.w3.org/2001/XMLSchema#
      <td> [[!XMLSCHEMA11-1]]
  <tbody>
    <tr>
      <td> <code>as
      <td> <samp>https://www.w3.org/ns/activitystreams#
      <td> [[!ACTIVITYSTREAMS-VOCABULARY]]
</table>
