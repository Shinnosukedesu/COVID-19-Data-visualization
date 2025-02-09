

# **COVID-19 Global Analysis Dashboard in Power BI**

This guide will help you create a comprehensive and interactive COVID-19 dashboard using Power BI. The dashboard visualizes key metrics like confirmed cases, deaths, recoveries, and trends across countries/regions. It includes various interactive elements like slicers, maps, and charts to make the data exploration insightful and engaging.

---

## **Steps to Build the COVID-19 Dashboard**

### **Step 1: Open Power BI Report**

- Open Power BI and create a new report.

### **Step 2: Import Dataset into Power BI**

1. Click on **Home** → **Get Data**.
2. Select the dataset (e.g., *CoronaVirus Data*) in **CSV** or **Excel (.xl)** format and **Load** it.

### **Step 3: Create Calculated Measures (Fields)**

- Right-click on the dataset in the **Fields** section.
- Select **New Measure** and enter the following formulas:

```DAX
Active cases = SUM('CoronaVirus Data'[Confirmed Daily])  
              - SUM('CoronaVirus Data'[Deaths Daily])  
              - SUM('CoronaVirus Data'[Recovered Daily])

Average Confirm daily = SUM('CoronaVirus Data'[Confirmed Daily])  
                        / DISTINCTCOUNT('CoronaVirus Data'[Date])

Average Death daily = SUM('CoronaVirus Data'[Deaths Daily])  
                      / DISTINCTCOUNT('CoronaVirus Data'[Date])

Average Recovered daily = SUM('CoronaVirus Data'[Recovered Daily])  
                          / DISTINCTCOUNT('CoronaVirus Data'[Date])

Mortality Rate = SUM('CoronaVirus Data'[Deaths Daily])  
                 / SUM('CoronaVirus Data'[Confirmed Daily])

Recovery Rate = SUM('CoronaVirus Data'[Recovered Daily])  
               / SUM('CoronaVirus Data'[Confirmed Daily])
```

### **Step 4: Design the Dashboard**

#### **1. Add a Logo**

- Go to **Insert** → **Image** → Upload the desired logo.

#### **2. Add a Title**

- Go to **Insert** → **Text Box** → Type: **"COVID-19 Global Analysis"**.

#### **3. Add KPI Cards**

- In the Visualization pane, drag and drop the **Card visual**, then assign the following fields:
  - Mortality Rate
  - Recovery Rate
  - Average Confirmed Cases per Day
  - Average Recovered Cases per Day
  - Average Deaths per Day

#### **4. Add Gauge Visuals**

- In the Visualization pane, drag the **Gauge visual** and assign:
  - Total Cases → Confirmed Daily (Value)
  - Active Cases → Active Cases (Value), Confirmed Daily (Max Value)
  - Deaths → Deaths Daily (Value), Confirmed Daily (Max Value)
  - Recovered → Recovered Daily (Value), Confirmed Daily (Max Value)

#### **5. Add Slicers for Filtering Data**

- In the Visualization pane, drag the **Slicer visual** and assign fields:
  - Month-Year
  - Date
  - Country/Region

#### **6. Add a Map for Confirmed Cases**

- Use the **Map visual** and assign:
  - Country/Region → Location
  - Confirmed Daily → Size

#### **7. Add a Clustered Bar Chart for Cases by Country**

- Use the **Clustered Bar Chart visual** and assign:
  - Country/Region → Axis
  - Confirmed Daily → Values

#### **8. Add a Line & Clustered Column Chart for Trends**

- Use the **Line & Clustered Column Chart visual** and assign:
  - Date → Shared Axis
  - Deaths → Column Values
  - Confirmed & Recovered → Line Values

#### **9. Add a Table for Data Summary**

- Use the **Table visual** and assign:
  - Country/Region, Confirmed Daily, Recovered Daily, Deaths Daily
  - Average Confirmed Daily, Average Recovered Daily, Average Deaths Daily
  - Recovery Rate, Mortality Rate

- **Apply Conditional Formatting**:
  - Go to **Format** → **Conditional Formatting**
  - Select the desired column and enable **Data Bars**

---

## **Additional Information**

### **Datasets Available:**

The dataset for this dashboard is provided in **CSV** and **Excel (.xl)** formats. You can import the data into Power BI to recreate or modify the dashboard as needed.

### **Access the Dashboard:**

- **Power BI Service Dashboard Link**:  
   You can interact with the published **COVID-19 Global Analysis Dashboard** by clicking on the following link:  
   (https://1drv.ms/u/c/48e06ba98674206f/EaxZfg1EQ1hNoZRsAJD9EE8BuqaT_c9tdqd7tKgqOB58qg?e=JdIkX7)

- **Power BI File (.pbix)**:  
   You can also download the file under the extension .pbix for real time interaction and editing

---

## **Conclusion**

This Power BI dashboard provides an interactive and engaging way to analyze global COVID-19 trends. By incorporating various visual elements such as maps, KPIs, and trend charts, it allows users to track the progression of the pandemic across different countries and regions. The slicers and filters give users flexibility in data exploration.

For modifications or additional features, the Power BI file and dataset can be adjusted according to user needs.
