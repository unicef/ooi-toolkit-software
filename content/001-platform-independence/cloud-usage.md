---
title: "Cloud usage"
icon: "ti-server"
description: "The use of cloud services and platform independence"
type: "docs"
---

# Cloud usage

> Can we use cloud services?

Nothing in the [DPG standard](https://digitalpublicgoods.net/standard/) suggests that you can't use
cloud services. The important piece is that you need to provide an open alternative to the service
you're using.

An easier approach to comply with the DPG standard is to:

> Use open source components. Delegate the hosting and operation to your cloud provider

## Examples

### Databases

Most applications need to persist data in order to query it at a later time, and most applications
use a database for this purpose. Depending on your system, a relational (RBMS) or a _NoSQL_
datastore will best serve your needs. Either way, you can use open source systems and deletage the
operation, hosting, backup to your cloud provider.


| Open Source | Cloud offering                                                                                                 |
|-------------|----------------------------------------------------------------------------------------------------------------|
| PostgreSQL  | AWS[^aws] RDS, GCP[^gcp] Cloud SQL, Azure Database for PostgreSQL, Scaleway Managed Database for PostgreSQL    |
| MySQL       | AWS RDS, GCP Cloud SQL, Azure Database for MySQL, Scaleway Managed Database for MySQL                          |
| Redis       | AWS ElastiCache, GCP Memorystore, Azure Cache for Redis, Scaleway Managed Database for Redis™                  |


The above table serve as example, the _Venture Fund_ does not endorse any particular Cloud vendor.

> Avoid using a propietary database (e.g. Microsoft SQL Server, Oracle Database) will make your
> application not platform independent

#### Business Source License (BSL) and Server Side Public License (SSPL)

The _Business Source License_ [BSL](https://mariadb.com/bsl11/), and _Server Side Public License_
[SSPL](https://en.wikipedia.org/wiki/Server_Side_Public_License) are recent _"source available"_
licenses that are not [OSI](https://opensource.org/osd) approved.

The main idea of users of this licenses, is to try to block the commercial hosting of their software
by other companies[^bsl].

Using a database like MariaDB Enterprise[^mariadb] released under BSL 1.1 or [Elastic
Search](https://www.elastic.co/pricing/faq/licensing) and
[MongoDB](https://www.mongodb.com/community/licensing) under SSPL, will make your system not
platform independent.


### Application server

#### Notes
* [^aws] Amazon Web Services
* [^gcp] Google Cloud Platform
* [^bsl] [BSL FAQ](https://mariadb.com/bsl-faq-mariadb/)
* [^mariadb] There is a GPL version of MariaDB
