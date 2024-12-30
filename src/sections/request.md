# Request # {#request}

A [=Solid server=] implementing [SUPER] on an LDP Resource MUST accept [[PREP#request|requests]] [[!PREP]] when the `accept` [[PREP#event-field|event-field]] associated with the `"prep"` list item in the <code>[[PREP#accept-events|Accept-Events]]</code> header field indicates a preferred media type of `application/ld+json` [[!JSON-LD11]].

<div class="example">
  <span class="marker">Request for Solid-PREP Notifications</span>
  <pre class="include-code">
    path: examples/request.http
  </pre>
</div>
