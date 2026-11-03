# Abylay Iskakov

Software engineer focused on **distributed systems, databases, and cloud infrastructure**.

Software Engineering Intern at **Amazon Web Services** in 2026. I build systems around database infrastructure, concurrency, reliability, and correctness.

Currently building **[Calve](https://github.com/aiskakov28/calve)**, a Jepsen-style correctness tester for Apache Iceberg REST catalogs. Calve has uncovered concurrency bugs across **Apache Iceberg/Hive, Apache Polaris, Lakekeeper, and Nessie**, with findings leading to upstream reports, fix PRs, and maintainer patches.

[LinkedIn](https://linkedin.com/in/abylay-iskakov) · [Email](mailto:aiskakov@u.rochester.edu)

---

## Amazon Web Services

**Software Engineering Intern · Jun-Aug 2026**

- Built application-consistent database cloning across multi-disk EBS volumes, reducing copies that took **hours to near-instant clones**.
- Engineered failure-safe cloning while minimizing write disruption to live databases.
- Built an AI diagnostic agent for on-call engineers that validates proposed root causes against observed evidence.

---

## [Calve](https://github.com/aiskakov28/calve)

**Distributed-systems correctness testing for Apache Iceberg REST catalogs**

Calve sends concurrent commits through real catalog implementations, injects network and process failures, records the raw HTTP history, and replays that evidence offline against correctness models.

**6 workloads · 5 open-source catalogs · 6 fault types · standalone reproducers for every finding**

### Selected impact

- **Apache Iceberg / Hive:** reproduced an acknowledged lost-update bug where **both concurrent transactions return HTTP 200 but one update disappears** · [iceberg#18758](https://github.com/apache/iceberg/issues/18758)
- **Lakekeeper:** found PostgreSQL lock-ordering failures causing **154-182 deadlocks per 200 concurrent commits** · [#2201](https://github.com/lakekeeper/lakekeeper/issues/2201) · maintainers adopted the table-row-first locking direction in [#2219](https://github.com/lakekeeper/lakekeeper/pull/2219)
- **Apache Polaris:** traced a concurrency regression causing **up to 76% of commits to be rejected** instead of retried · [#5907](https://github.com/apache/polaris/issues/5907) · [my fix PR #5921](https://github.com/apache/polaris/pull/5921)
- **Apache Iceberg:** found a JDBC namespace race leaking duplicate-key errors as HTTP 500 instead of 409 · [#18759](https://github.com/apache/iceberg/issues/18759) · [my fix PR #18760](https://github.com/apache/iceberg/pull/18760)
- **Nessie:** isolated a concurrent request-context failure producing intermittent HTTP 500s · [#13271](https://github.com/projectnessie/nessie/issues/13271) · [maintainer fix #13275](https://github.com/projectnessie/nessie/pull/13275)

### What Calve does

`concurrent workloads` → `network / process faults` → `raw HTTP histories` → `offline replay` → `VALID / INVALID / INCONCLUSIVE`

Instead of assuming a timeout or HTTP 500 means failure, Calve preserves the operation as **unknown** until later evidence can prove what happened. Its checkers are tested against deliberately buggy catalog implementations before being trusted against real systems.

[Explore the repository →](https://github.com/aiskakov28/calve)

---

## Tools I work with

**Languages:** Go · Java · Python · C++ · TypeScript · SQL · PowerShell

**Cloud & infrastructure:** AWS (EC2, EBS, Lambda, SQS, EventBridge, CloudWatch) · Docker · Linux · Kafka · CI/CD

**Databases & search:** PostgreSQL · SQL Server · MySQL · Redis · Elasticsearch · pgvector · Apache Iceberg

**Frameworks & tools:** Spring Boot · FastAPI · NestJS · React · Next.js · dbt · Playwright · Toxiproxy

**Systems:** distributed systems testing · fault injection · concurrency · database internals

---

Interested in **distributed systems, database/storage infrastructure, concurrency, and reliability engineering**.
