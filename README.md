#  Transit Performance Analysis

A logistics analytics project that analyzes shipment transit data to evaluate network efficiency, facility movement, and delivery performance using real-world tracking events.

---

##  Project Overview

This project processes complex, nested shipment tracking data (JSON format) from a courier logistics network and transforms it into structured, analytics-ready datasets.  
The goal is to measure **transit efficiency**, **facility touchpoints**, **delivery attempts**, and **service-level performance** to help courier partners optimize operations.

The solution handles real-world data challenges such as missing fields, inconsistent timestamps, duplicate events, and incomplete shipment journeys.

---

##  Objectives

- Analyze how shipments move across facilities
- Measure total and inter-facility transit time
- Evaluate delivery performance and first-attempt success
- Compare transit efficiency across service types (e.g., express vs standard)
- Generate detailed shipment-level and network-level performance reports

---

##  Data Pipeline & Approach

### 1. Data Ingestion & Exploration
- Load shipment tracking data from JSON
- Explore nested structures and event schemas
- Validate data consistency and completeness

### 2. Data Flattening & Normalization
- Extract shipment identifiers, service details, package info, and locations
- Flatten nested transit events into a structured format
- Normalize timestamps from mixed formats (ISO strings, MongoDB `$numberLong`)

### 3. Transit Performance Metrics
- Total transit time (pickup → delivery)
- Facility touchpoints (unique logistics facilities visited)
- Inter-facility transit duration
- Average hours per facility
- Out-for-delivery attempts and first-attempt delivery flag
- Service classification (express vs standard)

### 4. Edge Case Handling
- Missing or null fields
- Empty or missing event arrays
- Duplicate events at the same timestamp
- Incomplete shipment journeys
- Missing address components

---

## 📊 Outputs

### 1️⃣ Detailed Shipment-Level CSV  
**File:** `transit_performance_detailed.csv`

Contains per-shipment metrics such as:
- Transit time
- Facility count
- Delivery attempts
- Service type
- Velocity metrics

Useful for operational analysis and debugging individual shipments.

---

### 2️⃣ Network Performance Summary CSV  
**File:** `transit_performance_summary.csv`

Contains aggregated KPIs including:
- Average, median, min, max transit hours
- Facility usage statistics
- Service-type comparisons
- First-attempt delivery percentage

Useful for management-level insights and performance benchmarking.

---

##  Tech Stack

- **Python**
- **Pandas & NumPy**
- **JSON Processing**
- **Datetime & Timezone Handling**
- **CSV Analytics Outputs**

---

##  Key Insights Enabled

- Identification of facility congestion and excessive touchpoints
- Transit velocity comparison across service categories
- Delivery reliability and retry analysis
- Data-driven optimization of logistics routes

---

##  How to Run

```bash
# Install dependencies
pip install pandas numpy json datetime
