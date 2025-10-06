# Coupon Acceptance Analysis

## Project Overview

This project analyzes customer behavior regarding coupon acceptance using survey data collected via Amazon Mechanical Turk. The goal is to identify factors that determine whether a driver will accept a coupon for restaurants, bars, coffee houses, or carry-out establishments when delivered to their mobile device.

## Research Question

**Will the Customer Accept the Coupon?**

The analysis focuses on understanding what factors influence drivers' decisions to accept or decline location-based coupons, including:
- User demographics and preferences
- Contextual factors (weather, time, destination)
- Coupon attributes (type, expiration time)

## Dataset

**Source**: UCI Machine Learning Repository
**Collection Method**: Amazon Mechanical Turk survey
**Total Observations**: 12,684
**Features**: 25 attributes covering user demographics, contextual factors, and coupon details

### Data Structure

#### User Attributes
- **Demographics**: Gender, age, marital status, education, occupation, income
- **Lifestyle**: Number of children, frequency of visits to bars, coffee houses, restaurants, carry-out places

#### Contextual Attributes  
- **Driving Context**: Destination (home/work/other), passenger type, weather, temperature, time
- **Location**: Distance to coupon venue, direction relative to destination

#### Coupon Attributes
- **Type**: Bar, Coffee House, Carry-out, Restaurant (<$20), Restaurant ($20-50)
- **Expiration**: 2 hours or 1 day

## Key Findings

### Overall Acceptance Rate
- **57%** of all coupons were accepted

### Bar Coupons Analysis
- **41%** acceptance rate overall
- **Key Factors**:
  - Frequent bar visitors (>3 times/month): **77%** acceptance rate
  - Age >25 + frequent bar visits: **70%** acceptance rate  
  - No kids + non-farming occupation: **71%** acceptance rate

### Coffee House Coupons Analysis
- **50%** acceptance rate overall
- **Key Factors**:
  - Frequent coffee house visitors (>3 times/month): **68%** acceptance rate
  - Drivers under 21: **70%** acceptance rate
  - Passengers: Friends (**60%**) and Partners (**57%**) show higher acceptance

## Data Preprocessing

### Missing Data Handling
- **Dropped**: `car` column (12,576 missing values)
- **Imputed**: Used mode values for missing frequency data:
  - Bar visits: "never"
  - Coffee house visits: "less1" 
  - Carry-out visits: "1~3"
  - Restaurant visits: "1~3" (<$20), "less1" ($20-50)

## Methodology

1. **Data Exploration**: Comprehensive analysis of missing values and data quality
2. **Descriptive Statistics**: Acceptance rate calculations by coupon type
3. **Comparative Analysis**: Segmented analysis based on user attributes
4. **Visualization**: Bar plots and histograms for pattern identification
5. **Hypothesis Formation**: Evidence-based conclusions about acceptance drivers

## Libraries Used

- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computations
- **matplotlib**: Basic plotting
- **seaborn**: Statistical data visualization

## File Structure

```
Pract_App1/
├── pract_app1.ipynb    # Main analysis notebook
├── data/
│   └── coupons.csv     # Source dataset
└── README.md          # This documentation
```

## Key Insights for Business Applications

### Targeting Strategy Recommendations

1. **Bar Coupons**: Target frequent bar visitors, adults over 25, those without children
2. **Coffee House Coupons**: Focus on younger demographics (under 21), frequent coffee drinkers, social groups
3. **Contextual Targeting**: Consider time of day, weather conditions, and passenger composition
4. **Frequency-Based**: Prioritize users with established visit patterns to specific venue types

### Demographic Patterns
- **Age**: Younger drivers more receptive to coffee house coupons, older drivers to bar coupons
- **Social Context**: Presence of friends/partners increases acceptance rates
- **Lifestyle**: Regular visitors to specific venue types show significantly higher acceptance rates