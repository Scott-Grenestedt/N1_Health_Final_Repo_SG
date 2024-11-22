# **N1 Health Food Access Analysis**

## **Project Overview**
This project addresses food access challenges and their impact on population health. The analysis was conducted for N1 Health's client, a Medicare Advantage Plan, to identify areas most in need of food access programs and assess the potential health outcomes of such interventions.

### **Objectives**
1. Identify geographic regions (e.g., counties, census tracts) with significant food access challenges.
2. Explore key variables contributing to poor food access.
3. Determine the population size and subgroups that would benefit most from an intervention.
4. Project the health impacts of implementing a food access program.

---

## **Key Findings**
### **Top Target: Harris County, TX**
- **Why Harris County?**
  - Ranked highest in absolute numbers of low-access individuals overall, including children and seniors.
  - Demonstrates a high need for intervention based on combined metrics of food access and health outcomes.

### **Key Insights:**
1. **Populations at Risk:**
   - Seniors (~30,000 individuals projected to benefit from intervention).
   - Children (strong correlation between low child food access and overall county challenges).
2. **Predictive Analysis:**
   - Obesity is the strongest health predictor of food access issues (`ACCESS2_CrudePrev`).
   - Features such as senior and child food access (`LACCESS_CHILD15`, `LACCESS_SENIORS15`) are significant predictors of overall food access challenges.
3. **Projected Health Improvements:**
   - A reduction in obesity rates is expected to lead to improvements in related health outcomes (e.g., diabetes, hypertension).

---

## **Data Sources**
- **CDC 500 Cities Project**: Local-level health data.
- **FDA Food Atlas**: Food access metrics.

---

## **Methodology**
### **1. Data Cleaning and Preparation**
- **Inner Join**:
  - Merged the `access` and `five_hundred_cities` tables using county-level FIPS codes.
  - Filtered data for consistency (e.g., excluded 4-digit FIPS codes due to mismatched formatting).
- Final dataset: ~19,500 rows across 109 columns.

### **2. Exploratory Data Analysis**
- **Identified High-Risk Counties:**
  - Focused on absolute numbers of low-access individuals rather than percentages to prioritize high-impact urban areas.
  - Harris County stood out for overall population, seniors, and children with low food access.
- **Correlation Analysis:**
  - Explored relationships between food access and health metrics (e.g., obesity, diabetes).

### **3. Predictive Modeling**
- **Random Forest Feature Selection:**
  - Identified significant predictors of food access (`ACCESS2_CrudePrev`) and health outcomes (`OBESITY_CrudePrev`).
  - Key features for obesity prediction:
    1. Self-reported poor health (`PHLTH_CrudePrev`).
    2. Smoking rates (`CSMOKING_CrudePrev`).
    3. Physical inactivity (`LPA_CrudePrev`).

---

## **Visualizations**
1. **Heatmaps**:
   - Highlighted counties with high populations of low-access individuals (overall, seniors, children).
   - Correlation heatmap for obesity and other health metrics.
2. **Bar Charts**:
   - Feature importance for food access and obesity prediction.

---

## **Conclusions and Recommendations**
### **Where Should We Deploy a Food Access Program?**
- **Harris County, TX**: High population and significant food access challenges across multiple demographics.

### **How Many People Will Be Included?**
- ~30,000 seniors projected to benefit, with additional trickle-down effects for children and multigenerational households.

### **Which Subgroup Might Benefit the Most?**
- **Primary**: Seniors (Medicare Advantage focus).
- **Secondary**: Children and low-income households.

### **What is the Projected Impact?**
- **Health Improvements**:
  - Reduction in obesity rates, with correlated benefits for diabetes, hypertension, and self-assessed health.

