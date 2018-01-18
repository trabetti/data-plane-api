.. _config_http_filters_ip_tagging:

IP Tagging
==========
// FIXME add a arch overview

// FIXME
// This is an HTTP filter which enables Envoy to tag requests with extra
// information such as location, cloud source, and any extra data. This is
// useful to prevent against DDoS attacks.
// The\
// .. note::
// Currently the implementation doesn't support nested prefixes.



The HTTP IP Tagging filter will get all tags associated for a request's trusted address retrieved from
:ref:`x-forwarded-for<config_http_conn_man_headers_x-forwarded-for>` if it matches the request type
filter setting. l incoming requests with data specified associated with the CIDR range
This is an HTTP filter which enables Envoy to tag requests with extra information such as location, cloud source, and any
extra data. This is useful to prevent against DDoS.

// FIXME add a comment about the LC Trie algorithm refer to the paper
// FIXME when there are tags `x-envoy-ip-tags` gets populated


.. note::
  Note that the filter does not support nested prefixes. If there are nested prefixes, an
  exception will be thrown during filter initialization.

Configuration
-------------
* :ref:`v2 API reference <envoy_api_msg_filter.http.IPTagging>`

Runtime
-------
The IP Tagging filter supports the following runtime settings:

ip_tagging.filter_enabled
  The % of requests for which the filter is enabled. Default is 100.