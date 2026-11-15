# CIMERWA Cement Dealer Stock Reconciliation and Revenue Integrity System

**Student Name:** DUSHIMIMANA Emmanuel  
**Student ID:** 20251SEN201  
**Email:** dushimimanaemmanuel92@gmail.com  
**Course Code & Name:** INSY 8311 & Database Development with PL/SQL  
**Instructor:** Eric Maniraguha (AUCA)  
**Academic Year:** 2026–2027 (Semester I)  
**Group:** Monday Grp I (No. 6) — **Status:** APPROVED ✅  
**Repository:** [https://github.com/dushimimanaemmy/Emmanuel_20251SEN201_cimerwaTrack](https://github.com/dushimimanaemmy/Emmanuel_20251SEN201_cimerwaTrack)  

---

## 1. Project Overview & Problem Statement
CIMERWA cement dealers across Rwanda experience persistent financial losses from stock theft and revenue leakage. Unmonitored delivery drivers secretly siphon bags during transit from factory depots to retail points, while storefront employees exploit manual paper ledgers to underreport daily cash sales, manipulate selling prices, and retain cash payments. Because dealership owners cannot be physically present at all unloading bays and sales counters, these discrepancies remain undetected until delayed month-end physical stock counts.

This system provides an Oracle PL/SQL database solution that enforces an unbroken digital chain of custody from warehouse dispatch to retail checkout. Built-in database triggers detect delivery mismatches in real time, block unauthorized pricing, and log all table modifications into a tamper-proof audit trail. At the end of each billing cycle, an automated reconciliation engine compares dispatched stocks against remaining inventory and verified bank deposit slips, providing business owners with mathematically verified revenue statements and pinpointing leakage sources.

## 2. Project Objectives
- Establish an automated digital tracking pipeline for cement bags from warehouse dispatch to customer checkout.
- Deploy database triggers to catch transit delivery theft, price manipulation, and unrecorded cash sales upon entry.
- Build an automated PL/SQL monthly reconciliation package calculating exact stock gaps and missing revenues.
- Enforce non-repudiation using database-level audit shadow tables.
- Deliver an interactive User Interface (Python Streamlit / Oracle APEX) connecting live to Oracle Database.

## 3. Data Source
- **Primary Source:** Kaggle Cement Sales & Demand Dataset (`https://www.kaggle.com/datasets/kishorkhengare/cement-sales-demand`) by Kishor Khengare.
- **Scope:** 150+ monthly production and sales records without personal identifiable information (PII), used to calibrate normalized transactional tables and realistic Rwandan pricing benchmarks (8,500 RWF per 50kg bag).

## 4. Planned Schema (Focused 6-Table Relational Schema in 3NF)
- **`DEALERS`**: Master dealer profiles and official price per bag.
- **`DISPATCH_ORDERS`**: Factory/depot dispatch logs with truck plate, driver name, and bag counts.
- **`STOCK_RECEIPTS`**: Arrival receipts with trigger-generated shortage calculations and theft flags.
- **`DAILY_SALES`**: Point-of-sale transaction logs tracking sales volume, price, and cashier.
- **`MONTHLY_RECONCILIATION`**: Monthly audit records computing stock gaps and revenue gaps against bank receipts.
- **`AUDIT_LOG`**: Shadow table recording all DML modifications, timestamps, and session users.

## 5. Planned PL/SQL Features
- **Triggers:** `trg_check_transit_theft`, `trg_enforce_price_sales`, `trg_audit_sales`.
- **Packages:** `pkg_cimerwa_reconciliation` (containing `sp_run_monthly_recon`).
- **Functions:** `fn_calculate_stock_gap`, `fn_calculate_revenue_gap`.
- **Jobs:** Scheduled nightly audits using `DBMS_SCHEDULER`.

## 6. Innovation Component
- **User Interface:** Interactive Python Streamlit / Oracle APEX web application connecting live to Oracle Database, allowing dealer owners to review reconciliation reports, delivery shortages, and theft alerts in real time.

## 7. Phase 0 Deliverable Links
- [Research Log](docs/research/research_log.md)
- [Project Proposal (2-Page)](docs/proposal/project_proposal.md)
- [Presentation Slides (12 Slides)](docs/presentation/presentation_slides.md)
- [Benchmark Data Overview](data/data_source_description.md)
