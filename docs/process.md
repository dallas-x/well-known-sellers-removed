Perfect — here’s the updated Process Document with the added context around evidence requirements for resolution or decommissioning. I’ve added a new section called “Evidence Requirements” and revised Step 4 to include this verification.

⸻

Process Document: Splunk Logging Compliance Review

Owner: [Team Name Taking Ownership]
Prepared by: [Your Name / Team]
Last Updated: [Date]

⸻

Purpose

This process guides how to identify, assess, and remediate non-compliant assets (machines/servers) that are not logging to Splunk. The objective is to maintain visibility and accountability for all critical systems and ensure full compliance with logging and monitoring requirements.

⸻

Scope
	•	Rolling weekly analysis of system log activity
	•	Monthly update to the official asset inventory
	•	Investigation, documentation, and resolution of non-logging systems
	•	Use of dashboards and app tools to triage and track progress

⸻

Key Concepts
	•	Non-compliant Asset: A system that failed to log within a defined rolling time window.
	•	Threshold: Percent of missed logging intervals (e.g., 90% = only 1 week of logs in 10 weeks).
	•	Critical System: A machine essential to business continuity or security.
	•	Operational Status: Indicates whether the system is active, offline, or decommissioned.

⸻

Data Update Frequency

Data Element	Update Frequency
Log Activity Check	Weekly (Rolling Window)
Asset Inventory List	Monthly


⸻

Tools

1. Splunk Reporting Dashboard
	•	Asset list with:
	•	Hostname, Machine ID
	•	Reporting thresholds
	•	Operational status
	•	Report month
	•	Use for prioritization and triage

2. Splunk Interactive Compliance App
	•	Asset records with:
	•	Hostname, threshold
	•	Status selector
	•	Comment field
	•	Exception tracking
	•	Alert suppression

⸻

Evidence Requirements

All resolution statuses must be backed by evidence, depending on the outcome:

Outcome	Required Evidence
✅ Resolved (logging restored)	A valid RITM, Change, or Incident ticket showing the fix was implemented (e.g., reinstall agent, open port, etc.)
🛑 Decommissioned / Non-Operational	Valid evidence that the asset is no longer in use (e.g., CMDB entry, retirement ticket, or confirmation from Infra/Platform owner). The asset should be flagged for removal from the critical asset list.
📝 Exception Filed	Exception ticket ID or link must be recorded in the Exception field of the app.
🚫 Suppressed	Must include a justification and supporting context in the comments field.


⸻

Weekly Workflow

Step 1: Open Dashboards
	•	Access the Splunk Reporting Dashboard and Compliance App
	•	Confirm data is current for the week and month

⸻

Step 2: Triage and Prioritize

Sort systems by:
	1.	Operational Status = Active
	2.	Criticality (if known)
	3.	High threshold of missed logs
	4.	Sudden change in logging pattern

⚠️ Don’t prioritize only by threshold—critical assets that recently stopped logging take precedence.

⸻

Step 3: Investigate

For each non-compliant system:
	•	Validate if the system is:
	•	Logging but misclassified
	•	Inactive or decommissioned
	•	Still active but misconfigured
	•	Use secondary systems (CMDB, inventory, platform tools) to validate operational status
	•	Collaborate with system owners or platform teams if needed

⸻

Step 4: Document in App + Attach Evidence

In the Interactive Compliance App:
	•	Add a comment summarizing the investigation
	•	Update the Status using one of the following:
	•	✅ Resolved – Must include ticket number
	•	🛑 Non-Operational / Decommissioned – Must include evidence source
	•	🟡 Work in Progress
	•	📝 Exception Filed – Include exception ticket/link
	•	Toggle Suppress Alert only with justification
	•	Ensure all supporting ticket numbers or validation are entered in the Comment or Exception fields

⸻

Step 5: Escalate Critical Issues

Immediately escalate if:
	•	A critical asset has recently stopped logging
	•	No explanation can be found after investigation

Include:
	•	Hostname, ID, logging gap timeframe
	•	Any evidence or known issues
	•	Escalate to: [Escalation DL or Contact]

⸻

Optional Weekly Summary
	•	of systems reviewed
	•	resolved (with evidence)
	•	non-operational (pending removal)
	•	escalations or exceptions

⸻

Analyst Tips
	•	Always validate before marking anything as resolved or decommissioned.
	•	No undocumented assumptions—log evidence or source of truth.
	•	Review clusters or tags for pattern detection (e.g., platform outages).
	•	If unsure, escalate early instead of suppressing without review.

⸻

Contacts

Topic	Contact
Tool/Dashboard Issues	[Owner Name]
Asset Verification	[CMDB Owner / Infra Contact]
Escalation Path	[Security or Infra Escalation Contact]


⸻

Would you like me to format this as:
	•	✅ PDF or Word handoff doc
	•	✅ Confluence-ready markdown or page structure
	•	✅ Email summary for quick rollout

Let me know and I’ll generate the format you need.
