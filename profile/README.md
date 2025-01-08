# Developing ECH for OpenSSL (DEfO)

<p> The encrypted ClientHello (ECH) mechanism 
(<a href="https://tools.ietf.org/html/draft-ietf-tls-esni">draft-spec</a>) is a
way to plug a few privacy-holes that remain in the Transport Layer Security 
(<a href="https://tools.ietf.org/html/rfc8446">TLS</a>) protocol that's used as
the security layer for the web. <a href="https://openssl.org/">OpenSSL</a> is a
widely used library that provides an implementation of the TLS protocol.  The
<a href="https://defo.ie">DEfO project</a> has developed an implementation of
ECH for OpenSSL, and proof-of-concept implementations of various clients and servers that use OpenSSL as a
demonstration and for interoperability testing.  DEfO is funded by
the <a href="https://www.opentech.fund/">Open Technology Fund (OTF)</a>.
<a href="https://tolerantnetworks.com/">Tolerant Networks
Ltd.</a> and people from the <a href="https://guardianproject.info/">Guardian
Project</a> are doing the work in DEfO. </p>

This organisation is where we keep our various ECH-enabled code
repos and our [ech-dev-utils](https://github.com/defo-project/ech-dev-utils)
repo that has HOWTOs, test scripts and other ancillary ECH developer content.
That's the place to start if you want to play with these ECH-enabled packages.

## Builder/CI status for repos

We're currently (2025-01-07) making changes to these repositories to update the
ECH APIs used to match those agreed with OpenSSL maintainers, as part of the
work to upstream our ECH code into the [OpenSSL ECH feature
branch](https://github.com/openssl/openssl/tree/feature/ech). That work is
partly completed, so you can think of these repos as being a few PRs ahead of
the upstreaming work. In the short-term, that'll mean things will be broken
for a few days as we work through the transition from old to new APIs.

For each of our ECH-enabled repos, we've added a 'builder' workflow (run daily)
that attempts to merge our code with the latest upstream and that then does a
build and a basic test. We expect these to fail from time to time as changes
occur in the upstream packages. When that happens, there's a red badge below
and we usually fix those within a couple of days by rebasing the repos here
with the relevant upstream. Note that a red badge doesn't mean that our
ECH-enabled code is broken, just that some manual intervention is needed to
bring us back up to the bleeding edge with the upstream package.

Packages with our ECH code yet to be upstreamed:

| Package  | 'Builder' status | Details |
|--|--|--|
| [openssl](https://github.com/defo-project/openssl) | ![openssl packages.yaml](https://github.com/defo-project/openssl/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/openssl/actions/workflows/packages.yaml) |
| [apache-httpd](https://github.com/defo-project/apache-httpd) | ![apache-httpd packages.yaml](https://github.com/defo-project/apache-httpd/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/apache-httpd/actions/workflows/packages.yaml) |
| [haproxy](https://github.com/defo-project/haproxy) | ![haproxy packages.yaml](https://github.com/defo-project/haproxy/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/haproxy/actions/workflows/packages.yaml) |
| [nginx](https://github.com/defo-project/nginx) | ![nginx packages.yaml](https://github.com/defo-project/nginx/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/nginx/actions/workflows/packages.yaml) |
| [python](https://github.com/defo-project/cpython) | ![python packages.yaml](https://github.com/defo-project/cpython/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/cpython/actions/workflows/packages.yaml) |

For packages where our ECH code has already been upstreamed, we also have a
daily check that those build and pass a basic ECH test. So far, that's just
for `curl` and `lighttpd`:

| Package  | 'Builder' status | Details |
|--|--|--|
| [curl](https://github.com/defo-project/curl) | ![curl packages.yaml](https://github.com/defo-project/curl/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/curl/actions/workflows/packages.yaml) |
| [lighttpd1.4](https://github.com/defo-project/lighttpd1.4) | ![lighttpd packages.yaml](https://github.com/defo-project/lighttpd1.4/actions/workflows/packages.yaml/badge.svg) | [workflow link](https://github.com/defo-project/lighttpd1.4/actions/workflows/packages.yaml) |
