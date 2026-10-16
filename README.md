# India-Stocks-1021-1050-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1021 to 1050)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1021-1050-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1021 to 1050)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1021 | `EIHAHOTELS` | EIH Associated Hotels Limited | `EIHAHOTELS.NS` |
| 1022 | `EIMCOELECO` | Eimco Elecon (India) Limited | `EIMCOELECO.NS` |
| 1023 | `EKC` | Everest Kanto Cylinder Limited | `EKC.NS` |
| 1024 | `EKI` | EKI Energy Services Limited | `EKI.NS` |
| 1025 | `ELANTAS` | Elantas Beck India Limited | `ELANTAS.NS` |
| 1026 | `ELCIDIN` | EL CID Investments Limited | `ELCIDIN.NS` |
| 1027 | `ELDEHSG` | Eldeco Housing And Industries Limited | `ELDEHSG.NS` |
| 1028 | `ELECTCAST` | Electrosteel Castings Limited | `ELECTCAST.NS` |
| 1029 | `ELECTHERM` | Electrotherm (India) Limited | `ELECTHERM.NS` |
| 1030 | `ELEVATE` | Elevate Campuses Limited | `ELEVATE.NS` |
| 1031 | `ELGIRUBCO` | Elgi Rubber Company Limited | `ELGIRUBCO.NS` |
| 1032 | `ELIN` | Elin Electronics Limited | `ELIN.NS` |
| 1033 | `ELITECON` | Elitecon International Limited | `ELITECON.NS` |
| 1034 | `ELLEN` | Ellenbarrie Industrial Gases Limited | `ELLEN.NS` |
| 1035 | `ELPROINTL` | Elpro International Limited | `ELPROINTL.NS` |
| 1036 | `EMAMIPAP` | Emami Paper Mills Limited | `EMAMIPAP.NS` |
| 1037 | `EMAMIREAL` | Emami Realty Limited | `EMAMIREAL.NS` |
| 1038 | `EMBDL` | Embassy Developments Limited | `EMBDL.NS` |
| 1039 | `EMIL` | Electronics Mart India Limited | `EMIL.NS` |
| 1040 | `EMKAY` | Emkay Global Financial Services Limited | `EMKAY.NS` |
| 1041 | `EMMBI` | Emmbi Industries Limited | `EMMBI.NS` |
| 1042 | `EMPIND` | Empire Industries Limited | `EMPIND.NS` |
| 1043 | `EMPOWER` | Empower India Limited | `EMPOWER.NS` |
| 1044 | `EMSLIMITED` | EMS Limited | `EMSLIMITED.NS` |
| 1045 | `EMUDHRA` | eMudhra Limited | `EMUDHRA.NS` |
| 1046 | `ENERGYDEV` | Energy Development Company Limited | `ENERGYDEV.NS` |
| 1047 | `ENIL` | Entertainment Network (India) Limited | `ENIL.NS` |
| 1048 | `ENKEIWHEL` | Enkei Wheels (India) Limited | `ENKEIWHEL.NS` |
| 1049 | `ENTERO` | Entero Healthcare Solutions Limited | `ENTERO.NS` |
| 1050 | `EPACK` | EPACK Durable Limited | `EPACK.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream EIHAHOTELS 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1021-1050-Historical-Data/main/EIHAHOTELS/1m/2026/10/EIHAHOTELS_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
