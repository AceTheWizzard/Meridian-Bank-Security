# Chapter 03 — Data Inventory

## Purpose

Before Meridian can protect anything, it has to know what it holds, where 
it lives, and who can touch it. This chapter is the authoritative inventory 
of Meridian's data assets (the "crown jewels"), their classification, and 
their regulatory drivers. Every policy in Chapter 06 and every threat 
write-up in Chapter 07 references this inventory.

---

## Data Classification Scheme

Meridian uses a four-tier scheme adapted from common practice and aligned 
to FFIEC and NY DFS 500 expectations:

| Tier | Definition | Handling examples |
|---|---|---|
| **Restricted** | Data whose breach would cause severe customer or regulatory harm (identity theft, fraud, legal exposure) | Encryption at rest & in transit required; access on need-to-know; no removable media without approval |
| **Confidential** | Internal business data whose disclosure would harm Meridian competitively or operationally | Encrypted in transit; department-level access |
| **Internal** | Day-to-day operational data, not for public release but low-harm if seen | Standard access controls |
| **Public** | Approved for public disclosure (marketing, rates, disclosures) | Integrity controls only |

---

## Data Inventory

### Restricted — Crown Jewels

| # | Data | Primary system(s) | Format / Location | Owner | Access | Regulatory driver |
|---|---|---|---|---|---|---|
| R1 | Customer PII — names, SSNs, DOBs, contact info | Fiserv core (hosted); Loan origination SaaS | Vendor-hosted cloud; documents in M365 SharePoint | COO | Core: bank staff by role; SaaS: lending team | GLBA Safeguards, NY DFS 500 |
| R2 | Account & transaction data — balances, numbers, history | Fiserv core (hosted) | Vendor-hosted cloud | COO | Bank staff by role | GLBA, PCI DSS |
| R3 | Cardholder data — PANs (primary account numbers) | Fiserv core + ATM gateway | Vendor-hosted cloud; transient at ATM | COO | Minimal scope; teller terminals only | PCI DSS |
| R4 | Loan & mortgage files — SSNs, income docs, appraisals, credit reports | Loan origination SaaS; M365; imaging system | SaaS + SharePoint | Head of Lending | Lending & processing staff | GLBA, FCRA |
| R5 | Wire transfer instructions & treasury data | Core banking, email (M365) | Vendor-hosted + mailboxes | Head of Operations | Wire room (3 staff) | GLBA, OFAC |
| R6 | Wealth management client records & account values | Portfolio SaaS, M365 | Vendor-hosted | Head of Wealth Mgmt | Wealth advisors (6) | GLBA; fiduciary duties |
| R7 | Employee PII — SSNs, payroll, benefits, health | M365 / HR SaaS | SharePoint + SaaS | HR Manager | HR (2), self-access | IRS/SSA rules, NC & NY state law |
| R8 | Online banking credentials & MFA tokens | Fiserv online banking platform | Vendor-hosted | CIO | Fiserv + customer | GLBA, NY DFS 500 (MFA req.) |

### Confidential

| # | Data | Primary system(s) | Owner | Notes |
|---|---|---|---|---|
| C1 | Board & executive communications | M365 | CEO's office | Potential insider/insider-adjacent target |
| C2 | IT configurations, network diagrams, credentials | Local servers (VLAN 10), AD | CIO | If stolen, maps the whole kingdom |
| C3 | Security logs & SIEM data | SIEM / logging platform | Security Analyst | NY DFS 500 requires 5-year retention — see note |
| C4 | Vendor contracts & SOC 2 reports | M365 SharePoint | CIO | Includes the Fiserv agreement — see Vendor policy |
| C5 | Bank secrecy / AML records | Core + M365 | Compliance Officer | Climate of strict BSA/AML penalties |

### Internal

| # | Data | Primary system(s) | Owner |
|---|---|---|---|
| I1 | Policies & procedures (non-public) | M365 SharePoint | CISO/CIO |
| I2 | Marketing plans & customer lists | Marketing SaaS | Marketing |
| I3 | Help desk tickets & endpoint inventory | Ticketing SaaS | IT |

### Public

| # | Data | Primary system(s) | Owner |
|---|---|---|---|
| P1 | Rates, fees, marketing content | Website (Fiserv-hosted) | Marketing |

---

## '=' Data Maps to Assets & Facilities

Connecting Chapter 02 (network) and this inventory:

| Data (from above) | Device(s) that touch it | Location | Exposure path |
|---|---|---|---|
| R1, R4 | Workstations (VLAN 20), laptops | Both branches + remote | Email, downloads, misdirected sends |
| R2, R3 | Teller terminals, ATMs (VLAN 40) | Both branches | Skimming, terminal compromise |
| R5 | Wire room workstations | Charlotte HQ | BEC via email; compromised credentials |
| C2 | All servers (VLAN 10), mgmt stations | Charlotte HQ | Lateral movement post-compromise |
| R1, R6 | Everything | Remote/hybrid staff laptops | Unmanaged endpoints, travel |

---

## Repeat Loss Data Flows (worked examples)

These narratives are the inventory in motion — most useful to your Chapter 
07 threat write-ups later.

### Flow 1 — A customer's mortgage application (R1, R4)
Application submitted online (Loan SaaS) → processor downloads income docs 
to laptop → stores working copies in SharePoint → final loan recorded in 
Fiserv core → paper originals imaged & shredded. 
**Risk surfaced:** customer PII exists simultaneously in three vendor clouds 
and on endpoint devices — no single place to "delete" it.

### Flow 2 — A commercial wire transfer (R5)
Client phones or emails wire instructions → wire room verifies via call-back 
procedure → transfer initiated in Fiserv → confirmation logged. 
**Risk surfaced:** call-back verification is only as good as the phone 
number on file — classic BEC territory (combining phone + email fraud is 
the modern pattern).

### Flow 3 — Backups (R1–R7 aggregated)
Nightly: Fiserv & SaaS data (vendor-side, contractual RPO) + local servers 
& file shares → on-site backup NAS with immutable copies, per Ch. 02. 
**Risk surfaced:** much of the Restricted data has *no* Meridian-controlled 
backup — recovery depends on Fiserv's DR, which is only as strong as the 
contract. See gap analysis, Chapter 08.

---

## Known Gaps in the Inventory (deliberate, documented)

- **Shadow SaaS likely exists** — staff probably use personal email/USB/apps 
  despite policy; realistically unquantifiable at this staffing level. 
  Addressed through Acceptable Use policy + DLP-lite in M365.
- **Paper still matters** — loan files move physically between tellers and 
  operations before imaging. Cleaning-desk and shredding standards belong 
  in the Data Handling policy (Ch. 06).
- **PCI scope is intentionally narrow** — Meridian is likely PCI SAQ-A 
  (card data handled by Fiserv), keeping actual PAN storage off Meridian 
  systems. This is a deliberate architectural decision, not an oversight.

