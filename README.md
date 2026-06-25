# KPI Experiment Analysis: Onboarding Campaign Evaluation

## Business Context

A subscription-based digital product company launched a new onboarding and activation campaign to improve user conversion and early engagement.

Users were randomly assigned to one of two groups:

* **Control Group:** Existing onboarding experience
* **Treatment Group:** New onboarding campaign experience

The objective of this experiment was to determine whether the Treatment experience should be launched to all users based on its impact on conversion, engagement, and revenue-related metrics.

---

## Business Problem Statement

Leadership must decide whether the new onboarding campaign should be rolled out to all users.

The decision impacts:

* Product Teams
* Marketing Teams
* Revenue Growth
* Customer Experience

The primary objective is to improve user conversion while ensuring that customer satisfaction and revenue quality are not negatively impacted.

Before making a rollout decision, statistical evidence and guardrail metric analysis are required.

---

## Dataset Description

The dataset contains user-level experiment data including:

* Experiment Group
* User ID
* Landing Page Visits
* Trial Starts
* Onboarding Completion
* Paid Conversion Status
* Revenue
* Refund Requests
* Support Tickets
* Engagement Score
* Days to Convert
* Region
* Device Type
* Traffic Source
* Plan Type

### Total Users Analyzed: 1,408

| Group     | Users |
| --------- | ----: |
| Control   |   693 |
| Treatment |   715 |

---

## North Star Metric

### Paid Conversion Rate

#### Definition

> Paid Conversion Rate = Users Converted to Paid ÷ Total Users

#### Why This Metric Was Selected

* Directly measures onboarding success.
* Closely tied to business growth and revenue generation.
* Represents the final objective of the user activation funnel.
* Provides a clear decision-making metric for launch evaluation.

#### Supporting Metrics

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate
* Revenue Per User
* Engagement Score

#### Risks of Optimizing This Metric Alone

* Increased refund requests
* Increased support tickets
* Lower revenue quality
* Potential negative customer experience

Therefore, guardrail metrics were also evaluated.

---

## KPI Tree Summary

The KPI framework was built around **Paid Conversion Rate** as the North Star Metric.

### Primary Drivers

* Landing Page Engagement
* Trial Activation
* User Value Generation

### Supporting Metrics

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate
* Revenue Per User
* Engagement Score

### Guardrail Metrics

* Refund Rate
* Support Ticket Rate
* Days to Convert

### KPI Tree Files

* `outputs/kpi_tree.png`
* `screenshots/kpi_tree_preview.png`

---

## Data Cleaning and Preparation

Data quality checks were performed in:

`analysis/experiment_analysis.xlsx`

### Checks Performed

| Check                 | Result                            |
| --------------------- | --------------------------------- |
| Missing Values        | Identified and documented         |
| Group Counts          | Verified                          |
| Duplicate User IDs    | Identified and reviewed           |
| Invalid Binary Values | None found                        |
| Revenue Outliers      | Reviewed using box plot analysis  |
| Segment Distribution  | Verified across experiment groups |

### Missing Values Found

| Column           | Missing Values |
| ---------------- | -------------: |
| device_type      |             18 |
| traffic_source   |             24 |
| engagement_score |             14 |
| days_to_convert  |           1336 |

### Data Quality Conclusion

The dataset was suitable for analysis after validation checks were completed.

---

## Experiment Analysis Approach

The analysis compared Control and Treatment groups across key funnel, engagement, and revenue metrics.

### Metrics Evaluated

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate
* Paid Conversion Rate
* Revenue Per User
* Revenue Per Converted User
* Refund Rate
* Support Ticket Rate
* Engagement Score
* Days to Convert

### Segment-Level Analysis

* Region
* Device Type
* Traffic Source

### Results Summary File

`outputs/experiment_summary.xlsx`

---

## Experiment Results Summary

| Metric                   | Control | Treatment |
| ------------------------ | ------: | --------: |
| User Count               |     693 |       715 |
| Paid Conversion Rate     |   3.17% |     6.99% |
| Average Revenue Per User |   51.75 |     53.88 |
| Average Engagement Score |   57.03 |     62.93 |
| Average Days to Convert  |    8.86 |      6.40 |

### Key Findings

* Paid Conversion Rate increased significantly.
* User engagement improved.
* Users converted faster.
* Revenue Per User increased.
* Funnel performance improved across multiple stages.

---

## Hypothesis Test Summary

A one-tailed two-proportion z-test was conducted using Paid Conversion Rate as the primary metric.

### Test Results

| Metric             |  Value |
| ------------------ | -----: |
| Z-Score            |   3.25 |
| P-Value            | 0.0006 |
| Significance Level |   0.05 |

### Conclusion

The p-value is lower than the significance level.

**Decision:** Reject H₀

The Treatment experience significantly improved Paid Conversion Rate compared with the Control experience.

---

## Guardrail Metrics Considered

### Positive Outcomes

* Higher Engagement Score
* Faster Time to Convert
* Higher Revenue Per User

### Risks Identified

* Higher Refund Rate
* Higher Support Ticket Rate
* Lower Revenue Per Converted User

### Assessment

The identified risks should be monitored but do not outweigh the benefits observed in the primary success metric.

---

## Segment-Level Insights

### Region Analysis

Treatment outperformed Control across all regions.

### Device Analysis

The strongest improvements were observed on Mobile and Tablet devices.

### Traffic Source Analysis

Referral traffic showed the largest improvement in conversion rate.

Social traffic was the only segment where Treatment underperformed Control.

---

## Final Recommendation

### Recommendation: Launch

The Treatment onboarding experience should be launched to all users.

#### Supporting Reasons

* Statistically significant conversion improvement
* Improved engagement
* Faster conversion
* Increased Revenue Per User
* Consistent performance across most segments

---

## Assumptions and Limitations

### Assumptions

* Experiment groups were randomly assigned.
* Data accurately reflects user behavior.
* Revenue values represent valid transactions.

### Limitations

* Analysis is based on a single experiment period.
* Long-term retention was not measured.
* Revenue quality requires continued monitoring.

---

## Repository Structure

```text
part2_kpi_experiment/
├── data/
│   └── campaign_experiment_data.xlsx
├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md
├── outputs/
│   ├── kpi_tree.png
│   ├── experiment_summary.xlsx
│   └── recommendation_memo.md
├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png
└── README.md
```

---

## Screenshots Included

* `summary_metrics.png`
* `hypothesis_test_output.png`
* `kpi_tree_preview.png`

---

## Project Outcome

The experiment demonstrated that the new onboarding campaign significantly improved Paid Conversion Rate while also increasing user engagement and accelerating conversion speed.

Based on statistical evidence and business impact analysis, the Treatment experience is recommended for rollout to all users.
