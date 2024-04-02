# Developing ECH for OpenSSL (DEfO)

<p> The encrypted ClientHello (ECH) mechanism 
(<a href="https://tools.ietf.org/html/draft-ietf-tls-esni">draft-spec</a>) is a
way to plug a few privacy-holes that remain in the Transport Layer Security 
(<a href="https://tools.ietf.org/html/rfc8446">TLS</a>) protocol that's used as
the security layer for the web. <a href="https://openssl.org/">OpenSSL</a> is a
widely used library that provides an implementation of the TLS protocol.  The
<a href="https://defo.ie">DEfO project</a> has developed an implementation of
ECH for OpenSSL, and proof-of-concept implementations of various clients and servers that use OpenSSL as a
demonstration and for interoperability testing.  DEfO was initially funded by
the <a href="https://www.opentech.fund/">Open Technology Fund (OTF)</a>, and
subsequently by the <a href="https://www.ndi.org/">National Democratic
Initiative</a>. In mid-2023 OTF extended our funding to help with upstreaming
the relevant ECH code to the various projects involved.
<a href="https://tolerantnetworks.com/">Tolerant Networks
Ltd.</a> and people from the <a href="https://guardianproject.info/">Guardian
Project</a> are doing the work in DEfO. </p>

## Build/CI status for repos:

|  |  |
|--|--|
| apache-httpd | ![apache-httpd packages.yaml](https://github.com/defo-project/apache-httpd/actions/workflows/packages.yaml/badge.svg) |
| curl | ![curl packages.yaml](https://github.com/defo-project/curl/actions/workflows/packages.yaml/badge.svg) |
| haproxy | ![haproxy packages.yaml](https://github.com/defo-project/haproxy/actions/workflows/packages.yaml/badge.svg) |
| lighttpd1.4 | ![lighttpd packages.yaml](https://github.com/defo-project/lighttpd1.4/actions/workflows/packages.yaml/badge.svg) |
| nginx | ![nginx packages.yaml](https://github.com/defo-project/nginx/actions/workflows/packages.yaml/badge.svg) |
| openssl | ![openssl packages.yaml](https://github.com/defo-project/openssl/actions/workflows/packages.yaml/badge.svg) |

