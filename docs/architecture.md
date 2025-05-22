# Project Architecture Diagram

```
graph TB
    %% External Systems
    NOAA[NOAA API]
    USGS[USGS LiDAR Data]
    OSM[OpenStreetMap]
    
    %% Google Cloud Services
    AgentEngine[Agent Engine]
    BigQuery[BigQuery]
    CloudRun[Cloud Run]
    CloudStorage[Cloud Storage]
    VertexAI[Vertex AI]
    
    %% Multi-Agent System
    DataAgent[Data Management Agent]
    AnalysisAgent[Analysis Agent]
    PresentationAgent[Presentation Agent]
    
    %% Data Processing
    DataIngestion[Data Ingestion]
    DataProcessing[Data Processing]
    RiskAssessment[Risk Assessment]
    Visualization[Visualization]
    
    %% Styling
    classDef external fill:#f9f,stroke:#333,stroke-width:2px,color:#000
    classDef cloud fill:#bbf,stroke:#333,stroke-width:2px,color:#000
    classDef agent fill:#bfb,stroke:#333,stroke-width:2px,color:#000
    classDef process fill:#fbb,stroke:#333,stroke-width:2px,color:#000
    
    %% External to Cloud
    NOAA --> CloudStorage
    USGS --> CloudStorage
    OSM --> CloudStorage
    
    %% Cloud Services
    CloudStorage --> BigQuery
    CloudStorage --> VertexAI
    AgentEngine --> CloudRun
    
    %% Agent System
    CloudRun --> DataAgent
    CloudRun --> AnalysisAgent
    CloudRun --> PresentationAgent
    
    %% Data Flow
    DataAgent --> DataIngestion
    DataIngestion --> DataProcessing
    DataProcessing --> AnalysisAgent
    AnalysisAgent --> RiskAssessment
    RiskAssessment --> PresentationAgent
    PresentationAgent --> Visualization
    
    %% Apply Styles
    class NOAA,USGS,OSM external
    class AgentEngine,BigQuery,CloudRun,CloudStorage,VertexAI cloud
    class DataAgent,AnalysisAgent,PresentationAgent agent
    class DataIngestion,DataProcessing,RiskAssessment,Visualization process
```

## Architecture Components

### External Systems
- **NOAA API**: Source of water level data
- **USGS LiDAR Data**: Source of elevation information
- **OpenStreetMap**: Source of airport infrastructure data

### Google Cloud Services
- **Agent Engine**: Orchestrates multi-agent system
- **BigQuery**: Stores and analyzes data
- **Cloud Run**: Hosts agent containers
- **Cloud Storage**: Stores raw and processed data
- **Vertex AI**: Handles ML model training and deployment

### Multi-Agent System
- **Data Management Agent**: Handles data ingestion and processing
- **Analysis Agent**: Performs risk assessment and modeling
- **Presentation Agent**: Creates visualizations and reports

### Data Flow
- **Data Ingestion**: Collects data from external sources
- **Data Processing**: Cleans and prepares data
- **Risk Assessment**: Analyzes climate impact risks
- **Visualization**: Presents findings to users