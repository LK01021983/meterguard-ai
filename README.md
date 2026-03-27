# MeterGuard AI
## Intelligent error detection for submetering field service operations

**Building AI course project**

> MeterGuard AI is an AI supported quality assurance system for submetering and technical field service.  
> Its goal is to detect likely installation, documentation, material, and billing errors early enough to prevent rework, invoice delays, complaints, and unnecessary operational cost.

---

## Summary

Field service operations in submetering depend on accurate work execution and complete documentation. MeterGuard AI analyzes completed service jobs and identifies cases that are likely to contain errors, inconsistencies, or billing risks. The system is designed to support technicians, dispatchers, QA teams, and billing staff by making hidden problems visible before they become expensive.

---

## At a glance

| Topic | Description |
|-------|-------------|
| **Project name** | MeterGuard AI |
| **Main idea** | Detect likely service and documentation errors before invoicing or rework |
| **Use case** | Submetering, meter replacement, smoke alarm service, field service QA |
| **Main users** | Technicians, dispatchers, QA teams, billing teams, operations managers |
| **AI methods** | Classification, anomaly detection, NLP, computer vision, hybrid rule based AI |
| **Main benefit** | Fewer repeat visits, fewer invoice issues, better quality control, lower cost |

---

## Background

In field service operations, serious operational problems often start with very small mistakes.

A missing installation photo, an incorrect serial number, an implausible meter value, a material mismatch, or an incomplete service report may seem minor in isolation. But in practice, these issues can lead to rejected invoices, client complaints, repeat visits, internal friction, and unnecessary cost.

This problem is especially relevant in technical service environments involving:

* water meters
* heat meters
* heat cost allocators
* smoke alarms
* other recurring device related service jobs

The challenge is not that people do not care. The challenge is complexity.

Technicians work under time pressure. Dispatchers coordinate large volumes of orders. Back office teams must verify data from different systems. Clients may have different documentation standards. Source data can be incomplete. Materials may not fully match the order. All of this creates an environment where preventable errors are common.

My motivation for this project comes from practical service operations. In real field work, quality issues are often not caused by lack of effort, but by fragmented workflows and overloaded processes. Because of this, I believe AI is most valuable when it supports people rather than replacing them.

MeterGuard AI focuses on a practical operational question:

**Can we identify risky jobs before they create cost, conflict, or delay?**

---

## The problem this project solves

Most organizations only discover quality problems after the damage is already done.

Examples:

* the invoice cannot be processed because proof is missing
* a device exchange has been documented incorrectly
* a serial number does not fit the installed device
* a meter reading appears implausible
* an extra effort claim cannot be billed
* a warehouse discrepancy is discovered too late
* a customer complaint reveals an issue that should have been caught internally

In other words:

**The problem is not only error creation. The problem is late error detection.**

---

## How is it used?

MeterGuard AI is intended as a decision support system inside the operational workflow.

### Typical workflow

1. A technician completes a service job on site  
2. Job data is uploaded from mobile forms, photos, device records, notes, and back office systems  
3. MeterGuard AI evaluates the job using both learned patterns and explicit business logic  
4. The system assigns a risk score and identifies likely issue types  
5. High risk cases are prioritized for manual review  
6. The issue is corrected before invoicing, audit, complaint escalation, or repeat visit

### Example situations

MeterGuard AI could flag jobs where:

* a required photo is missing
* a serial number is unreadable or implausible
* the article number does not fit the expected device family
* duration is suspiciously short or long compared with similar jobs
* a technician note mentions a problem that is not reflected structurally in the report
* an old and new meter pair looks inconsistent
* billing relevant extra work has no supporting evidence
* a completed order still contains contradictory data fields

### Main users

This solution would mainly serve:

* field technicians
* dispatch and planning teams
* quality assurance staff
* billing and finance preparation teams
* subcontractor managers
* operational leadership

### People affected indirectly

* property managers
* utility service providers
* housing companies
* tenants
* client side auditors
* customer service teams

---

## Why this idea matters

AI often gets attention for spectacular consumer products. But in many industries, the most valuable AI systems are much quieter.

A system that reduces avoidable mistakes in daily operations can create real measurable value:

* fewer repeat visits
* fewer rejected invoices
* lower manual QA effort
* more consistent documentation
* less friction between field staff and back office teams
* better trust between service provider and client
* reduced travel and lower emissions through avoided rework

This is the type of AI that interests me most:

**AI that improves reliability, not just novelty.**

---

## Data sources and AI methods

A realistic solution would combine several kinds of data and several kinds of AI.

### Data sources

Possible sources include:

* work orders
* building and apartment information
* device master data
* meter types and article numbers
* installation timestamps
* appointment and route data
* technician IDs and qualification status
* old and new meter readings
* service notes
* customer notes
* photo documentation
* warehouse movements
* returns and discrepancies
* complaint records
* rework cases
* invoice approval or rejection outcomes

### Structured features

Examples:

* service type
* region
* property type
* number of devices in visit
* work duration
* material used vs expected material
* serial number format
* presence of required documentation
* distance between jobs
* technician history for similar issue types
* time since previous service

### Unstructured features

Examples:

* technician comments
* tenant access notes
* issue descriptions
* photo evidence
* extracted text from forms or attachments

---

## AI methods

MeterGuard AI should not rely on one single black box model. A hybrid approach is more realistic and more trustworthy.

### 1. Rule based validation

Some issues are better handled through explicit rules.

Examples:

* mandatory photo missing
* impossible device and article combination
* incomplete billing relevant fields
* invalid serial number pattern
* contradictory data entries

Rule based validation is fast, transparent, and useful as a first safety layer.

### 2. Supervised learning

If historical labels are available, models can learn patterns linked to outcomes such as:

* complaint
* rework
* invoice rejection
* QA correction
* documentation deficiency
* missing billable support

Possible baseline models:

* logistic regression
* random forest
* gradient boosting

These are suitable because they work well on operational tabular data and can remain reasonably interpretable.

### 3. Anomaly detection

Some future issues will not appear in the historical labels. Anomaly detection can identify jobs that differ sharply from normal operational patterns.

Examples:

* unusual duration
* suspicious readings
* rare material and device combinations
* unusual timing patterns
* inconsistent job structures

### 4. Natural language processing

Free text notes often contain important signals that structured fields miss.

Examples:

* "tenant absent"
* "serial unreadable"
* "wrong material"
* "access impossible"
* "device blocked"
* "leak found"
* "exchange incomplete"

NLP can turn these hidden text signals into risk indicators.

### 5. Computer vision

A more advanced version could also check photos.

Examples:

* is the required image present?
* is the image sharp enough?
* does it show the expected device type?
* does it contain a readable serial region?

This is especially useful when photo evidence is mandatory but not reviewed consistently.

---

## Why this is an AI project

This is not just a reporting dashboard.

The difficult part is recognizing patterns across thousands of jobs, incomplete human inputs, mixed data types, and different operational contexts. The system needs to learn from historical outcomes, detect unusual cases, and support human decisions with useful signals.

That makes this a strong AI assisted decision support problem.

---

## Example output

For each completed job, the system could produce something like this:

| Job ID | Risk score | Likely issue | Confidence | Recommended action |
|--------|------------|--------------|------------|--------------------|
| 3019995217 | 87 | Missing support for extra effort | High | Check attachments before invoice release |
| 301852918 | 72 | Unresolved billing irregularity | Medium | Escalate to billing review |
| 301994892 | 64 | Documentation inconsistency | Medium | Compare note, serial number, and material data |

A useful system should not only say **something is wrong**.  
It should also say **why the job was flagged** and **what should be checked next**.

---

## Prototype idea

A realistic first prototype could be built with anonymized historical service data.

### Step 1
Collect 1,000 to 10,000 historical jobs

### Step 2
Create labels such as:

* correct
* documentation incomplete
* probable billing risk
* probable material mismatch
* data inconsistency
* rework likely

### Step 3
Train simple baseline models and compare them against rules only logic

### Step 4
Build a review dashboard for flagged cases

### Step 5
Measure whether the system improves operational outcomes

### Success metrics

* reduction in invoice rejection rate
* reduction in documentation related errors
* reduced repeat visit rate
* lower QA handling time
* higher first pass billing success
* better precision in selecting cases for manual review

---

## Example pseudocode

```python
job = {
    "device_type": "WMZ",
    "duration_minutes": 9,
    "required_photos": 2,
    "attached_photos": 1,
    "serial_match": False,
    "material_code_match": True,
    "comment_text": "old meter removed, serial unreadable",
    "region": "Dresden"
}

risk_score = model.predict_proba(job)[1]

if risk_score > 0.75:
    print("Flag for manual review")
