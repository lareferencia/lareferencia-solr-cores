# LA Referencia Solr Configsets

Configuration repository included in the platform workspace lock. It has no Maven
artifact and does not inherit the parent POM version.

The repository contains `biblio`, `entity`, `historic`, `networks`, `oai`,
`projects`, `vstats` and the `solr.v9` configuration tree. Some original configsets
are historical, including the older Lucene compatibility settings in `oai`.

The current platform Compose image uses Solr 9.11. Its staging script takes the
active `oai` configset from `lareferencia-oai-pmh/solr.core/oai/` and `biblio`, jars
and import resources from the separately managed VuFind checkout. It copies those
sources into generated `Docker/solr/` directories; edit the owning source instead
of the generated copies.

See the [Solr lifecycle guide](../Docker/README.md) for staging,
configuration updates and schema migration. VuFind is external to the platform
lock and release archives even when Docker prepares its checkout.
