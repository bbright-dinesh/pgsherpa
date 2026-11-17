# Credits and thanks

pgSherpa's checks were not invented from scratch. Most of its SQL queries, the signals they look for and the
thresholds they warn at were learned from, and adapted from, the open-source PostgreSQL tools below. Their authors
worked these out over many years on real servers and shared them with everyone.

**Thank you** to every author and contributor of these projects. pgSherpa would not exist without your work.

## Where the SQL queries come from

| Project | By | What pgSherpa took from it | Licence |
|---|---|---|---|
| [postgres_exporter](https://github.com/prometheus-community/postgres_exporter) | The Prometheus Authors, William Rouesnel | Collector queries: WAL directory size, replication slots' safe WAL size, the WAL receiver, lock table use, role changes, bgwriter and checkpointer. The alert rules of its postgres_mixin (too many locks, timed-checkpoint ratio). | Apache-2.0 |
| [pgMonitor](https://github.com/CrunchyData/pgmonitor) | Crunchy Data, Snowflake | Exporter queries and alert rules: WAL activity, data checksum failures, settings waiting for a restart, emergency vacuum thresholds, recovery status switch, statements writing the most WAL. | Apache-2.0 |
| [pgwatch](https://github.com/cybertec-postgresql/pgwatch) | CYBERTEC PostgreSQL International | metrics.yaml: WAL size, archiver backlog, database stats, recovery conflicts, logical decoding spilling to disk, logical subscriptions stuck in sync, functions without a search_path, clients without TLS, disabled triggers, WAL buffers full, parallel workers not launched, session counters, leaving utility statements out of pg_stat_statements. | BSD-3-Clause |
| [pgmetrics](https://github.com/rapidloop/pgmetrics) | RapidLoop | Collector queries: WAL file counts, settings, table bloat, conflicting slots, the WAL receiver, NOTIFY queue use, disabled triggers. | Apache-2.0 |
| [check_postgres](https://github.com/bucardo/check_postgres) | Greg Sabino Mullane | archive_ready, autovac_freeze (90 / 95 %), bloat, checkpoint age, pgbouncer_backends and pgbouncer_maxwait. | BSD-2-Clause |
| [pgsql-bloat-estimation](https://github.com/ioguix/pgsql-bloat-estimation) | Jehan-Guillaume (ioguix) de Rorthais | The way to estimate table bloat from planner statistics, with no extension and no table scan. | BSD-2-Clause |
| [pgcenter](https://github.com/lesovsky/pgcenter) | Alexey Lesovsky | Snapshotting pg_stat_statements and diffing the snapshots; the maintenance progress views. | BSD-3-Clause |
| [pg_activity](https://github.com/dalibo/pg_activity) | Julien Tachoires, Dalibo | Temporary files on disk right now. | PostgreSQL |
| [Datadog PostgreSQL integration](https://github.com/DataDog/integrations-core/tree/master/postgres) | Datadog | The last checkpoint from pg_control, idle transactions holding exclusive locks, pg_stat_wal, the progress views, session counters. | BSD-3-Clause |
| [pganalyze collector](https://github.com/pganalyze/collector) | pganalyze | pg_stat_statements snapshots (text only for the top entries, columns by extension version), per-table stats, insert-only tables vacuum never visits, the xmin horizon broken down by what holds it. | BSD-3-Clause |
| [Zabbix agent 2 PostgreSQL template](https://github.com/zabbix/zabbix/tree/master/templates/db/postgresql_agent2) | Zabbix | Signals and thresholds. | AGPL-3.0 |
| [pg_catcheck](https://github.com/EnterpriseDB/pg_catcheck) | EnterpriseDB | The idea behind the catalog consistency check: catalog rows pointing at objects that don't exist. | PostgreSQL |

Thresholds that none of these define are pgSherpa's own.

## Extensions pgSherpa works with

- [pgsentinel](https://github.com/pgsentinel/pgsentinel) (PgSentinel, PostgreSQL licence): session history, from its
  sampled `pg_active_session_history`.
- [HypoPG](https://github.com/HypoPG/hypopg) (PostgreSQL licence): the index advisor tries each candidate index as a
  hypothetical one, so nothing is written.
- `amcheck` and `pg_visibility`, which ship with PostgreSQL: the Integrity checks.

## PostgreSQL

Every query reads PostgreSQL's own statistics views and catalogs. The `\h` syntax help in the SQL box is taken from
the PostgreSQL documentation for each version, © The PostgreSQL Global Development Group,
PostgreSQL licence. Thank you to everyone who builds and documents PostgreSQL.

## Something missing or wrong?

If you wrote one of these projects and want the credit worded differently, or we used your work and missed you
here, please open an issue at https://github.com/bbright-dinesh/pgsherpa/issues and we will put it right.
