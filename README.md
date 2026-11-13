# Terra Shift

**Terra Shift** is a machine learning project focused on understanding and predicting urban growth across US metropolitan areas.

The project uses historical demographic, employment, housing, and geographical data to study how metropolitan areas change over time and explore their potential growth over the next five years.

The goal is to build a reliable dataset, analyse different machine learning algorithms, and identify which models can provide useful predictions for urban planning.

## Project Objectives

- Analyse historical urban growth across US metropolitan areas.
- Study population, employment, housing, and geographical changes.
- Build a structured dataset using multiple public data sources.
- Compare different machine learning algorithms.
- Predict potential metropolitan growth over a five-year period.
- Visualise geographical patterns and model predictions.

## Data Sources

### 1. US Census Bureau – American Community Survey (ACS)

The primary data source is the **American Community Survey (ACS) 5-Year Estimates**, accessed through the US Census Bureau API.

API endpoint:

`https://api.census.gov/data/{year}/acs/acs5`

We are collecting data from three historical releases:

| Release | Survey period |
|---|---|
| 2014 | 2010–2014 |
| 2019 | 2015–2019 |
| 2024 | 2020–2024 |

Currently, the project is working with the 2024 dataset.

**Important API variables:**

| Variable | Description |
|---|---|
| `B01003_001E` | Total population |
| `B01003_001M` | Population margin of error |
| `B23025_004E` | Civilian employed population |
| `B23025_004M` | Employment margin of error |
| `B25001_001E` | Total housing units |
| `B25001_001M` | Housing margin of error |

The API also provides metropolitan area names and geographical identifiers.

### 2. Geographical Data

Additional geographical datasets are planned to provide:

- Metropolitan land area.
- Water area.
- Road network length.
- Geographical boundaries.

Planned sources include US Census TIGER/Line geographical data and Census metropolitan statistical area boundaries.

## Technology Stack

- **Language:** Python 3.12.3
- **Environment:** Python Virtual Environment
- **Data Processing:** Pandas, NumPy
- **Visualisation:** Matplotlib, Seaborn
- **Data Collection:** Requests
- **Environment Variables:** python-dotenv
- **Development Workspace:** Jupyter Notebook
- **Machine Learning:** Scikit-learn (planned)

## Project Structure

```text
terra-shift/
│
├── data/
│   ├── raw/
│   │   └── Original API responses and downloaded datasets
│   │
│   ├── processed/
│   │   └── Cleaned and transformed datasets
│   │
│   └── final/
│       └── Validated datasets ready for analysis and modelling
│
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_geographical_data.ipynb
│   ├── 04_dataset_analysis.ipynb
│   └── 05_model_training.ipynb
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Zayed-Ahmed-dev/terra-shift.git

cd terra-shift
```

### 2. Create a Virtual Environment

The project uses Python 3.12.3.

```bash
python3.12 -m venv .venv
```

Activate the environment:

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install --upgrade pip

pip install -r requirements.txt
```

### 4. Configure the Census API

Create a `.env` file in the project root:

```env
CENSUS_API_KEY=your_census_api_key
```

Replace the placeholder with your actual US Census API key.

API keys can be requested from the [US Census Bureau Developer Portal](https://api.census.gov/data/key_signup.html).

**Never commit your `.env` file or expose your API key publicly.**

### 5. Start Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks directory and execute the notebooks in sequence.

## Data Processing Workflow

Terra Shift follows a structured data pipeline:

1. **Data Collection:** Retrieve original datasets from the Census API and other geographical sources.
2. **Data Cleaning:** Handle missing values, inconsistent records, and duplicate entries.
3. **Geographical Processing:** Match metropolitan areas with geographical boundaries and road network information.
4. **Dataset Analysis:** Explore distributions, correlations, missing values, and historical changes.
5. **Model Training:** Train and compare different machine learning algorithms.

### Data Cleaning Workflow

Before using the collected data for analysis and modelling, it goes through a cleaning and validation process.

The following diagram illustrates how the raw Census data is processed, how inconsistencies and unusual records are examined, and how the cleaned dataset is prepared for further analysis.

![Terra Shift Data Cleaning Workflow](<Terra Shift_ Clean Data Workflow.png>)

## Current Development Status

- [x] Initial project structure
- [x] Python virtual environment
- [x] Census API integration
- [x] Initial 2024 ACS metropolitan dataset collection
- [x] Initial raw and processed data organisation
- [ ] Historical 2014 and 2019 data collection
- [ ] Geographical data integration
- [ ] Dataset validation and feature engineering
- [ ] Exploratory data analysis
- [ ] Machine learning model comparison
- [ ] Five-year growth prediction

## Future Scope

The project aims to develop a model capable of analysing historical metropolitan growth patterns and estimating future changes in population, employment, housing, and urban development.

The final objective is to create a data-driven foundation that can support better urban planning and geographical decision-making.

## License

License to be decided.
