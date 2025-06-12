# Microsoft Sentinel - False Positive Time Savings Tracker

This repository contains a production-ready KQL query to track and report false positive alerts in Microsoft Sentinel
using **incident comments**. It helps security teams estimate operational efficiency, visualize time savings, and
justify automation or triage workflows.

## 🔍 What It Does

- **Extracts false positive alerts** tagged in incident comments (e.g., "analyze.intezer" and "False positive")
- Calculates:
  - `IncidentCount`
  - `Estimated_Minutes_Saved`
  - `Estimated_Hours_Saved`
  - `FTE_Saved` (based on 160 hrs/month)
- Groups data **monthly** for trend reporting

## 📊 Example Use Cases

- Build a Sentinel Workbook to visualize false positives over time
- Integrate with Power BI to show automation ROI
- Compare performance of threat intel tools (Intezer, Ontinue, etc.)
- Share results with leadership using real staffing impact

## 📂 Query File

See [`sentinel_false_positive_tracker.kql`](./sentinel_false_positive_tracker.kql)

## 🚀 How To Use

1. Add a comment like `"False positive"` when dismissing alerts (manually or via playbooks)
2. Paste the KQL into your Sentinel Workbook or Log Analytics
3. Optionally import the Workbook JSON included in this repo

> **Note**: This technique leverages the `mv-expand Comments` capability in Sentinel,
> and is not yet published by Microsoft Learn or community repos (as of June 2025).

## 📎 Attribution

Created by Terrick Taylor | GitHub: `@Timelord901`
