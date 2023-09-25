---
title: "Cloud usage"
icon: "ti-cloud"
description: "The use of cloud services and platform independence"
type: "docs"
---

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
datastore will best serve your needs. Either way, you can use open source systems and delegate the
operation, hosting, backup to your cloud provider.


| Open Source | Cloud offering                                                                                                 |
|-------------|----------------------------------------------------------------------------------------------------------------|
| PostgreSQL  | AWS[^aws] RDS, GCP[^gcp] Cloud SQL, Azure Database for PostgreSQL, Scaleway Managed Database for PostgreSQL                |
| MySQL       | AWS RDS, GCP Cloud SQL, Azure Database for MySQL, Scaleway Managed Database for MySQL                          |
| Redis       | AWS ElastiCache, GCP Memorystore, Azure Cache for Redis, Scaleway Managed Database for Redis™                  |

The above table serve as example, the _Venture Fund_ does not endorse any particular Cloud vendor.

> Avoid using a proprietary database (e.g. Microsoft SQL Server, Oracle Database) will make your
> application not platform independent

### Alternative to non open source components

| Component                    | Open Source alternative                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Confluent Kakfa              | [Apache Kakfa](https://kafka.apache.org/)                                                                           |
| Elastic Search               | [OpenSearch](https://opensearch.org/)                                                                               |
| MongoDB                      | [FerretDB](https://www.ferretdb.io/)                                                                                |
| Mapbox                       | [Leaftlet](https://leafletjs.com/)                                                                                  |
| Google Maps                  | [Leaftlet](https://leafletjs.com/)                                                                                  |


| Service                      | Open source                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Auth0                        | OpenID Connect based authentication ([Keycloak](https://www.keycloak.org/), [Ory](https://www.ory.sh/open-source/)) |
| Firebase                     | [Supabase](https://supabase.com/docs/guides/self-hosting), [Etebase](https://www.etebase.com/)                      |
| Google Cloud Messaging (GCM) | [UnifiedPush](https://unifiedpush.org/)                                                                             |

##### Notes

[^aws]: Amazon Web Services
[^gcp]: Google Cloud Platform
