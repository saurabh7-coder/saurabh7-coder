# Hi, I'm Saurabh 👋

**Backend and Data Engineer** building reliable APIs, data pipelines, distributed systems, and observable software platforms.

I enjoy transforming complex operational requirements into systems that are secure, maintainable, testable, and measurable. My work spans Python data engineering, event-driven ingestion, REST API development, database design, concurrency control, authentication, Docker, CI/CD, and real-time dashboards.

I am focused on understanding not only *how* a system works, but also why a particular architecture, data model, consistency strategy, or failure-handling approach was chosen.

<p align="left">
  <a href="https://github.com/saurabh7-coder">
    <img src="https://img.shields.io/badge/GitHub-saurabh7--coder-181717?logo=github&logoColor=white">
  </a>
  <a href="mailto:230160203101.saurabh@gdgu.org">
    <img src="https://img.shields.io/badge/Email-Contact-EA4335?logo=gmail&logoColor=white">
  </a>
  <img src="https://img.shields.io/badge/Focus-Backend%20%26%20Data%20Engineering-2563EB">
  <img src="https://img.shields.io/badge/Built%20With-Python%20%7C%20Node.js%20%7C%20SQL-16A34A">
</p>

---

## 🎯 What I Build

- **Backend platforms** with secure REST APIs and clear domain boundaries
- **ETL and event pipelines** that clean, validate, transform, and analyze data
- **Distributed ingestion systems** using Kafka, streaming agents, and OLAP stores
- **Data-backed dashboards** for operational and business insights
- **Transaction-heavy applications** with concurrency-safe database operations
- **Tested and containerized software** with automated CI workflows

My strongest interests are backend architecture, distributed data systems, observability, database correctness, performance, and the engineering decisions that keep software reliable under real-world failure conditions.

---

## 🚀 Featured Projects

<table>
<tr>
<td width="50%">

### 🔭 Observability & Log Analytics Platform

An end-to-end observability platform that simulates microservice activity, ingests operational logs, detects anomalies, and presents service health through analytical dashboards.

**Repository:** [observability-log-analytics-platform](https://github.com/saurabh7-coder/observability-log-analytics-platform)  
**Live dashboard:** [Open deployment](https://observability-log-analytics-platfor.vercel.app)

**Architecture:**

```text
Microservice Simulator
          ↓
         Vector
          ↓
         Kafka
          ↓
      ClickHouse
       ↙      ↘
  Grafana     Airflow
                 ↓
           Anomaly tables
                 ↓
            Next.js dashboard
```

**What it demonstrates:**

- Structured JSON log generation
- Kafka-based buffering and backpressure
- Vector log shipping and transformations
- Partitioned ClickHouse storage
- Rolling z-score anomaly detection
- Error-rate and latency analysis
- SLO and error-budget calculations
- Grafana provisioning
- Next.js live visualization
- Nightly scheduled anomaly jobs
- Optional Slack incident notifications
- Synthetic pytest datasets
- GitHub Actions CI
- Docker Compose infrastructure

**Key technologies:**

`Python` `Kafka` `Vector` `ClickHouse` `Airflow` `Grafana` `Next.js` `Docker` `Pytest`

</td>
<td width="50%">

### 🍽️ Smart Restaurant Platform

A comprehensive MERN platform for customer ordering, table reservations, staff operations, administrator workflows, payments, promotions, and reporting.

**Repository:** [smart-restaurant](https://github.com/saurabh7-coder/smart-restaurant)  
**Deployment:** [Open API/server](https://smart-restaurant-server-five.vercel.app)

**Core backend guarantees:**

- Database-enforced prevention of duplicate active reservations
- Unique reservation keys composed from table and seating slot
- Atomic handling of concurrent booking requests
- Server-authoritative item prices and totals
- Integer paise storage instead of floating-point money
- Verified payment signatures and idempotent payment updates
- JWT authentication and bcrypt password storage
- Role-based customer, staff, and administrator access
- Validated status transitions for reservations and orders
- Refunds coordinated with order cancellation
- API rate limits and protected administrative operations

**What it demonstrates:**

- Express controller, route, middleware, and model separation
- MongoDB/Mongoose schema design
- Concurrency testing with real HTTP and database operations
- Domain-specific status state machines
- Payment security and webhook verification
- Referential integrity guards
- Image upload validation
- Environment-based configuration
- React context and route protection
- Production deployment considerations

**Key technologies:**

`React` `Node.js` `Express` `MongoDB` `Mongoose` `JWT` `bcrypt` `Razorpay`

</td>
</tr>
<tr>
<td colspan="2">

### 📊 Student Performance ETL Pipeline

A Python ETL system that extracts academic records, validates data quality, applies transformation rules, loads results into MySQL, and generates SQL performance reports.

**Repository:** [student-performance-data-pipeline](https://github.com/saurabh7-coder/student-performance-data-pipeline)

**Pipeline stages:**

```text
CSV sources
    ↓
Schema validation and extraction
    ↓
Deduplication and data cleaning
    ↓
Grade, percentage, and pass/fail transformations
    ↓
MySQL relational loading
    ↓
SQL reports and academic insights
```

**Engineering features:**

- CSV ingestion and schema checks
- Whitespace normalization and duplicate handling
- Mark-range validation and missing-data quarantine
- Grade and pass/fail calculations
- SQLAlchemy database abstraction
- Separate extract, validate, transform, load, and reporting modules
- CLI pipeline orchestration
- Class, subject, grade, and performance reports
- Environment-based database configuration
- Unit tests for cleaning and transformation behavior

**Key technologies:**

`Python` `Pandas` `NumPy` `SQLAlchemy` `MySQL` `Pytest` `SQL`

</td>
</tr>
</table>

---

## 🧠 Backend Engineering Approach

### API Design

I favor clear resource boundaries, consistent response structures, server-side validation, and explicit HTTP semantics. APIs should make valid operations obvious and invalid operations predictable.

Good APIs need more than working endpoints. They need:

- Stable route contracts
- Authentication and authorization at every protected boundary
- Field-level validation and useful error responses
- Idempotency where repeated operations can occur
- Pagination for unbounded collections
- Correct status codes and lifecycle transitions
- Separation of transport, business, and persistence concerns
- Logs and metrics for debugging and operational visibility

### Concurrency and Correctness

Concurrency is not an edge case; it is a normal property of web applications. I design operations so that simultaneous requests cannot silently create duplicate reservations, accept invalid state transitions, or corrupt financial totals.

Examples of correctness patterns used in my projects include:

- Database-enforced uniqueness constraints
- Compare-and-update payment state changes
- Status transition validation
- Server-derived pricing
- Idempotent payment callbacks
- Referential integrity guards
- Concurrency tests against real systems
- Retries without changing the meaning of an operation

### Security

Security should be enforced at the server boundary, not only in the interface.

I work with:

- bcrypt password hashing
- JWT authentication and configurable expiry
- Role-based authorization
- Uniform login failure responses
- Input and upload validation
- Secret and environment separation
- HMAC-signed payment verification
- CORS and security header configuration
- Rate limiting
- Administrative self-protection rules
- Replay and double-processing prevention

### Money and Business Transactions

Money should never rely on floating-point calculations or browser-provided prices. In transaction-heavy applications, I use:

- Integer minor units
- Server-side price reconstruction
- Immutable order line-item snapshots
- Explicit refund and payment states
- Idempotent state transitions
- Atomic database operations where consistency requires it

### Data Engineering

Reliable data systems begin with understanding their data quality, volume, and failure behavior.

My pipeline work includes:

- Source validation
- Schema and type checks
- Duplicate and missing-value handling
- Range and referential validation
- Incremental transformations
- Relational loading
- Reporting and query design
- Synthetic test data
- Reproducible local execution
- Generated artifact and sample-data handling

### Observability

Systems should answer: **What happened, when, where, and at what scale?**

I use structured events and operational metrics to track:

- Service error rates
- Latency distributions
- Anomaly windows
- Pipeline progress
- State transitions
- SLO and error-budget status
- CI/test/build outcomes

---

## 🛠️ Technical Toolkit

### Languages

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)

### Backend and APIs

`Node.js` · `Express` · `REST` · `JWT` · `bcrypt` · `Role-based Access Control` · `Webhooks` · `Payment Integrations`

### Databases

`MongoDB` · `Mongoose` · `MySQL` · `SQLAlchemy` · `Schema Design` · `Indexes` · `Transactions` · `Query Optimization`

### Data and Streaming

`Pandas` · `NumPy` · `Apache Kafka` · `Vector` · `ClickHouse` · `Airflow` · `Anomaly Detection` · `ETL`

### Frontend

`React` · `Vite` · `Next.js` · `Responsive UI` · `REST Client Integration`

### Engineering and Operations

`Docker` · `Docker Compose` · `Git` · `GitHub Actions` · `Pytest` · `Vercel` · `Grafana` · `Mermaid`

---

## 🔄 Systems I've Studied and Implemented

### 1. Double-Booking Prevention

A reservation system cannot rely exclusively on reading availability and then inserting a record. Two simultaneous requests can pass the same availability check.

My implementation uses a unique database index over the active table and seating slot. Only one record can hold that resource, while cancellation or a no-show releases it for future booking.

### 2. Event-Ingestion Backpressure

Log producers can generate traffic faster than a storage system can ingest it. Kafka acts as a durable shock absorber between Vector and ClickHouse, allowing ingestion to continue independently of downstream speed.

### 3. Rolling Anomaly Detection

Raw events are aggregated into service-minute metrics. Recent rolling baselines are compared against current behavior using z-scores, with minimum-volume and absolute-threshold guards to reduce false positives.

### 4. Server-Authoritative Pricing

A client should transmit item identity and quantity—not trusted prices. The server loads current database prices, applies promotions, calculates totals, and persists an item-level snapshot for auditability.

### 5. State-Machine Workflows

Reservations and orders move through validated lifecycle states. The system prevents illegal jumps such as completing an unpaid order or allowing an unauthorized role to cancel a kitchen process.

### 6. ETL Data Quality

Raw records are not assumed to be trustworthy. The pipeline detects duplicates, invalid ranges, missing marks, inconsistent values, and malformed inputs before loading transformed facts.

---

## 📈 Current Learning Priorities

- Distributed systems fundamentals
- Microservice communication patterns
- Database transaction isolation and locking
- Message delivery guarantees
- Event schemas and data contracts
- Kubernetes and container orchestration
- Cloud databases and managed streaming
- API observability and tracing
- Infrastructure as Code
- OpenTelemetry and distributed tracing
- System design for high-volume services
- Production reliability and incident response

---

## 🧪 Engineering Habits

- Read error logs before changing code
- Reproduce failures with the smallest possible example
- Separate data transformation from side effects
- Use environment variables for runtime configuration
- Keep secrets outside source control
- Prefer explicit state transitions over boolean flags
- Test concurrency-sensitive operations when possible
- Commit small, understandable changes
- Record architectural trade-offs in documentation
- Treat README setup instructions as executable specifications
- Include limitations honestly instead of overstating production readiness

---

## 📊 Project Comparison

| Project | Primary Capability | Architecture Focus | Validation Depth |
|---|---|---|---|
| Observability Platform | Log analytics | Streaming, OLAP, scheduling | Anomaly, simulator, and pipeline tests |
| Smart Restaurant | Business operations | REST, concurrency, authorization | Live concurrency testing and state transitions |
| Student Pipeline | Data processing | ETL, SQL, data quality | Unit tests for cleaning and transformations |

---

## 🌱 Ten-Year Engineering Direction

My long-term goal is to grow into an engineer who can design systems at the intersection of backend reliability and data infrastructure.

The growth path I am targeting:

1. **Strong fundamentals** — HTTP, databases, SQL, data structures, algorithms, and testing
2. **Production backend skills** — secure APIs, queues, caching, monitoring, and deployment
3. **Data platform expertise** — streaming, warehouses, orchestration, schema evolution, and quality
4. **Distributed systems knowledge** — consistency, partition tolerance, retries, and delivery guarantees
5. **Technical leadership** — architecture decisions, code review, mentoring, and operational ownership

I value systems that remain understandable after the original author leaves, scale only where needed, and fail in controlled, observable ways.

---

## 🤝 Let's Connect

- [GitHub](https://github.com/saurabh7-coder)
- [Email](mailto:230160203101.saurabh@gdgu.org)

> Interested in backend engineering, platform engineering, data engineering, and software roles involving distributed systems or scalable applications.
