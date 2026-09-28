# Editable prompt: recreate the Azure VM provisioning swimlane flowchart

Copy the prompt below into a tool that can produce diagrams.net / draw.io XML. Edit the fields in **Customise first** and any process steps before using it.

---

## Customise first

- Diagram title: **DHCW – End-to-End Microsoft Azure Virtual Server Provisioning Process**
- Organisation: **DHCW**
- Output filename: **DHCW_Azure_Virtual_Server_Provisioning_Process.drawio**
- Document status: **Draft v1.0**
- Preferred automation: **approved Terraform modules through CI/CD pipelines**
- Monitoring product: **Site24x7**
- Lane names, if your team structure differs: **Service Requester; Architecture & Design; Cloud Platform Engineering; Network & Security; Infrastructure Operations; Monitoring & Backup; Service Management**
- Any local approvals, owners or technical standards to substitute: **[EDIT HERE]**

## Prompt

Create a detailed, editable, Visio-style **horizontal swimlane flowchart** for the end-to-end Microsoft Azure virtual server provisioning process described below. Produce a complete, valid **diagrams.net / draw.io `.drawio` XML document** that can be saved with the output filename above and opened directly in diagrams.net. All lanes, labels, shapes, connectors, decisions, side panels, and notes must be native editable draw.io elements; do not flatten the diagram into an image.

Use the title, organisation, document status, terminology, product names, and team names in **Customise first**. Treat the workflow as a draft representation of the attached diagram, not as confirmation that it is an approved organisational standard. Do not invent an approval, control, or technical requirement that is not specified here. If details are uncertain, label them for review in a small note instead of silently filling them in.

### Layout and style

Use these seven horizontal lanes in this top-to-bottom order:

1. Service Requester
2. Architecture & Design
3. Cloud Platform Engineering
4. Network & Security
5. Infrastructure Operations
6. Monitoring & Backup
7. Service Management

Make the flow readable from left to right within each lane, with clear handovers between lanes. Use rounded rectangles for activities, diamonds for decisions, and distinct Start and End shapes. Colour code native shapes consistently: blue for manual or engineer-led work; green for preferred automated IaC / CI/CD work; purple for approval gates; yellow for decisions; red dashed arrows for rework or exceptions. Place Yes/No labels beside their respective branches. Avoid crossing arrows where practical. Number the process activities **1–33** as below. Use enough canvas space for readable labels; do not shrink the text to force the diagram onto one page.

### Workflow and lane ownership

**Service Requester**
- Start → **1. Server request received**.

**Architecture & Design**
- **2. Build sheet creation**. Capture the server and service requirements, including the VM specification and known network, security, domain, monitoring, and backup needs.
- **3. Build sheet approval**. Approval gate. If incomplete or changes are required, loop back to step 2.
- **4. Subscription requirement assessment**.
- **5. Existing subscription available?** Decision. **Yes → step 7**; **No → step 6**.

**Cloud Platform Engineering**
- **6. Subscription creation**, when required; then proceed to step 7.
- **7. Resource group creation**.
- **8. IP address allocation request**, handed to Network & Security as necessary.

**Network & Security**
- **9. IP allocation approved?** Decision. **Yes → step 10**. **No → revise the request/design and return to step 2 or the appropriate approval step**; label this as rework, not a successful path.
- **10. VNet assessment**.
- **11. Existing VNet suitable?** Decision. **Yes → step 13**; **No → step 12**.
- **12. VNet creation and configuration (IaC / automated)**; then proceed to step 13.
- **13. Firewall request submission**.
- **14. Firewall rules approved?** Decision. **Yes → step 15**; **No → revise firewall rules or requirements and return to step 13**.

**Infrastructure Operations**
- **15. VM specification review**.
- **16. VM build and configuration (CI/CD pipeline, IaC)**.
- **17. Operating system configuration (if required)**.
- **18. Domain join (if applicable)**.
- **19. Group Policy activities**.
- **20. Group Policy changes needed?** Decision. **No → step 21**. **Yes → GPO change request, testing and approval, then return to the Group Policy activities at step 19 and continue to step 21 when complete**. Show the approval clearly; do not create an infinite unlabeled loop.
- **21. Security hardening activities**.

**Monitoring & Backup**
- **22. Site24x7 monitoring agent installation**.
- **23. Backup agent installation / protection enablement**.
- **24. Backup schedule defined**.
- **25. Patching schedule defined**.
- **26. Additional platform agent installations**.

**Service Management**
- **27. Validation checks**.
- **28. IQ (Installation Qualification) testing**.
- **29. IQ testing successful?** Decision. **Yes → step 31**; **No → step 30**.
- **30. Remediation and re-test**; loop back to step 28.
- **31. Service handover**.
- **32. Build documentation completion**.
- **33. Closure** → End.

Connect all consecutive steps unless a decision explicitly branches. Use clear connector anchors so each arrow joins its intended shape. Do not leave unconnected or duplicate activity boxes.

### Side panels

Add a compact legend with the five visual meanings: manual activity, automated IaC / CI/CD activity, approval gate, decision point, and red dashed rework / exception path.

Add a **Key dependencies** panel containing: approved build sheet; approved subscription and resource group; approved IP allocation; VNet and subnet availability; firewall approval; AD, DNS and GPO availability; Recovery Services Vault; monitoring platform access; backup policy availability; platform security baselines.

Add a **Current-standard position** panel: target is IaC-first using approved Terraform modules and CI/CD pipelines; ClickOps is a controlled exception or transition method; backup is enabled after VM creation unless the approved design states otherwise; IQ must pass before handover; document status is Draft v1.0. Include an explicit **review note** that the source diagram's side panel says IP allocation should be requested before build-sheet submission, while its numbered flow places the IP request at step 8. Keep the numbered flow above until an owner resolves this conflict; do not claim both sequences are simultaneously definitive.

Add a **Risks, bottlenecks and automation opportunities** panel, summarised in readable text:
- Risks: incomplete build sheets; manual IP and firewall approvals; late AD, DNS and GPO dependencies; inconsistent manual IQ evidence; delayed documentation and CMDB updates.
- Opportunities: mandatory build-sheet validation; IPAM and firewall workflow integration; policy-as-code and pipeline approval gates; automated agent, backup and patch onboarding; automated IQ evidence; CMDB update and closure enforcement.

Add a **Notes and control principles** panel: keep request, plan, apply, validation, IQ and handover evidence; temporary disks are non-persistent and must not store durable application data; manual portal changes should be captured back into code.

### Source-diagram corrections and quality checks

The source `.drawio` file has one extra disconnected copy of **3. Build sheet approval**. Include only one connected step 3. The source also routes a “No” connector from the subscription assessment box instead of the **Existing subscription available?** decision; connect it from step 5 to step 6. Ensure all approval and rework arrows have valid sources and targets. Inspect the finished XML for duplicate IDs, missing endpoints, clipped text, legible lane labels, and valid Yes/No branches. Give the complete XML document as the output, with no markdown fence around the XML.

---

**Scope note:** This prompt reconstructs the attached draft diagram and flags its internal inconsistency. It does not validate the process against unpublished SOPs, build sheets or platform standards.
