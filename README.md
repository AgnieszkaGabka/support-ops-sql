**# Support Ops SQL (Ticketing Analytics)**



A small SQL project that simulates a customer support ticketing system and answers core operational questions:

SLA performance, backlog health, agent workload, and drivers of reopens/escalations.



\## Business questions (v1)

\- How many tickets are created and resolved per day?

\- What is the current backlog and how is it trending?

\- Which categories generate the most volume?

\- What is the first response time distribution?

\- Which agents handle the most tickets and which tags appear most often?



\## Data model (v1)

Tables:

\- `customers` — who reports issues

\- `agents` — support team members

\- `tickets` — the main ticket entity

\- `interactions` — messages/updates related to tickets (used for first response time)



\## How to run (SQLite)

1\. Create a SQLite database in DBeaver (e.g. `support\_ops.db`)

2\. Run:

&nbsp;  - `sql/01\_schema.sql`

&nbsp;  - `sql/02\_seed.sql`

&nbsp;  - `sql/03\_queries\_day1.sql`



\## Tech notes

\- Dataset is intentionally small at the start (seed v1) to validate logic.

\- Next steps will expand data volume and add views for daily metrics \& SLA.

## Day 2
SLA and performance metrics:
- Cycle time (created -> resolved) + SLA breach flag
- SLA compliance rate (resolved tickets)
- SLA breaches by priority
- Avg time to resolve by category
- Agent workload and resolution performance
- First response time proxy (created -> first agent message)

## Day 3
Time-based analysis:
- Tickets created and resolved per day
- Backlog snapshot by creation date
- SLA compliance trend over time
- Ticket distribution by weekday

## Day 4
Business-oriented analysis:
- Ticket load by customer segment
- Resolution time by segment
- Workload distribution by team
- Escalation proxy (L1 -> L2 involvement)
- Priority vs SLA breach analysis


## Project Structure

sql/
  01_schema.sql
  02_seed.sql
  03_queries_day1.sql
  04_queries_day2_sla_agent_performance.sql
  05_queries_day3_trends.sql

The project is structured incrementally:
- Day 1: baseline KPIs
- Day 2: SLA and agent performance
- Day 3: time-based trends




