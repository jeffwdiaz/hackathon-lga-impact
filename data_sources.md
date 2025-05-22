# Data Sources for LaGuardia Airport Climate Impact Analysis

## Primary Data Categories

### 1. Water Level Data (Primary Focus)
* **NOAA (National Oceanic and Atmospheric Administration)**
    * Historical tide gauge data for New York Harbor
    * Sea-level rise projections
    * Data format: CSV/JSON
    * Update frequency: Daily
    * API access: REST

### 2. Topographical Data (Primary Focus)
* **USGS (U.S. Geological Survey)**
    * LiDAR data for elevation information
    * Data format: LAS/LAZ
    * Update frequency: Annual
    * Access: Direct download

### 3. Airport Infrastructure Data (Primary Focus)
* **OpenStreetMap**
    * Basic airport layout information
    * Runway and terminal outlines
    * Data format: OSM XML
    * Update frequency: Continuous
    * API access: REST

## Secondary Data Categories (If Time Permits)

### 4. Land Subsidence Data
* **USGS (U.S. Geological Survey)**
    * Land subsidence studies
    * Research papers and datasets
    * Data format: Various
    * Update frequency: Irregular
    * Access: Research portal

### 5. Weather Data
* **NOAA National Climatic Data Center (NCDC)**
    * Historical weather records
    * Rainfall and temperature data
    * Data format: CSV
    * Update frequency: Daily
    * API access: REST

## Data Integration Strategy

### Phase 1: Core Data Integration
1. **Water Levels**
    * Primary source: NOAA
    * Focus on historical data and basic projections
    * Simple REST API integration

2. **Topography/Elevation**
    * USGS National Map
    * Basic LiDAR processing
    * Elevation model generation

3. **Airport Infrastructure**
    * OpenStreetMap data
    * Basic feature extraction
    * Infrastructure mapping

### Phase 2: Enhanced Data Integration (If Time Permits)
1. **Land Subsidence**
    * USGS research data
    * Basic subsidence analysis
    * Integration with elevation data

2. **Weather Information**
    * NOAA NCDC
    * Historical weather patterns
    * Correlation with flooding events

## Data Processing Pipeline

### 1. Data Ingestion
* Automated API calls to NOAA
* Scheduled LiDAR data downloads
* OpenStreetMap data updates

### 2. Data Processing
* Water level data normalization
* LiDAR data processing
* Infrastructure data cleaning

### 3. Data Storage
* BigQuery for structured data
* Cloud Storage for raw data
* Processed data management

### 4. Data Quality
* Automated validation checks
* Data completeness verification
* Error handling and logging

## Integration Considerations
* Focus on reliable, accessible data sources
* Prioritize data quality over quantity
* Maintain clear documentation of data processing
* Implement robust error handling
* Ensure data consistency across sources