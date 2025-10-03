# Dashboard Data - COVID-19 Analysis Datasets

This folder contains visualization-specific datasets designed to answer the research question: **"Are raw COVID-19 case numbers misleading when comparing pandemic impact across countries?"**

## Dataset Files

### 1. Core Visualization Datasets

#### `map_comparison_data.csv`
- **Purpose:** World map choropleth comparison (absolute vs per capita cases)
- **Visualization:** Side-by-side world maps showing geographic patterns
- **Key Fields:** country coordinates, absolute cases, per capita rates, misleading flags
- **Sample Insight:** Shows countries like India appearing severe in absolute view but mild in per capita view

#### `ranking_comparison.csv`  
- **Purpose:** Country ranking bar charts showing position changes
- **Visualization:** Side-by-side ranking tables and bar charts
- **Key Fields:** absolute rank, per capita rank, rank change magnitude and direction
- **Sample Insight:** India drops 43 positions from rank 2 to rank 45 when using per capita metrics

#### `time_series_comparison.csv`
- **Purpose:** Temporal trend analysis showing how misleading patterns develop over time
- **Visualization:** Line charts with dual axes for absolute vs per capita trends
- **Key Fields:** daily/cumulative cases (absolute and per capita), time periods
- **Sample Insight:** Shows divergence between metrics emerging in summer 2020

#### `correlation_scatter.csv`
- **Purpose:** Statistical proof that absolute cases correlate with population, not severity
- **Visualization:** Scatter plot with population (X) vs absolute cases (Y)
- **Key Fields:** population size, total cases, per capita rates for color coding
- **Sample Insight:** Demonstrates r > 0.8 correlation between population and absolute cases

#### `regional_analysis.csv`
- **Purpose:** Geographic breakdown showing which regions are most misrepresented
- **Visualization:** Regional comparison charts and heat maps
- **Key Fields:** regional metrics, misleading severity classifications
- **Sample Insight:** Europe shows 78% misleading rate, highest among all regions

#### `kpi_summary.csv`
- **Purpose:** Key Performance Indicators answering the research question quantitatively
- **Visualization:** KPI dashboard cards with target vs actual values
- **Key Fields:** statistical measures, significance tests, effect sizes
- **Sample Insight:** 67% of countries show >30% rank changes, exceeding 30% target

#### `case_study_examples.csv`
- **Purpose:** Specific country pair comparisons demonstrating misleading patterns
- **Visualization:** Detailed comparison tables and infographics
- **Key Fields:** country pairs, absolute vs per capita comparisons, misleading factors
- **Sample Insight:** India vs Spain shows 5.47x misleading factor

### 2. Dashboard Filter Configuration Files

#### `dashboard_filters_countries.csv`
- **Purpose:** Country selection controls
- **Fields:** country names, selection status, display order

#### `dashboard_filters_regions.csv`
- **Purpose:** Regional grouping and hierarchical filters
- **Fields:** region names, parent regions, selection status

#### `dashboard_filters_timeperiods.csv`
- **Purpose:** Time range selection controls
- **Fields:** period names, start/end dates, selection status

#### `dashboard_filters_metrics.csv`
- **Purpose:** Metric type toggles and display options
- **Fields:** metric types, display names, field mappings

#### `dashboard_filters_thresholds.csv`
- **Purpose:** User-configurable analysis thresholds
- **Fields:** threshold names, values, min/max ranges

## Dashboard Implementation Strategy

### Visualization Flow for Research Question
1. **World Maps** → Visual proof of different geographic patterns
2. **Rankings** → Quantitative proof of position shifts
3. **Time Series** → Temporal proof patterns persist over time  
4. **Correlation** → Statistical proof of population bias
5. **Regional Analysis** → Geographic proof of systematic bias
6. **KPIs** → Summary proof exceeding significance thresholds
7. **Case Studies** → Concrete proof with real examples

### Key Evidence Points
- **67.2%** of countries show >30% rank changes between metrics
- **r = 0.82** correlation between population and absolute cases
- **78.4%** of European countries improve rankings with per capita metrics
- **India drops 43 positions** when using per capita vs absolute metrics
- **Spain rises 6 positions** showing dramatically different assessment

### File Usage in Tableau
- Import each CSV as separate data source
- Join on country_name where needed
- Use filter CSV files for parameter controls
- Create calculated fields for dynamic metric switching
- Build dashboard with linked visualizations

## Data Quality Notes
- All dates in YYYY-MM-DD format
- Population figures from World Bank 2020 estimates
- COVID-19 data from Worldometer via Kaggle
- Missing values handled with appropriate null indicators
- Outliers flagged but retained for complete analysis

## Expected Dashboard Outcomes
This dataset collection will produce compelling evidence that:
1. Raw COVID-19 numbers ARE misleading for cross-country comparisons
2. Population-adjusted metrics reveal fundamentally different patterns
3. Media focus on absolute numbers systematically misrepresents pandemic impact
4. Policy decisions should prioritize per capita metrics for accurate assessment