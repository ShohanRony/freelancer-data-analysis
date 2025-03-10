# Data Dictionary: Freelancer Earnings Dataset

This document provides detailed information about the variables in the freelancer earnings dataset used for this analysis.

## Core Variables

| Variable | Type | Description |
|----------|------|-------------|
| `freelancer_id` | String | Unique identifier for each freelancer |
| `job_category` | Categorical | Primary job category of the freelancer (e.g., Web Development, Content Writing) |
| `platform` | Categorical | Platform where the freelancer operates (e.g., Upwork, Fiverr, Freelancer) |
| `experience_level` | Categorical | Freelancer's experience level (Beginner, Intermediate, Expert) |
| `hourly_rate` | Numeric | Hourly rate charged by the freelancer in USD |
| `monthly_earnings` | Numeric | Average monthly earnings in USD |
| `client_rating` | Numeric | Average client rating (typically on a 1-5 scale) |
| `success_rate` | Numeric | Percentage of successfully completed projects |
| `total_projects` | Integer | Total number of projects completed |
| `rehire_rate` | Numeric | Percentage of clients who rehired the freelancer |

## Client-Related Variables

| Variable | Type | Description |
|----------|------|-------------|
| `client_region` | Categorical | Primary geographic region of clients (e.g., North America, Europe, Asia) |
| `payment_method` | Categorical | Preferred payment method (e.g., Direct, PayPal, Bank Transfer) |
| `client_industry` | Categorical | Primary industry of clients (e.g., Technology, Healthcare, Education) |
| `avg_response_time` | Numeric | Average time to respond to client inquiries in hours |
| `client_satisfaction` | Numeric | Client satisfaction score (typically on a 1-100 scale) |

## Project-Related Variables

| Variable | Type | Description |
|----------|------|-------------|
| `project_type` | Categorical | Type of project pricing (Fixed, Hourly) |
| `avg_project_length` | Numeric | Average length of projects in days |
| `completion_time_ratio` | Numeric | Ratio of actual to estimated completion time |
| `revision_requests` | Numeric | Average number of revision requests per project |
| `on_time_delivery` | Numeric | Percentage of projects delivered on time |
| `avg_project_size` | Numeric | Average project size/value in USD |

## Marketing and Business Variables

| Variable | Type | Description |
|----------|------|-------------|
| `marketing_spend` | Numeric | Monthly amount spent on marketing in USD |
| `profile_completeness` | Numeric | Percentage of profile completeness on platform |
| `portfolio_size` | Integer | Number of portfolio items or samples |
| `years_active` | Numeric | Number of years active as a freelancer |
| `skill_endorsements` | Integer | Number of skill endorsements received |
| `certifications` | Integer | Number of relevant certifications |
| `profile_views` | Integer | Average monthly profile views |
| `conversion_rate` | Numeric | Percentage of profile views that convert to inquiries |

## Derived Variables

| Variable | Type | Description |
|----------|------|-------------|
| `earnings_per_project` | Numeric | Average earnings per project (monthly_earnings / total_projects) |
| `marketing_roi` | Numeric | Return on marketing investment (earnings attributed to marketing / marketing_spend) |
| `efficiency_score` | Numeric | Composite score based on delivery time, revision requests, and client satisfaction |
| `growth_rate` | Numeric | Year-over-year growth rate in earnings |
| `market_penetration` | Numeric | Estimated market share within specific niche |

## Data Preprocessing Notes

- Missing values in `hourly_rate` were imputed using the median rate for the same job category and experience level
- Outliers in `monthly_earnings` (beyond 3 standard deviations) were capped
- Categorical variables were encoded using one-hot encoding for modeling purposes
- Numeric variables were standardized (z-score normalization) for certain analyses
- Time-based variables were converted to a consistent unit (hours or days)

## Data Quality Considerations

- Self-reported earnings data may contain reporting biases
- Platform differences in rating systems were normalized to a consistent scale
- Regional differences in currency values were converted to USD using average exchange rates
- Seasonal variations in freelance work were accounted for by using annual averages where appropriate