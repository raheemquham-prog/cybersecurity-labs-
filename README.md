# 🛡️ Capstone Project 14: Macro Execution & Physical Social Engineering Simulation

> **An authorized, simulated exercise for studying macro execution, user warning decisions, lab-only callback telemetry, and defensive remediation.**

## 📌 Overview

This capstone models a USB-themed physical social engineering scenario using designated virtual machines, consenting participants, and mock data. Its purpose is to observe security controls and document defensive improvements within an isolated lab. Any references to payloads, lures, or callbacks describe simulation artifacts; they do not authorize deployment outside the approved environment.

## ⚠️ Safety, Authorization & Scope

### Rules of Engagement

Before any run, obtain and record written approval from the lab owner or instructor. The approval must identify the exercise lead, consenting participants, designated VMs and lab addresses, permitted simulation artifacts, test window, allowed observations, and a stop contact. Repository access or possession of an artifact does not constitute permission to execute it. Changes to these boundaries require renewed approval.

The scope is limited to the designated Kali Linux and Windows 11 VMs on the VMware Host-Only network, approved dummy documents or virtual removable media, synthetic accounts, and a lab-local telemetry listener. Physical social engineering is a consent-based role-play in an approved lab space. Do not distribute USB devices, documents, or links to unsuspecting people.

All credentials, computer names, user profiles, and scenario records must be fictitious. Public endpoints, live accounts, production services, real corporate networks, the host operating system, and unrelated devices are out of scope.

### Prohibited Actions and Stop Conditions

- Do not contact external callback services, collect real credentials or personal data, or transfer information outside the lab.
- Do not conduct unauthorized phishing, impersonation, physical access attempts, or real-world media drops.
- Do not use destructive behavior, denial of service, persistence, propagation, lateral movement, or remote command execution. Keep artifacts limited to approved benign simulation signals.
- Do not bypass or weaken host or organizational protections. Any approved comparison of guest control settings must be documented, confined to a disposable VM, and restored afterward.
- Stop immediately if isolation is uncertain, an unexpected destination or device appears, real data is encountered, a participant withdraws consent, or behavior exceeds the approved test plan. Suspend execution, disconnect the affected VM from the lab network, and notify the exercise lead. Resume only after the issue is resolved and approval is reconfirmed.

### Lab Isolation and Pre-Run Checks

VMware Host-Only networking is the required configuration, but it is not sufficient evidence of complete isolation: the host may still be reachable, and additional adapters or forwarding can introduce unintended paths.

Before each run, record that both VMs use only the designated Host-Only network; remove or disconnect NAT, bridged, and other network adapters. Confirm that host routing, Internet Connection Sharing, and forwarding do not provide an external path. Restrict guest access to host services and unrelated host-only guests. Disable shared folders, shared clipboard, drag-and-drop, and unnecessary device passthrough; prefer virtual media over physical USB devices.

Keep the telemetry listener confined to the approved lab interface and approved guests. Verify network settings and isolation without probing public or production destinations. Take clean VM snapshots, confirm that only mock data is present, and record the baseline security settings. If these checks cannot establish the intended boundary, do not run the exercise.

## 🔎 Methodology and Reporting

The following is the required workflow, not a claim that testing or validation has already occurred.

1. **Authorize and prepare.** Record the scope and consent, define the benign expected signal, select defensive controls to observe, and complete the isolation and snapshot checks.
2. **Establish a baseline.** Record guest configuration, macro policy, relevant endpoint protections, and available logs. Define expected outcomes before testing, including when controls should block the simulation.
3. **Conduct the controlled simulation.** Use only approved mock artifacts within the designated guests. Observe the role-play decision, warning or block behavior, and any permitted lab-local telemetry. This methodology does not provide lure construction, warning bypass, or real-target execution instructions.
4. **Collect and interpret evidence.** Correlate guest and listener observations by timestamp. Separate attempted actions, observed execution, blocked actions, and unverified assumptions. A callback alone does not establish privilege, persistence, or access to sensitive data; an absent alert does not prove an absence of detection.
5. **Evaluate defenses.** Document how macro restrictions, document trust controls, removable-media policy, endpoint monitoring, and user reporting affect the scenario. Compare approved lab observations before and after remediation using the same benign test conditions.
6. **Close and restore.** Stop listeners, remove simulation artifacts and virtual media, restore the approved clean guest state, and verify that temporary guest configuration changes are reversed. Record remaining limitations and follow-up recommendations.

For each test, report its identifier, approved asset, objective, baseline, expected result, observed result, evidence references, limitations, and recommended remediation. Mark unperformed tests as planned and unsupported conclusions as unverified. Results apply to the tested lab configuration and must not be presented as proof about real corporate defenses.

## 🗂️ Evidence Handling

Collect only the minimum screenshots, guest event logs, and lab-local telemetry needed to support findings. Use a consistent timestamp format with timezone and assign each evidence item an identifier, source VM, collection time, collector, and related test identifier. Preserve original exports in access-controlled storage; record file hashes to help detect later changes, and use separate redacted copies for the report.

Review every artifact before committing or sharing it. Exclude real credentials, tokens, personal information, host details, and unrelated network traffic; publish only sanitized mock examples. Record who may access evidence, the approved retention period, and the disposal date. If real data appears unexpectedly, stop the exercise, restrict access, and follow the lab owner's handling instructions.

## 🎯 Defensive Learning Outcomes

- Explain how macro policy and document trust controls affect execution and user warnings.
- Recognize suspicious document or removable-media requests and practice a safe reporting response.
- Correlate document activity, endpoint events, and lab-local network telemetry while identifying visibility gaps.
- Assess removable-media restrictions, least privilege, and endpoint monitoring using documented observations.
- Produce a reproducible report that distinguishes evidence from assumptions and recommends measurable defensive improvements.

## 🛠️ Lab Setup & Infrastructure

| Component | Asset / OS | Role in Simulation |
| --- | --- | --- |
| Simulation controller | Kali Linux VM (VMware) | Hosts the approved lab-local telemetry listener and log collection |
| Test workstation | Windows 11 VM (VMware) | Designated guest for observing document controls and benign simulation behavior |
| Network mode | VMware Host-Only | Restricted guest communications, subject to the isolation checks above |
| Simulation artifact | Microsoft Word (`.docm`) / LNK | Approved mock artifact confined to the lab |

## 📂 Repository Layout

The layout below describes the intended project structure; filenames do not establish that artifacts have been reviewed or verified as safe.

```text
.
├── payloads/
│   ├── AutoOpen_macro.vba      # Simulation source; review before any authorized lab run
│   └── usb_launcher.bat        # Simulation script; review before any authorized lab run
├── listeners/
│   └── beacon_listener.py      # Lab-local telemetry listener
├── documentation/
│   └── Technical_Report.md     # Test records, evidence references, and defensive findings
└── README.md                   # Scope, safety requirements, and methodology
```
