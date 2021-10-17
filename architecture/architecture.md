# Architecture

## Sustainability chapter template

Add a chapter to your architecture or design document. Feel free to copy [the  sustainability chapter template](softwareArchitectureSustainabilityChapter.md) into your document and elaborate it.

## Infrastructure as Code

### Split resources into persistent and runtime

When architecting your infrastructure-as-code you can split your resources into a `persistent` part and a `runtime` part, where the latter contains resource demanding runtime components that you can destroy when not in use and the former contains cheaper components that may require some manual setup like key vault.

An example system in Azure could be:

| Persistent      | Runtime         |
|-----------------|-----------------|
| storage account | app service plan|
| key vault       | function app    |
| app insights    | service bus     |
| VNet            | API management  |
| DNS zone        |                 |

Advantages:

* Save resources and cost when an environment is not in use. Pipelines can be set up to create and destroy on a schedule.
* Enable you to create beefy test environments that would otherwise be too costly and cumbersome to set up

Disadvantages:

* A little more complexity

## References

* Read up on concepts at [Principles.Green](https://principles.green/)

## TODO write about

Efficient data retrieval patterns

Network efficiency (HTTP/2, gRPC)
