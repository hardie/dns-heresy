---
title: DNS Heresies
abbrev: DNS heresies
docname: draft-hardie-dns-heresy
category: info

ipr: trust200902
area: INT
keyword: Internet-Draft

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: "T. Hardie"
    name: "Ted Hardie"
    email: ted.ietf@gmail.com

normative:
  RFC2119:

informative:
  RFC8484



--- abstract

One of the critical problems in discussing the DNS has always been that the “Domain Name System” is comprised of parts that have very different characteristics but tend to be lumped together in discussions as if they were a unitary whole.  This document presents a strawman view of the related issues in order to prompt better descriptions.

--- middle

# Introduction

One of the critical problems in discussing the DNS has always been that the “Domain Name System” is comprised of parts that have very different characteristics but tend to be lumped together in discussions as if they were a unitary whole.  This document presents a strawman view of the related issues.  Because DNS over HTTPS {{RFC8484}} is a current hot topic, some specific attention is paid to the DNS as deployed using DoH.


# Conventions and Definitions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in BCP 14 {{RFC2119}} {{!RFC8174}}
when, and only when, they appear in all capitals, as shown here.

# Elements of the DNS

There a lot of ways to describe the Domain Name System.  My personal take is that it is valuable to split discussions into:  the namespace; the system for delegating authority over parts of the namespace; the currently deployed database of mappings between the names in the namespace and specific values for individual record types; the protocol for querying the database for a mapping; the transport carrying the protocol for querying the database; the sets of servers which hold that database; the software which poses the queries; and the software which answers the queries. 

A really complete look could include the registry protocols like EPP and RDAP, the databases they maintain, and the software which queries those databases and responds.  You could even include the routing systems that let anycast deployments work.  Mostly, though, I see those as outside the grouping that get lumped into “the DNS”.

## Requirements for the DNS namespace

The namespace has to have unique names to be useful to URIs and other higher-layer identifiers as well as lower-layer protocol functions. 

The system for delegating authority over parts of the namespace must also have unique delegations or very clear exception processing (and we’ve all felt the pain when it has not).  

But once we shift from there to the database of mappings between the names and the records, things start to change.  While there was once a presumption that the mappings were universal, the deployed reality now is that there is considerable variation in what mappings are returned to queries, commonly based on network location.  The system still works despite that change because the party responsible for a specific variation is delegated the authority over that part of the namespace; they determine that the variation is beneficial or pay the price when it is not. 


# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.



--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
