---
name: analyze-opportunity
description: Investigates a land parcel for real estate investment opportunity analysis.
metadata:
  adk_additional_tools:
    - get_lot_data
---
# Analyze Opportunity Skill

When asked to investigate a property or analyze an investment opportunity for a lot:
1. Use the `get_lot_data` tool to lookup the subject property attributes by its lot ID (`plot_id`).
2. Immediately check the `adjacent_parcels` field in the returned data and call `get_lot_data` for **every adjacent/neighboring parcel ID** listed so you have complete data on neighboring properties' flood zones, topography, soil classifications, easements, sale prices, and acreage.
3. **Derive and Highlight Acquisition Cost-Per-Acre (Core Valuation Metric)**:
   - Explicitly calculate the exact mathematical **Acquisition Cost-Per-Acre** using the formula:
     $$\text{Acquisition Cost-Per-Acre} = \frac{\text{Last Sale Price}}{\text{Acreage}}$$
   - State the explicit mathematical formula, the exact inputs (`last_sale_price` and `acreage`), and the exact calculated dollar-per-acre figure (rounded to the nearest cent/dollar, e.g., `$450,000 / 1.2 acres = $375,000.00 per acre`).
   - Emphasize and highlight **Acquisition Cost-Per-Acre** as a **core valuation metric** in both the `Executive Summary` and `Acquisition Basis and Holding Costs` sections (including in markdown summary tables), and **benchmark** it directly against the calculated cost-per-acre of the neighboring/adjacent parcels and the site's zoning density potential.
4. Consult the `analyze-flood-risk` skill to exhaustively investigate the FEMA flood zone classifications and shared hydrological/drainage/runoff risks of both the subject lot and all neighboring/adjacent properties.
5. Consult the `analyze-tax-implications` skill to investigate property tax holding costs (including exact monthly tax carrying cost = annual tax / 12) and assessment records using the lot's `parcel_apn`.
6. Synthesize all findings—including core specifications (`plot_id`, `acreage`, `zoning`), utility access and topography CapEx impacts, Phase I/II ESA environmental due diligence steps, acquisition cost-per-acre benchmarking, and neighboring property flood/hydrological risk analysis—into the final memorandum.
