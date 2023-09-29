---
title: "Platform Independence"
icon: "ti-server"
description: "Platform Independence as defined by DPGA Standard - Indicator 4"
type: "docs"
---

> **4. Platform Independence**
>
> When the digital public good has mandatory dependencies that create more restrictions than the
> original license, proving independence from the closed component(s) and/or indicating the existence
> of functional, open alternatives that can be used **without significant changes to the core product** is
> **required**.

Source: https://digitalpublicgoods.net/standard/

If your software is released using an open source license but depends on closed source proprietary
components and/or services, you have a problem. Your dependencies are creating more restrictions
than the license you chose. This applies to all closed but _"free"_ services and components.

### Examples of platform independence issues

#### Google Firebase

You're creating a mobile app and chose [GPL-3.0](https://choosealicense.com/licenses/gpl-3.0/) as
the license for your product. You also decided to use Google Firebase for handling user's data,
authentication and analytics. Even if your application is open source, it cannot work without
Google's proprietary components.

Google makes it really easy to start using Firebase using their `SDK`, locking yourself to work with
their services. They give you a generous entry level tier that makes it feel it's _"free"_.

In this scenario you need to provide an open alternative to the data storage, authentication and
analytics components of your application, away from Google.

#### AWS Lambda

You're creating a service that ingests data (e.g. CSV files) and stores it in a database. You decide
to use AWS Lambda to react to new files in AWS S3.

If you architect your solution around the proprietary services of a particular Cloud vendor, your
solution is not _Platform Independent_.

#### AWS Simple Storage Service (S3) - An exception

Amazon Simple Storage Service (S3) is a proprietary service by Amazon Web Services (AWS), it was
launched in 2006 and has become a _de-facto standard_ on how to handle _object storage_ (binary
files).

Over the years several implementations have emerged. All the major Cloud vendors support S3 API, and
you have access to open source implementations like [MinIO](https://min.io/),
[Ceph](https://docs.ceph.com/en/latest/radosgw/s3/), OpenStack [Object
Storage](https://docs.openstack.org/mitaka/config-reference/object-storage/configure-s3.html) and
others.

If your application uses AWS S3, you can claim that there are open alternatives that support those
API calls without major code changes.

#### Large Language Models (LLMs)

Most projects release their models (weights) under a non-OSI approved licenses, e.g. just for
academic purposes or preventing any commercial activity. Other expose their models via a closed
source and propietary API.

If your project depends directly on any of this components or services, your project is **not**
platform independent.

| Component/Service | Open Source | Platform Independent | Notes                    |
|-------------------|-------------|----------------------|--------------------------|
| Open AI ChatGPT   | No          | No                   | Commercial               |
| Facebook LLAMA2   | No          | No                   | Custom Community license |
|                   |             |                      |                          |


### Business Source License (BUSL) and Server Side Public License (SSPL)

The _Business Source License_ [BUSL](https://mariadb.com/bsl11/), and _Server Side Public License_
[SSPL](https://en.wikipedia.org/wiki/Server_Side_Public_License) are recent _"source available"_
licenses that are not [OSI](https://opensource.org/osd) approved.

The main idea of users of this licenses, is to try to block the commercial hosting of their software
by other companies[^bsl].

Using a database like MariaDB Enterprise[^mariadb] released under BSL 1.1 or [Elastic
Search](https://www.elastic.co/pricing/faq/licensing) and
[MongoDB](https://www.mongodb.com/community/licensing) under SSPL, will make your system not
platform independent.


## Use Open Source components, delegate the hosting and maintenance

A strategy to achieve Platform Independence easily, is to always use open source components and
delegate the hosting/maintenance of those components/services to your hosting provider.

As example, you can use PostgreSQL database for your data and any of the major cloud providers for
hosting it: AWS RDS, GCP Cloud SQL, Azure Database for PostgreSQL.

If you are using a MERN[^mern] stack, your database can be hosted in AWS DocumentDB, MongoDB Atlas
in GCP, Azure Cosmos DB for MongoDB.

##### Notes

[^bsl]: [BSL FAQ](https://mariadb.com/bsl-faq-mariadb/)
[^mariadb]: There is a GPL version of MariaDB
[^mern]: **M**ongoDB, **E**xpress.js, **R**eact.js, **N**ode.js
