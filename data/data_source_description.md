# Dataset Overview: Cement Sales & Demand Benchmark

- **Source Name:** Kaggle "Cement Sales & Demand Dataset"
- **Author:** Kishor Khengare
- **Direct Kaggle URL:** [https://www.kaggle.com/datasets/kishorkhengare/cement-sales-demand](https://www.kaggle.com/datasets/kishorkhengare/cement-sales-demand)
- **Time Coverage:** January 2010 – November 2022 (150+ monthly transactional records)
- **License:** Open Database License (ODbL) / Permitted for educational use
- **Privacy:** 100% anonymized, zero personally identifiable information (PII)

### Core Features & Columns
1. `Month`: Monthly chronological series.
2. `Production`: Tonnage of cement produced per cycle.
3. `Demand`: Aggregate market demand and incoming retail order requests.
4. `Sales`: Total volume sold.
5. `Disbursement`: Housing & construction loans disbursed (underlying driver of cement consumption).
6. `Interest Rate`: Commercial bank lending rates influencing builder activity.

### Calibration to Rwandan Dealership Context
We utilize the empirical distribution ratios (production-to-demand-to-sales) from this benchmark dataset to seed our normalized dealership transactional tables:
- Standard Retail Unit: 50 kg Bag (CIMERWA 32.5R / 42.5N)
- Official Retail Benchmark Price: 8,500 RWF per bag
- Warehouse Truck Batches: 200–500 bags per dispatch order
- Simulation of Transit Shortages: Systematic injection of 5%–10% driver siphoning variances to test and validate `trg_check_transit_theft` and `pkg_cimerwa_reconciliation`.
