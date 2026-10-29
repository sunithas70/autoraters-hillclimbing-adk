---
name: analyze-flood-risk
description: Investigates flood zone designations and environmental risks for real estate investment opportunity analysis.
metadata:
  adk_additional_tools:
    - get_lot_data
---
# Analyze Flood Risk Skill

When evaluating flood, hydrological, environmental, or geographic risks for a subject lot:
1. **Subject Parcel Flood & Physical Profile**:
   - Check the `flood_zone`, `topography`, `soil_classification`, `easement_type`, and `environmental_status` fields from the subject property's `get_lot_data` record.
   - Explicitly flag the exact FEMA flood zone classification (e.g., `Zone AE (High Risk)`, `Zone VE (Coastal High Hazard)`, `Zone X (Minimal Risk)`) and detail specific vertical construction requirements (Base Flood Elevation / BFE compliance, engineered fill dirt, deep pilings/piers, breakaway walls, podium parking, retaining walls) and mandatory NFIP/private flood insurance cost impacts.
2. **Mandatory Neighboring / Adjacent Property Flood Risk Investigation**:
   - Inspect the `adjacent_parcels` array in the subject parcel's data.
   - **You MUST call `get_lot_data` for EVERY parcel ID listed in `adjacent_parcels`** (if not already retrieved) to obtain the exact `flood_zone`, `topography`, `soil_classification`, and `easement_type` of all neighboring properties.
3. **Exhaustive Neighboring Hydrological, Drainage, and Runoff Analysis**:
   - In the `Risk Assessment` section (and highlighted in the `Executive Summary`), present a dedicated comparative table and in-depth engineering analysis of the **neighboring/adjacent properties' FEMA flood zone designations and hydrological conditions**:
     - Explicitly state the Lot ID, exact FEMA `flood_zone` designation, `topography` (grade/slope), `soil_classification`, and `easement_type` for each adjacent property alongside the subject parcel.
     - **Drainage & Surface Runoff Interaction**: Critically analyze how the relative topography/grade slopes and soil classifications (e.g., clay loam with shrink-swell/low permeability vs. sandy loam vs. urban land) between the neighboring parcels and the subject parcel drive cross-boundary stormwater runoff, sheet flow, erosion, or water pooling onto or off of the subject lot.
     - **Floodplain Connectivity & Hydrological Encroachment**: Evaluate how adjacent high-hazard flood zones (such as neighboring `Zone AE` or `Zone VE` parcels) create shared floodplain boundary risks, tailwater/backwater effects, coastal storm surge propagation, or groundwater table elevation impacts—even if the subject parcel itself is in `Zone X (Minimal Risk)`, or how adjacent `Zone X` upland runoff drains into a `Zone AE`/`Zone VE` subject parcel.
     - **Development Feasibility & Mitigation Engineering**: Prescribe concrete civil and hydrological engineering measures required to mitigate shared neighboring hydrological impacts (e.g., perimeter swales, retaining walls with French drains, oversized on-site stormwater detention/retention basins, reciprocal drainage easements, grading/fill displacement restrictions, and joint hydrological modeling during due diligence).
