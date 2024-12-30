# Response # {#Response}

A [=Solid server=] implementing [SUPER] on an LDP Resource MUST be able to transmit [PREP] notifications using the `application/ld+json` [[!JSON-LD11]] media type. It MAY also support other media types to transmit [PREP] notifications.

<div class="example">
  <span class="marker">Response with Solid-PREP Notifications</span>
  <pre class="include-code">
    path: examples/response.http
  </pre>
</div>
