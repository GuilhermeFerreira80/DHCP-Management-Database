# DHCP Management Database — Centralized Network IP Management

Relational database design and implementation project developed for the **Databases** course in the Informatics Engineering BSc at **ISEC**.

### Overview
This project proposes a centralized relational database architecture implemented in Oracle Database to optimize and scale DHCP server management. By replacing fragmented text configuration files and flat log files, the system establishes a single source of truth for dynamic lease assignment, mitigating human configuration errors, preventing IP conflicts, and enabling real-time network telemetry and auditing.

### Database Architecture & Data Modeling
- Core Network Entities: Structured modeling of routing gateways (`Router`), logical networks (`Subrede`), IP ranges (`Pool_IP`), physical hardware (`Dispositivos` bound by MAC address), and static IP reservations (`Reservas`).
- Transactional Lease Tracking: Detailed state logging via the `Lease` entity, capturing precise assignment periods (start/end timestamps), allocation state, and pool mappings.
- Audit Trail & Access Control: Comprehensive tracking of hardware and service anomalies (`Log_Evento`, `Tipo_Evento`), coupled with role-based administrative access control (`Users`, `Cargo`).
- Relational Integrity: Enforced constraints including composite primary keys, foreign key cascades, and indexing strategies tailored for the Oracle RDBMS engine.

### Analytical Views & Administrative Features
- Active Lease Surveillance: Instant visibility into currently leased IP addresses and associated physical endpoints.
- Pool Utilization Telemetry: Dedicated views monitoring subnet saturation and occupancy rates to guide infrastructure capacity planning.
- Forensic Historical Logs: Streamlined queries across chronological event logs to simplify compliance audits and quickly detect network anomalies.

### Tech Stack
- RDBMS: Oracle Database / Oracle SQL Developer
- Modeling Tools: Conceptual Data Model (CDM) and Physical Data Model (PDM)
- Scripting: SQL (DDL schema generation and constraint configuration)
