# pgSherpa

pgSherpa is a PostgreSQL companion for macOS. Its website is https://cortexridge.com/

- Downloads: the [Releases](https://github.com/bbright-dinesh/pgsherpa/releases) of this repository (one disk image for Apple silicon, one for Intel), or the Mac App Store.
- Support: https://cortexridge.com/pgsherpa/support/ and the Issues tab of this repository. Never post passwords, tokens or connection strings.
- Privacy policy: https://cortexridge.com/pgsherpa/privacy/

The pages that used to be served from this repository now forward to those addresses.

## Credits and thanks

pgSherpa's SQL queries, and the signals and thresholds behind its checks, were learned from and adapted from these
open-source PostgreSQL projects. Thank you to their authors and contributors:

[postgres_exporter](https://github.com/prometheus-community/postgres_exporter) ·
[pgMonitor](https://github.com/CrunchyData/pgmonitor) ·
[pgwatch](https://github.com/cybertec-postgresql/pgwatch) ·
[pgmetrics](https://github.com/rapidloop/pgmetrics) ·
[check_postgres](https://github.com/bucardo/check_postgres) ·
[pgsql-bloat-estimation](https://github.com/ioguix/pgsql-bloat-estimation) ·
[pgcenter](https://github.com/lesovsky/pgcenter) ·
[pg_activity](https://github.com/dalibo/pg_activity) ·
[Datadog PostgreSQL integration](https://github.com/DataDog/integrations-core/tree/master/postgres) ·
[pganalyze collector](https://github.com/pganalyze/collector) ·
[Zabbix PostgreSQL template](https://github.com/zabbix/zabbix/tree/master/templates/db/postgresql_agent2) (ideas only, none of its code) ·
[pg_catcheck](https://github.com/EnterpriseDB/pg_catcheck)

It also works with the [pgsentinel](https://github.com/pgsentinel/pgsentinel) and
[HypoPG](https://github.com/HypoPG/hypopg) extensions, and its SQL syntax help comes from the PostgreSQL documentation.
[CREDITS.md](CREDITS.md) says what came from each project, with its licence.
