# 🛡️ Capstone Project 14: Macro Execution & Physical Social Engineering Simulation


> **Simulation of a physical social engineering attack demonstrating USB drop execution flows, macro warning bypass mechanics, initial access tracking, and defense remediation.**


📌 Overview

This project simulates a USB-based physical social engineering attack conducted within an isolated lab environment. The exercise demonstrates how an attacker with temporary physical access can plant a payload, trick a user into enabling macros, establish an HTTP beacon callback, and track initial access without triggering perimeter defenses.


⚠️ Rules of Engagement (RoE) & Lab Isolation

**Isolated Environment:** Executed strictly within a VMware Host-Only network 
**Zero External Impact:** No public endpoints, live user accounts, or real corporate networks were targeted.
**Mock Data:** All credentials, computer names, and user profiles are dummy data created solely for this lab.



## 🛠️ Lab Setup & Infrastructure

| Component | Asset / OS | Role in Simulation |

| **Attacker Machine** | Kali Linux (VMware) | Hosts Python HTTP beacon listener & log aggregator |
| **Victim Machine** | Windows 11 VM (VMware) | Target environment executing payload |
| **Network Mode** | VMware Host-Only | Isolated internal communications |
| **Delivery Vehicle** | Microsoft Word (`.docm`) / LNK | Macro execution vector & social engineering lure |


## 📂 Repository Layout

```text
.
├── payloads/
│   ├── AutoOpen_macro.vba      # VBA payload source code
│   └── usb_launcher.bat        # Harmless batch beacon script
├── listeners/
│   └── beacon_listener.py      # Python HTTP C2 callback listener
├── documentation/
│   └── Technical_Report.md     # Detailed step-by-step execution flow
└── README.md                   # Project documentation
