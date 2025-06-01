# EigenWatch 🛡️📊📡  
*A Restaking Risk Oracle for Ethereum’s EigenLayer Ecosystem*

---

## Overview

EigenWatch is an open-source risk telemetry and slashing alert system designed for Ethereum’s restaking ecosystem, specifically within the EigenLayer framework.

It provides:
- Validator risk scoring
- Slashing alert feeds
- Validator reputation indexing
- APIs and oracles for consumption by stakers, AVSs, LRTs, and insurance protocols

This project empowers protocols and stakers with real-time insights into operator behavior and systemic risks in the EigenLayer universe.

---

## ✨ Key Features

- 🧠 **Risk Scoring Oracle**: Tracks validator performance across AVSs, uptime, and slashing events.
- 📉 **Slashing Alerts API**: Sends real-time alerts on validator slashing.
- 📊 **Validator Reputation Index**: Combines historical telemetry and correlated exposures.
- 🖥️ **Dashboard Interface**: For protocols, stakers, and researchers to explore risk data.

---

## 🧱 Architecture

+------------------+
| Data Collectors |
| (AVS APIs, EL) |
+--------+---------+
|
v
+--------+---------+
| Analytics Engine|
| (Risk Scoring, |
| Correlation) |
+--------+---------+
|
v
+--------+---------+ +-----------------+
| Oracle Publisher |----->| Onchain Feed |
+--------+---------+ +-----------------+

markdown
Copy
Edit
     |
     v
+-------------------+
| Dashboard / API |
| REST + Webhooks |
+-------------------+

yaml
Copy
Edit

---

## 🛠️ Technologies

- **Languages**: TypeScript, Rust (WASM module), Solidity (Oracle publishing)
- **Backend**: Node.js (Telemetry Fetchers), PostgreSQL (data storage)
- **Frontend**: Next.js, TailwindCSS
- **Smart Contracts**: Solidity / EigenLayer-compatible
- **Oracle Publishing**: Chainlink or EigenLayer-native

---

## 🧪 MVP Scope

- [x] Validator telemetry collectors (off-chain)
- [x] Slashing alert webhook + sample consumers
- [x] Risk scoring script
- [ ] MVP dashboard (Next.js)
- [ ] Oracle publishing contract (testnet)

---

## 📦 Installation

```bash
git clone https://github.com/eigenwatch/eigenwatch.git
cd eigenwatch
yarn install

Would you like this exported as a downloadable `README.md`, added to a GitHub repo, or paired with a proper `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md`?

Run Data Collectors
bash
yarn collectors:start
Run Dashboard (Dev)
bash
Copy

cd packages/dashboard
yarn dev


 API & Oracle Specs
REST API
http
Copy
Edit
GET /api/v1/validators/:address/score
GET /api/v1/alerts/slashing



Webhooks
json
Copy
Edit
{
  "event": "SLASHING",
  "validator": "0xabc...",
  "timestamp": "2025-08-15T13:02:03Z",
  "source": "AVS-X"
}
Onchain Oracle Output
solidity
Copy
Edit
mapping(address => uint256) public riskScore;
📄 License
MIT License © EigenWatch Contributors

👥 Contributing
We welcome contributors from the Ethereum, DeFi, and validator communities! Please see CONTRIBUTING.md to get started.

🌍 Links
Twitter: @eigenwatch

Docs: https://eigenwatch.xyz/docs

Contact: team@eigenwatch.xyz

