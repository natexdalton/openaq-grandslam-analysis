# Grand Slam Tennis Air Quality Analysis

An analysis of air quality patterns at the four Grand Slam tennis tournament locations using the OpenAQ API to compare pollution levels and investigate the impact of court surface types.

## Overview

This project analyzes real-world air quality data from the locations of the four major Grand Slam tennis tournaments to answer two key questions:

1. **Which Grand Slam tournament location experiences the best and worst air quality overall?**
   - US Open (New York, USA)
   - French Open (Paris, France)
   - Australian Open (Melbourne, Australia)
   - Wimbledon (London, UK)

2. **Does court surface type affect air quality levels?**
   - Hard courts (US Open, Australian Open)
   - Clay courts (French Open)
   - Grass courts (Wimbledon)

## Data Source

- **API**: [OpenAQ API v3](https://docs.openaq.org/)
- **Endpoints Used**:
  - Locations Query: `https://api.openaq.org/v3/locations`
  - Pollutant Information: `https://api.openaq.org/v3/parameters`
  - Monthly Average: `https://api.openaq.org/v3/sensors/{sensor_id}/days/monthly`

## Key Features

- Automated data collection from air quality sensors near each Grand Slam venue
- Time-series analysis of pollutant levels during tournament periods
- Comparative analysis across different geographic locations and court types
- Data visualization using matplotlib and seaborn
- Analysis of multiple air quality metrics including PM2.5, PM10, CO, NO2, and O3

## Installation

### Prerequisites

- Python 3.7+
- Jupyter Notebook or JupyterLab
- OpenAQ API key (free registration at [OpenAQ](https://openaq.org/))

### Required Libraries

```bash
pip install -r requirements.txt
```

Or install individually:

```bash
pip install openaq pandas numpy matplotlib seaborn requests
```

### Setup

1. Clone this repository:
```bash
git clone https://github.com/yourusername/grandslam-air-quality.git
cd grandslam-air-quality
```

2. Set up your OpenAQ API key as an environment variable:
```bash
export OPENAQ_API_KEY='your_api_key_here'
```

For Windows:
```bash
set OPENAQ_API_KEY=your_api_key_here
```

3. Open the Jupyter notebook:
```bash
jupyter notebook OpenAQ_GrandSlam.ipynb
```

## Project Structure

```
grandslam-air-quality/
│
├── OpenAQ_GrandSlam.ipynb    # Main analysis notebook
├── README.md                  # This file
├── requirements.txt           # Python dependencies
├── .gitignore                # Git ignore rules
├── LICENSE                   # MIT License
└── .env.example              # Example environment variables file
```

## Usage

The notebook is organized into four main steps:

### Step 1: Setup
Import required libraries and configure API access.

### Step 2: Define Event Data
Create dictionaries with tournament information including:
- Event name and location
- Coordinates for sensor queries
- Tournament dates and time windows
- Court surface type

### Step 3: Data Collection Functions
Functions to:
- Query nearby air quality sensors
- Fetch historical pollutant data
- Aggregate and process measurements
- Handle API rate limits and errors

### Step 4: Analysis & Visualization
Execute queries, generate dataframes, and create visualizations comparing:
- Air quality across all four Grand Slam locations
- Pollution patterns by court surface type
- Temporal trends during tournament periods

Simply run all cells sequentially to reproduce the analysis.

## Methodology

### Data Collection
- Sensors within a specified radius of each tournament venue are identified
- Air quality data is collected for periods surrounding each tournament
- Multiple pollutants are tracked to provide comprehensive air quality assessment

### Analysis Approach
- Statistical comparison of pollutant levels across locations
- Grouping by court surface type to identify patterns
- Visualization of trends and distributions
- Consideration of geographic and seasonal factors

## Key Findings

The analysis reveals:
- Comparative air quality rankings for the four Grand Slam locations
- Relationships between court surface types and local air quality
- Temporal patterns in pollution levels during tournament periods

*(Detailed findings and visualizations are available in the notebook)*

## Technologies Used

- **Python**: Core programming language
- **Jupyter Notebook**: Interactive development environment
- **pandas**: Data manipulation and analysis
- **OpenAQ API**: Air quality data retrieval
- **matplotlib & seaborn**: Data visualization
- **numpy**: Numerical computations

## Data Notes

- Australian Open data was collected from 2023 due to incomplete sensor data availability for 2025
- All timestamps are in UTC
- Missing data points are handled appropriately in the analysis
- Sensor locations and availability may vary by region

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## Future Enhancements

Potential areas for expansion:
- Include additional tennis tournaments (ATP/WTA events)
- Analyze weather data alongside air quality
- Compare indoor vs. outdoor venue air quality
- Extend analysis to multi-year trends
- Investigate correlation with player performance metrics

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [OpenAQ](https://openaq.org/) for providing free, open air quality data
- Grand Slam tournament organizations for inspiring this analysis
- The open-source Python data science community

## Contact

For questions or feedback, please open an issue in this repository.

---

**Author**: Your Name  
**Project Type**: Data Analysis / Environmental Science  
**Status**: Complete
