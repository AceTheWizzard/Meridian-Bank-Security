# Meridian Community Bank — Security Program & Threat Analysis Portfolio

**A fictional case study in securing a community bank.**

Meridian Community Bank is a fictional two-branch community bank (HQ in
Charlotte, NC, branch in Manhattan) with ~120 employees. This project is a
complete, ground-up security program built for that organization: its network
and data, the regulations it must meet, its policies, the threats targeting
it, and the gaps between the two.

The goal is to demonstrate applied security thinking — not just knowing
frameworks, but connecting **threats → controls → business impact** for a
specific, realistic environment.

---

## ⚠️ About This Project

- **Meridian Community Bank is fictional.** All people, systems, and events
  are invented — but modeled on real-world community bank structures and
  publicly documented attacks on the financial sector.
- Policies are informed by NIST CSF, CIS Controls v8, FFIEC guidance, and
  GLBA/NY DFS requirements — adapted to Meridian, with rationale for each
  adaptation documented alongside them.
- Threat analysis references real vulnerabilities, threat actors, and breach
  case studies, and assesses their specific impact on this organization.

---

## 📁 Repository Structure

| Chapter | Contents | Status |
|---------|----------|--------|
| [01 — Company Profile](/01-company-profile) | Org chart, business lines, IT staffing | ✅ |
| [02 — Network Architecture](/02-network-architecture) | Topology, asset inventory, data flows | ✅ |
| [03 — Data Inventory](/03-data-inventory) | Crown jewels, classification, access | ✅ |
| [04 — Regulatory Landscape](/04-regulatory-landscape) | GLBA, FFIEC, PCI DSS, NY DFS 500 | 🚧 |
| [05 — Risk Assessment](/05-risk-assessment) | Methodology + risk register | 🚧 |
| [06 — Policies](/06-policies) | Access control, IR, vendor mgmt, & more | 🚧 |
| [07 — Threat Landscape](/07-threat-landscape) | OWASP analysis + adversary profiles | 🚧 |
| [08 — Controls Gap Analysis](/08-gap-analysis) | Mapping threats to controls, finding gaps | 🚧 |
| [09 — Incident Case Studies](/09-incident-case-studies) | Simulated attacks, after-action reports | ⏳ planned |

**Legend:** ✅ complete · 🚧 in progress · ⏳ planned

---

## 🔍 Highlights

A few pieces of this project best demonstrate the skills I'm building:

- **[Vendor/Third-Party Risk Policy](/06-policies/06.4-vendor-management.md)** —
  Meridian's crown-jewel system (core banking) is hosted by a third party. This
  policy addresses how a bank this size actually controls risk it can't patch.
- **[Broken Access Control: Impact on Meridian](/07-threat-landscape/appsec/01-broken-access-control)** —
  how one OWASP vulnerability class plays out against a real architecture, not
  in the abstract.
- **[Controls Gap Analysis](/08-gap-analysis/README.md)** — the capstone:
  where Meridian's policies leave it exposed to the threats profiled here.

*(Update these links to whichever chapters you finish first.)*

---

## 🛠 Skills Demonstrated

- Risk assessment methodology (NIST SP 800-30 informed)
- Security policy authoring mapped to NIST CSF & CIS Controls v8
- Regulatory analysis: GLBA Safeguards Rule, NY DFS 500, FFIEC, PCI DSS
- Threat analysis: MITRE ATT&CK mapping, OWASP Top 10, adversaries in the
  financial sector
- Applying all of the above to a realistic mid-size environment with realistic
  (i.e., limited) staffing

---

## 📈 Ongoing

This is a living project. I add threat write-ups as notable campaigns or
vulnerabilities hit the financial sector, and revisit policies as frameworks
update. Latest activity:

- **[date]** — Added threat write-up: [name]
- **[date]** — Published Access Control policy
- **[date]** — Initial release: company profile, network, data inventory

---

## 👤 Author

**Zachary Atwell**
BAS in Information Technology (Networking concentration), AS in Cybersecurity
[LinkedIn] · [Resume] · [Email]
