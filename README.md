\# ZWaveForge Pro (v1.0.0)  
\> \*\*Enterprise Z-Wave Plus v2 & Z-Wave Long Range (ZWLR) Protocol Engineering Studio, S2 Security Encapsulation Engine, DSK Key Derivator & 10-Point Normative Zero-Trust Compliance Auditor\*\*

\[\!\[Z-Wave Standard\](https\://img.shields.io/badge/Z--Wave%20Alliance-Z--Wave%20Plus%20v2%20%7C%20ZWLR-00E5FF.svg)\](\#)  
\[\!\[Security 2\](https\://img.shields.io/badge/Security-S2%20AES--128--CCM-7C4DFF.svg)\](\#)  
\[\!\[Audit Score\](https\://img.shields.io/badge/Normative%20Audit-10%2F10%20PASS-00E676.svg)\](\#)  
\[\!\[Zero Dependency\](https\://img.shields.io/badge/CLI-Python%203.8%2B-FF9100.svg)\](\#)

\---

\#\# Overview  
\*\*ZWaveForge Pro\*\* is an enterprise developer tool designed for firmware engineers, IoT hardware manufacturers, and smart home product builders developing devices for \*\*Z-Wave Plus v2\*\*, \*\*Z-Wave Long Range (ZWLR)\*\*, and \*\*Z-Wave Security 2 (S2)\*\*.

It eliminates costly certification test failures and expensive proprietary test sets by delivering a zero-dependency web studio, a bit-accurate S2 security encapsulation encoder/dissector, a Device Specific Key (DSK) PIN derivation tool, and an automated 10-point normative compliance audit engine.

\#\#\# Core Capabilities  
1\. \*\*Interactive Web Studio\*\*: Real-time Z-Wave Command Class frame builder, S2 security level selector (Access Control, Authenticated, Unauthenticated, None), and byte-level dissection.  
2\. \*\*Security 2 (S2) Encapsulation Engine\*\*: Implements AES-128-CCM encryption, 8-byte authentication MAC tags, sequence numbering, and security class key separation.  
3\. \*\*Device Specific Key (DSK) & SmartStart\*\*: Validates 16-byte DSK strings and computes the standard 5-digit decimal SmartStart QR pairing PIN.  
4\. \*\*10-Point Normative Zero-Trust Auditor\*\*: Validates S2 security class allocation, 128-bit DSK entropy, Node ID addressing bounds (Classic 1–232 vs ZWLR 1–4,000), mandatory Z-Wave Plus v2 CCs (0x5E, 0x86, 0x9F), SPAN nonce freshness, and Lifeline Group 1 mappings.  
5\. \*\*Standalone Python CLI\*\*: Zero-dependency command-line utility for automated CI/CD pipelines, regression testing, and build scripts.  
6\. \*\*Embedded C SDK Exporter\*\*: Generates production C data structures for Silicon Labs Z-Wave 800 Series GSDK and Z-Wave JS.

\---

\#\# Directory Structure  
\`\`\`  
product\_297/  
├── README.md                                  \# Complete product guide and quick start  
├── source-code/  
│   ├── index.html                             \# Multi-tab responsive web studio  
│   ├── zwave.css                              \# Modern cybersecurity dark theme  
│   ├── zwave-engine.js                        \# Core Z-Wave & S2 security codec engine  
│   ├── zwave-auditor.js                       \# 10-point normative compliance rules  
│   └── app.js                                 \# Interactive Studio controller  
├── build/  
│   ├── zwave-cli.py                           \# Zero-dependency Python 3 CI/CD CLI runner  
│   └── zwaveforge-pro-v1.0.0.zip              \# Packaged distribution archive  
├── documentation/  
│   ├── ARCHITECTURE.md                        \# Protocol stack and S2 framing spec  
│   ├── USER\_GUIDE.md                          \# Studio and CLI user guide  
│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Pricing, GTM, and market strategy  
├── screenshots/  
│   └── zwave-studio-preview.svg               \# Vector architecture & UI mock  
└── test\_zwave.py                              \# Automated 10-point unit verification suite  
\`\`\`

\---

\#\# Automated Verification & Test Coverage  
ZWaveForge Pro is validated against a 10-test automated verification suite (\`test\_zwave.py\`):  
\- \[x\] S2 Authenticated binary switch frame synthesis  
\- \[x\] Plaintext command frame synthesis (No Security)  
\- \[x\] S2 encapsulated frame byte-level dissection  
\- \[x\] 10-point normative compliance audit on standard profiles (10/10 PASS)  
\- \[x\] Rejection of weak DSK entropy (\< 128 bits)  
\- \[x\] Rejection of profiles missing mandatory Z-Wave Plus v2 CCs (5E, 86, 9F)  
\- \[x\] Enforcement of classic mesh Node ID bounds (1 to 232\)  
\- \[x\] Support for Z-Wave Long Range (ZWLR) Node ID addressing up to 4,000  
\- \[x\] Support across all S2 security classes (Access Control, Authenticated, Unauthenticated)  
\- \[x\] End-to-end smart lock S2 Access Control command and audit workflow verification

\---

\#\# Quick Start  
\`\`\`bash  
\# Synthesize S2 Authenticated Binary Switch ON command  
python3 build/zwave-cli.py cmd \--cc 0x25 \--cmd 0x01 \--param FF \--sec S2\_AUTHENTICATED

\# Synthesize S2 Access Control Door Lock command  
python3 build/zwave-cli.py cmd \--cc 0x62 \--cmd 0x01 \--param FF \--sec S2\_ACCESS\_CONTROL

\# Dissect raw Z-Wave hex stream  
python3 build/zwave-cli.py dissect \--hex 9f011a0210e7197a1f4b09c255e092

\# Run 10-point normative compliance audit  
python3 build/zwave-cli.py audit  
\`\`\`  
