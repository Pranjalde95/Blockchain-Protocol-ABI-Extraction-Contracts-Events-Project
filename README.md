# Blockchain Protocol ABI Contracts Extraction & Events Project

## Overview
This project builds a dataset linking DeFi protocols → smart contracts → verified ABIs → decoded functions/events across multiple EVM chains. It also enriches each address with a contract_name field for the final JSON deliverable.

## Pipeline Phases

- Phase 1 — Data Collection
Extract contract addresses & minimal metadata.
Output: data/defillama_extracted_contracts.csv

- Phase 2 — ABI Fetching
Batch-fetch verified ABIs via Etherscan-family explorer APIs (Etherscan, BscScan, SnowTrace, Polygonscan, Arbiscan, Optimistic Etherscan).
Output: data/contracts_with_abis.csv

- Phase 3 — ABI Decoding
Parse ABIs to extract functions and events for analysis.
Output: data/contracts_events_and_functions.csv

- Phase 4 — Final JSON Build (+ Name Enrichment)
Produce final JSON with protocol, address, contract_name, abi.
Output: data/all_protocols_contracts_with_abis_named.json

## Usage

1. Update API keys in `src/batch_abi_fetch.py` or notebook.
2. Run ABI fetching phase to create `data/contracts_with_abis.csv`.
3. Run ABI decoding phase to extract events/functions.
4. Generate the final JSON deliverable using `src/build_final_json.py`.

## Folder Structure
Blockchain-Protocol-ABI-Extraction-Contracts-Events-Project/
├── data/
│   ├── protocols.csv
│   ├── defillama_extracted_contracts.csv
│   ├── contracts_with_abis.csv
│   ├── contracts_events_and_functions.csv
│   ├── all_protocols_contracts_with_abis.json
│   └── all_protocols_contracts_with_abis_named.json
│
├── reports/
│   └── DeFi_Contracts_ABI_Report_Full.pdf
│
├── notebooks(Pipeline)/
│   └── Defi_.ipynb
│
├── requirements.txt
└── README.md

## Requirements
- Python
- pandas
- requests


## Running

- pip install -r requirements.txt
- python src/batch_abi_fetch.py
- python src/parse_abi_phase3.py
- python src/build_final_json.py


## Notes
- Contracts without verified ABIs are included with empty ABI fields.
- API token limits apply; careful with rate limiting.

---

