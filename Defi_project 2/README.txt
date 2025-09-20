# Blockchain Protocol ABI Contracts Extraction & Events Project

## Overview
This project extracts verified ABIs for blockchain smart contracts across multiple protocols and blockchains (Ethereum, BSC, Avalanche). It includes contract interface decoding for analysis and documentation.

## Pipeline Phases

- **Phase 1:** Data Collection (contract addresses & metadata)
- **Phase 2:** ABI Fetching (batch fetch verified ABIs via Etherscan/BscScan/SnowScan APIs)
- **Phase 3:** ABI Decoding (extract contract events and function signatures)

## Usage

1. Update API keys in `src/batch_abi_fetch.py` or notebook.
2. Run ABI fetching phase to create `data/contracts_with_abis.csv`.
3. Run ABI decoding phase to extract events/functions.
4. Generate the final JSON deliverable using `src/build_final_json.py`.

## Folder Structure

- `src/` - Source code and notebooks
- `data/` - Input and output datasets including extracted JSON
- `README.md` - Project overview and usage
- `requirements.txt` - Python dependencies

## Requirements

- Python 3.x
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

