<h2 id="considerations" class="no-num">
  Considerations
</h2>

*This section is non-normative.*

This section details security and privacy considerations.

Some of the normative references within this specification point to documents with a Living Standard or Draft status, meaning their contents can still change over time. It is advised to monitor these documents, as such changes might have implications.

Since [PROTOCOL] defines representation and semantics for the use of [SUPER] to transmit notifications from Solid resources, it follows that the [PROTOCOL] inherits security and privacy considerations of both the [SUPER] and the Solid Protocol. Considerations relevant to the use of [SUPER] for transmitting notifications are discussed in [[!PREP]] [[PREP#name-considerations|§ 11 Considerations]], and considerations relevant to Solid Protocol are discussed in  [[!SOLID]] [[SOLID#considerations|§ 10 Considerations]].

## Security Considerations ## {#security-considerations}

*This section is non-normative.*

[=Solid servers=] are strongly discouraged from exposing information beyond the minimum amount necessary in a notification. [=Solid clients=] are strongly discouraged from exposing information beyond the minimum amount necessary to receive notifications from particular resources.

[=Solid clients=] are discouraged from sending requests for notifications to untrusted [=Solid servers=], including localhost or any other loopback IP address, in order to avoid making arbitrary requests.
