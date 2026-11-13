# Developing ECH for OpenSSL (DEfO)

<p> The encrypted ClientHello (ECH) mechanism 
(<a href="https://datatracker.ietf.org/doc/rfc9849/">RFC 9849</a>) is a
way to plug a few privacy-holes that remain in the Transport Layer Security 
(<a href="https://tools.ietf.org/html/rfc8446">TLS</a>) protocol that's used as
the security layer for the web. <a href="https://openssl.org/">OpenSSL</a> is a
widely used library that provides an implementation of the TLS protocol.  The
<a href="https://defo.ie">DEfO project</a> has developed an implementation of
ECH for OpenSSL, and proof-of-concept implementations of various clients and servers that use OpenSSL as a
demonstration and for interoperability testing.  DEfO was funded by
the <a href="https://www.opentech.fund/">Open Technology Fund (OTF)</a>.
<a href="https://tolerantnetworks.com/">Tolerant Networks
Ltd.</a> and people from the <a href="https://guardianproject.info/">Guardian
Project</a> did the work in DEfO.</p>

<p>OTF funding for DEfO finished in November 2026, but the team continues
to try help other projects with integrating and using ECH.</p>

This organisation is where we keep our various ECH-enabled code
repos and our [ech-dev-utils](https://github.com/defo-project/ech-dev-utils)
repo that has HOWTOs, test scripts and other ancillary ECH developer content.
That's the place to start if you want to play with these ECH-enabled packages.

Now that ECH has been upstreamed to all targets, the code here is almost
identical to upstream, with the following additional features only supported
here:
- ECH split mode is supported here in the OpenSSL, haproxy and nginx packages
- The OpenSSL code here supports use of X-Wing as an ECH KEM, in order to 
  demonstrate use of post-quantum algorithms with ECH. That works with
  curl as built here (using that OpenSSL build) but also with golang clients.

## Builder/CI status for repos

The ECH APIs used in these repos are those agreed with OpenSSL maintainers,
which will be part of the OpenSSL 4.0 release, and (other than for split-mode
ECH) have been upstreamed into the OpenSSL master branch.

For each of these ECH-enabled repos, we've added a 'builder' workflow (run
daily and after a push) that attempts to merge our code with the latest
upstream and that then does a build and a basic test. We expect these to fail
from time to time as changes occur in the upstream packages. When that happens,
there's a red badge below and we usually fix those within a couple of days by
rebasing the repos here with the relevant upstream. Note that a red badge
doesn't mean that our ECH-enabled code is broken, just that some manual
intervention is needed to bring us back up to the bleeding edge with the
upstream package.

We have now upstreamed ECH shared-mode code to the OpenSSL project and we've
also upstreamed ECH code to curl, lighttpd, apache2, haproxy and nginx.

For openssl, haproxy and nginx, our ECH shared-mode code has been upstreamed,
but the defo-project repos here also support ECH split-mode so we also have a daily
check that those build and pass the basic ECH test.

As of 2026-09-17 we've updated these builds to reflect the latest upstreams.

For packages where our ECH code has already been upstreamed, we have
checks that those build and pass a basic ECH test. Those are currently
only run after a git push.

| Package  | 'Builder' status | Details |
|--|--|--|
| [openssl](https://github.com/defo-project/openssl) | ![openssl packages.yaml](https://github.com/defo-project/openssl/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/openssl/actions/workflows/packages.yaml) |
| [apache-httpd](https://github.com/defo-project/apache-httpd) | ![apache-httpd packages.yaml](https://github.com/defo-project/apache-httpd/actions/workflows/packages.yaml/badge.svg?event=workflow_dispatch) | [workflow link](https://github.com/defo-project/apache-httpd/actions/workflows/packages.yaml) |
| [curl](https://github.com/defo-project/curl) | ![curl packages.yaml](https://github.com/defo-project/curl/actions/workflows/packages.yaml/badge.svg?event=workflow_dispatch) | [workflow link](https://github.com/defo-project/curl/actions/workflows/packages.yaml) |
| [lighttpd1.4](https://github.com/defo-project/lighttpd1.4) | ![lighttpd packages.yaml](https://github.com/defo-project/lighttpd1.4/actions/workflows/packages.yaml/badge.svg?event=workflow_dispatch) | [workflow link](https://github.com/defo-project/lighttpd1.4/actions/workflows/packages.yaml) |
| [haproxy](https://github.com/defo-project/haproxy) | ![haproxy packages.yaml](https://github.com/defo-project/haproxy/actions/workflows/packages.yaml/badge.svg?event=workflow_dispatch) | [workflow link](https://github.com/defo-project/haproxy/actions/workflows/packages.yaml) |
| [nginx](https://github.com/defo-project/nginx) | ![nginx packages.yaml](https://github.com/defo-project/nginx/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/nginx/actions/workflows/packages.yaml) |
| [python](https://github.com/defo-project/cpython) | [![builder](https://github.com/defo-project/cpython/actions/workflows/packages.yaml/badge.svg?event=workflow_dispatch)](https://github.com/defo-project/cpython/actions/workflows/packages.yaml) | [workflow link](https://github.com/defo-project/cpython/actions/workflows/packages.yaml) |
