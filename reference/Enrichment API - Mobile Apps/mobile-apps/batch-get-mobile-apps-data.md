---
title: /mrt/apps
excerpt: >-
  <p>The purpose of this API is to provide risk ratings and reputational data
  across thousands of mobile applications in a batch mode.</p> <p>Posted data
  should be in CSV format where each line consists of a single field which is
  the Bundle ID or Track ID.  The request MIME type should be
  <code>text/plain</code>.</p> <p>Once request data is submitted, a URL to a
  newline-delimited JSON formatted report is provided as a response. While the
  resulting resource is public, the URL contains a randomly generated identifier
  that ensures the data is relatively secure unless the URL itself is made
  public by the user.</p> <p>The report will not be available for download at
  the returned URL location until processing has been completed. While creating
  the report, a request to retrieve the report using the response URL will
  return an HTTP status code Not Found (404). Once asynchronous processing has
  completed, the report is returned as normal. If asynchronous processing of a
  report fails because of an invalid query the request to retrieve the report
  using the response URL will return an HTTP status code Bad Request (400). Or,
  if the submitted file contained more than 5000 Bundle ID or Track IDs, then an
  HTTP status code Request Entity Too Large (413) is returned. Or, if the
  account's quota limit has been exceeded, then an HTTP status code Forbidden
  (403) is returned. For all other errors, a request to retrieve the report
  using the response URL will return an HTTP status code Internal Service Error
  (500). Client systems should poll the response URL until the report is
  available, or a non 404 HTTP status code is returned.</p> <p><b>This operation
  requires an Enterprise subscription. Please reach out to us at <a
  href="mailto:support@pixalate.com">support@pixalate.com</a> for details on how
  to enable this for your account.</n></p>
api:
  file: enrichment-api-mobile-apps.json
  operationId: Batch Get Mobile Apps Data
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---