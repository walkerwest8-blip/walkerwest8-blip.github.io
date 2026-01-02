# Project 001 — Cobb County Park Access & Equity

**Status:** Completed (Foundational)  
**Location:** Cobb County, Georgia  
**Tools:** QGIS, US Census ACS (S0101, S1901), Open GIS Data

---

## Project Overview

This project evaluates how public park access varies across census tracts in Cobb County, Georgia when progressively normalized by:

1. land area  
2. population  
3. household income  

Rather than treating park presence as a binary condition, the analysis focuses on **relative access and potential pressure**, producing metrics that better support planning and equity-oriented decision making.

---

## Key Questions

- Which census tracts contain public parks?
- How much park land exists relative to tract size?
- How much park land is available relative to population?
- Which tracts may face higher recreational pressure when income is considered?

---

## Data Sources

- **Cobb County GIS Hub** — Public park property polygons  
- **US Census Bureau**
  - TIGER/Line Census Tracts
  - ACS 5-Year Estimates:
    - S0101 — Total Population
    - S1901 — Median Household Income

Raw geospatial data are excluded from this repository in accordance with best practices.

---

## Methodology

### 1. Data Preparation
- Park geometries were validated and repaired to ensure accurate spatial operations.
- All datasets were projected to **NAD83 / Georgia West (EPSG:2240)** for consistent distance and area calculations.

---

### 2. Park Presence Identification
- Census tracts intersecting park polygons were selected using spatial joins.
- Selected tracts were exported as a standalone analytical dataset.

**Outcome:**  
A working layer of census tracts that contain at least one park.

---

### 3. Land-Based Normalization
- Park areas were calculated in acres.
- Park acreage was aggregated by census tract.
- Tract land area was converted to acres.
- A normalized metric was created:

**`park_pct_of_tract`**  
Percentage of a tract’s land area occupied by park land.

**Purpose:**  
Distinguish between nominal park presence and meaningful spatial coverage.

---

### 4. Population-Based Normalization
- Total population was joined to census tracts using `GEOID`.
- A population-pressure metric was created:

**`park_acres_per_1000`**  
Acres of park land per 1,000 residents.

**Purpose:**  
Account for demand, not just spatial extent.

---

### 5. Income-Adjusted Equity Stress Test
- Median household income was joined at the census tract level.
- A composite metric was calculated:

**`park_access_income_adj`**  
Park acres per 1,000 residents, weighted by median household income.

**Interpretation:**
- Lower values indicate higher potential pressure on parks in lower-income tracts.
- Higher values indicate lower pressure and greater relative access.

This metric is intended as a **screening tool**, not a definitive measure of service quality.

---

## Key Findings

- Park presence alone overstates access in several large census tracts.
- Normalizing by population reveals tracts with high recreational pressure despite having parks.
- Income adjustment highlights tracts where limited park space may disproportionately affect more economically vulnerable populations.
- Some tracts with moderate park acreage still rank low once population and income are considered.

---

## Planning Relevance

This analysis can support:
- Preliminary identification of underserved areas
- Prioritization for park expansion or investment
- Equity-focused planning discussions using defensible metrics

---

## Limitations

- Park quality, amenities, and usability are not considered.
- Accessibility is assumed to be uniform within tracts.
- Cross-tract park usage is not captured.
- Income is treated as a proxy for vulnerability and does not represent individual experience.

Results should be interpreted as **indicators for further investigation**, not final conclusions.

---

## Skills Demonstrated

- GIS data modeling and cleanup
- Spatial joins and aggregation
- Normalization and ratio-based metrics
- ACS Census data integration
- Equity-oriented analytical framing
- Technical documentation

---

## Next Steps

Future work could extend this analysis by:
- Incorporating network-based park accessibility
- Adding age-based or mobility-based vulnerability metrics
- Comparing results across multiple counties
- Evaluating park quality and amenities

---

## Summary

This project demonstrates a complete GIS analysis pipeline—from raw data to equity-informed insight—emphasizing analytical reasoning, defensible methodology, and transparent limitations.
