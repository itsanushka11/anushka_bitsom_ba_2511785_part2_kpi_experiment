# anushka_bitsom_ba_2511785_part2_kpi_experiment
Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

# Business Context

This project analyzes the performance of a new onboarding and activation campaign launched by a subscription-based digital product company. The company aims to improve user activation, engagement, and conversion into paying subscribers.

Users were randomly assigned to one of two groups:

- Control Group: Existing onboarding experience
- Treatment Group: New onboarding and activation campaign

The objective of this analysis is to determine whether the treatment experience should be rolled out to all users based on business impact, statistical evidence, and guardrail metric evaluation.

---

Business Problem Statement

The company must decide whether the new onboarding and activation campaign should replace the existing onboarding experience.

This decision impacts multiple stakeholders, including product teams, marketing teams, customer success teams, and company leadership. The primary goal is to increase the number of users who convert into paying subscribers while maintaining a positive user experience and healthy business performance.

Success will be evaluated using a primary North Star metric supported by additional KPIs and guardrail metrics. A recommendation will only be made if the treatment demonstrates meaningful business improvement supported by statistical evidence and without creating significant risks in key guardrail metrics.

---

# Dataset Description

The dataset contains user-level experiment data collected from both Control and Treatment groups.

Key variables include:

- User ID
- Experiment Group
- Landing Page Visit
- Trial Start
- Onboarding Completion
- Paid Conversion
- Revenue
- Refund Request
- Support Ticket
- Engagement Score
- Days to Convert
- Region
- Device Type
- Traffic Source
- Plan Type

The dataset is stored as:

"data/campaign_experiment_data.xlsx"

---

# North Star Metric

Selected North Star Metric: Paid Conversion Rate

Definition

Paid Conversion Rate measures the percentage of users who convert into paying subscribers.

Formula:

Paid Conversion Rate = Number of Paid Conversions ÷ Total Users

---

Why This Is the Main Success Metric

The objective of the onboarding and activation campaign is to increase the number of users who become paying customers. Since the company operates on a subscription-based business model, paid conversion directly reflects whether the campaign successfully drives business growth.

A higher paid conversion rate means:

- More users are becoming customers.
- Revenue potential increases.
- Customer acquisition efforts become more effective.
- Long-term subscription growth improves.

Because the experiment is specifically designed to improve user activation and conversion, Paid Conversion Rate is the most appropriate North Star metric.

---

Why Other Metrics Are Supporting Metrics

Several metrics help explain user behavior but do not directly measure business success.

Landing Page Visit Rate

Indicates whether users enter the onboarding funnel but does not generate revenue by itself.

Trial Start Rate

Measures activation interest but does not guarantee payment.

Onboarding Completion Rate

Shows onboarding effectiveness but does not necessarily lead to conversion.

Engagement Score

Measures user interaction and product usage but is not the final business outcome.

Average Revenue Per User (ARPU)

Provides revenue insights but depends on users first converting into paying customers.

Days to Convert

Measures conversion speed but not conversion success.

These metrics are valuable for understanding performance drivers, but they support the North Star metric rather than replace it.

---

Connection to Business Growth

Paid Conversion Rate directly impacts company growth because every additional converted user contributes to subscription revenue.

Improvements in paid conversion can lead to:

- Higher recurring revenue
- Better customer acquisition efficiency
- Improved return on marketing investment
- Greater long-term customer value

Therefore, increasing Paid Conversion Rate aligns closely with the company's strategic objectives.

---

Risks of Optimizing This Metric Blindly

Focusing only on Paid Conversion Rate may create unintended business problems.

Potential risks include:

- Increased refund requests from low-quality conversions
- Higher support ticket volume due to onboarding confusion
- Poor customer experience
- Lower customer retention after conversion
- Performance declines within specific user segments

For this reason, Paid Conversion Rate must be evaluated alongside guardrail metrics such as Refund Rate, Support Ticket Rate, Engagement Score, and Segment-Level Performance before making a rollout decision.

---

# KPI Tree Summary

North Star Metric:

Paid Conversion Rate

Primary KPI Drivers:

1. Acquisition Quality

- Landing Page Visit Rate
- Traffic Source Quality

2. Activation Success

- Trial Start Rate
- Onboarding Completion Rate

3. User Engagement

- Engagement Score
- Days to Convert

Guardrail Metrics:

- Refund Rate
- Support Ticket Rate
- Average Revenue Per User
- Segment-Level Performance

The complete KPI tree is available in:

"outputs/kpi_tree.png"

Preview screenshot:

"screenshots/kpi_tree_preview.png"

---

Data Cleaning and Preparation

The dataset was reviewed before analysis to ensure data quality.

The following checks were performed:

Missing Values

Missing values were identified and reviewed across all variables. Missing values in categorical fields were documented, while missing values in conversion-related fields were assessed for business relevance.

Duplicate User IDs

Duplicate user records were identified and reviewed to ensure they did not distort experiment results.

Group Counts

Control and Treatment group sizes were validated to confirm proper experiment allocation.

Binary Value Validation

Binary fields such as conversions, onboarding completion, support tickets, and refunds were checked to ensure values were limited to valid 0/1 entries.

Revenue Outlier Review

Revenue distributions were reviewed to identify unusual observations that could distort average revenue metrics.

Segment Distribution Review

Region, device type, traffic source, and plan type distributions were compared across experiment groups to verify balanced allocation.

The cleaned dataset and analysis workbook are available in:

"analysis/experiment_analysis.xlsx"

---

# Experiment Analysis Approach

The analysis compared Control and Treatment groups across key business metrics, including:

- User Count
- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Paid Conversion Rate
- Average Revenue Per User
- Average Revenue Per Converted User
- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Average Days to Convert

Additional segment-level analysis was conducted for selected metrics across:

- Region
- Device Type
- Traffic Source
- Plan Type

Results are summarized in:

"outputs/experiment_summary.xlsx"

---

# Hypothesis Testing

Metric Tested

Paid Conversion Rate

Null Hypothesis (H₀)

There is no difference in paid conversion rate between the Control and Treatment groups.

Alternative Hypothesis (H₁)

The Treatment group has a higher paid conversion rate than the Control group.

Test Type

One-tailed Two-Proportion Z-Test

Significance Level

α = 0.05

Results

- Control Conversion Rate = 3.17%
- Treatment Conversion Rate = 6.99%
- Z Statistic ≈ 3.25
- P Value ≈ 0.0011

Since the p-value is below the significance threshold of 0.05, the null hypothesis is rejected.

This indicates that the treatment campaign significantly improves paid conversion performance.

Detailed test notes are available in:

"analysis/hypothesis_test_notes.md"

Evidence screenshot:

"screenshots/hypothesis_test_output.png"

---

# Guardrail Metrics Considered

To ensure business improvement is sustainable, the following guardrail metrics were evaluated:

- Refund Rate
- Support Ticket Rate
- Average Revenue Per User
- Average Revenue Per Converted User
- Engagement Score
- Days to Convert
- Segment-Level Performance

These metrics were reviewed to identify any negative side effects associated with the treatment experience.

---

# Final Recommendation

Recommendation: Launch

The treatment campaign demonstrates a statistically significant improvement in paid conversion rate compared to the control experience.

The experiment provides strong evidence that the new onboarding experience improves user activation and conversion performance.

While conversion improvements are substantial, support-related metrics should continue to be monitored to ensure increased customer support demand does not offset business gains.

Therefore, the recommendation is to proceed with a broader rollout of the treatment experience while maintaining ongoing monitoring of guardrail metrics.

---

# Assumptions and Limitations

- Experiment assignment is assumed to be random.
- Revenue quality is evaluated using available revenue fields only.
- User behavior outside the observed experiment window is not included.
- Missing values may impact certain segment analyses.
- Results reflect the available sample and may differ in future cohorts.

---

# Repository Contents

Data

- data/campaign_experiment_data.xlsx

Analysis

- analysis/experiment_analysis.xlsx
- analysis/hypothesis_test_notes.md

Outputs

- outputs/kpi_tree.png
- outputs/experiment_summary.xlsx
- outputs/recommendation_memo.md

Screenshots

- screenshots/summary_metrics.png
- screenshots/hypothesis_test_output.png
- screenshots/kpi_tree_preview.png

Documentation

- README.md
