---
name: analyze-tax-implications
description: Investigates property tax holding costs and assessment records for a parcel.
metadata:
  adk_additional_tools:
    - get_tax_assessment_data
    - get_lot_data
---
# Analyze Tax Implications Skill

When investigating financial carrying costs, acquisition valuation basis, or tax implications for a lot:
1. **Exact Acquisition Cost-Per-Acre Calculation & Benchmarking (Core Valuation Metric)**:
   - Using `last_sale_price` and `acreage` from the lot property records, explicitly derive and state the exact mathematical **Acquisition Cost-Per-Acre**:
     $$\text{Acquisition Cost-Per-Acre} = \frac{\text{Last Sale Price}}{\text{Acreage}}$$
   - Show the full mathematical derivation formula and exact dollar figure (e.g., `$450,000 ÷ 1.2 acres = $375,000.00/acre`).
   - Highlight and emphasize **Acquisition Cost-Per-Acre** as a **core valuation metric** in a structured financial summary table and in the narrative under `Acquisition Basis and Holding Costs` (as well as `Executive Summary`).
   - Benchmark the subject parcel's cost-per-acre against the cost-per-acre of its adjacent parcels (from `adjacent_parcels`) and against its assessed land value per acre (`assessed_land_value / acreage`) to evaluate acquisition price efficiency.
2. **Official Tax Assessment & Monthly Carrying Cost Calculation**:
   - Locate the `parcel_apn` from the lot property records and use `get_tax_assessment_data` to retrieve official county tax assessment details.
   - Explicitly calculate and state the **Monthly Tax Holding Cost** (`Annual Taxes ÷ 12 = $X,XXX.XX/month`) for both the official county annual tax and the estimated annual tax, and analyze its impact on pre-development carrying budgets.
