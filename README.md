# World Bank Projects Overview (1947 - Present)

This Tableau dashboard provides a comprehensive overview of World Bank-funded projects from 1947 to the most recent available year. It analyzes project funding trends, commitments, project costs, financial instruments, risk levels, and regional distribution.

⚠️ Important Notes 

- All insights in this project are based on the committed amounts, as listed in the World Bank data.

  These do not reflect actual disbursements — meaning the committed money may not have been fully spent or delivered due to changes, delays, or project cancellations.



- The dashboard was designed to be interactive in [Tableau](https://public.tableau.com/app/profile/sanjaya.kunwar/vizzes), but due to GitHub limitations, you can only explore it by:

  Downloading the .twbx file and opening in Tableau Desktop or Tableau Public

  Browsing through the provided screenshots

---


## 🎯 Goals of the Analysis

Before starting the analysis, the following questions were asked:
- How has World Bank investment changed over the years?
- Which countries and regions have received the most funding?
- What types of lending instruments were used?
- How much of the project cost is covered by commitments?
- Are there any patterns in risk levels and project status?

---

## 📊 Dashboard Overview
📌 At a Glance
| Metric               | Value         |
|----------------------|---------------|
| Total Projects       | 27,264        |
| Total Project Cost   | $3,534.13B    |
| Total Commitments    | $1,612.67B    |



<br><br>
The dashboard answers the following key questions using visuals:


### 1. **How has World Bank funding changed over time?**
- **Visual:** Time Series Chart (Funding Trends)
- **Insight:** Commitments have significantly grown after the 1990s with noticeable peaks post-2010.

- ![Alt Text](./Screnshots/Funding%20trend.png)

<br><br>

### 2. **What is the current status of World Bank projects?**
- **Visual:** Pie Chart (Project Status)
- **Insight:** Most projects are **Closed (64.23%)**, followed by **Dropped**, **Active**, and a few still in the **Pipeline**.

- ![Alt Text](./Screnshots/Project%20Status.png)

### 3. **How does project cost compare to commitments across lending types?**
- **Visual:** Horizontal Bar Chart
- **Insight:** Some instruments like "Special Structural Adjustment Loan" show close alignment between cost and commitment, while others reveal gaps.

- ![Alt Text](./Screnshots/Cost%20vs%20commitment%20by%20lending%20type.png)

### 4. **Which regions receive the highest commitment percentage?**
- **Visual:** Bar Chart (Commitment % by Region)
- **Insight:** **Africa** received the highest percentage of project costs covered by World Bank funding (64.64%), followed by Latin America and Europe.

   ![Alt Text](./Screnshots/Contribution%20of%20world%20bank%20to%20region.png)

<br><br>
### 5. **How are projects geographically distributed and what’s their funding status?**
- **Visual:** World Map
- **Insight:** Projects are distributed globally, with higher commitments in countries like Guatemala, South Sudan, Somalia, and African nations.

-  ![Alt Text](./Screnshots/Geographical%20analysis.png)

<br><br>
### 6. **How is funding distributed by financial type?**
- **Visual:** Pie Chart
- **Insight:** Funding types like **Investment Loans**, **Program-for-Results**, and **Grants** form the major share of commitments.

  ![Alt Text](./Screnshots/Financial%20Type%20Distribution.png)

<br><br>
### 7. **How does project cost vary by environmental risk rating?**
- **Visual:** Vertical Bar Chart
- **Insight:** Projects marked as **Substantial** and **Moderate** risk received the highest adjusted commitments.

![Alt Text](./Screnshots/Risk%20Assesment.png)

<br><br>
## 🧹 Data Cleaning Process

- Data was sourced directly from the **[World Bank Open Projects Dataset](https://projects.worldbank.org/en/projects-operations/projects-list)**.
- Timeline: Covers **projects from 1947 to present**.
- **Inconsistencies were found** between project documents and spreadsheet amounts.
  - In such cases, **the most reliable source value was kept**.
- **Monetary formatting varied**:
  - Some amounts were in small values (e.g., 0.05, 1, 10)
  - Some were in **millions** (e.g., 100, 500, 1000+)
  - All values were **converted into consistent whole numbers** for better aggregation and visualization.

---

## 📐 Calculated Fields

### 1. **Adjusted Commitment**
To handle gaps where the project cost was 0, the following field was created:
```tableau
IF [Current Project Cost] > 0 THEN [Total IBRD, IDA and Grant Commitment] ELSE 0 END
```

### 2. **Commitment Percentage on Project Cost**
To calculate how much of a country or group’s project cost is covered by commitment:
```tableau
IF SUM([Current Project Cost]) = 0 THEN
    NULL
ELSE
    SUM([Adjusted Total Commitment]) / SUM([Current Project Cost])
END
```
This calculation adjusts based on the dimension being used (e.g., Country, Lending Instrument, Region).

---



## 📁 Files and Format
- Tableau Workbook (.twbx)
- Screenshot preview
- README file
- Dataset
---

## 📍 Conclusion
This dashboard helps uncover:
- How World Bank investments evolved over time
- Which countries and regions received more support
- What type of financing tools were used
- Risk exposure and project statuses


---




**Sanjaya Kunwar**  
LinkedIn: [Click Here](https://www.linkedin.com/in/sanjaya-k-71938217b/)  
Tableau Public: [Click Here](https://public.tableau.com/app/profile/sanjaya.kunwar/vizzes)

Feel free to explore, download, and share!

