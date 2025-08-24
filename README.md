````
# 🏋️‍♂️ Gym Analysis Dashboard (Power BI)

A fully interactive **Power BI Dashboard** built for **Gym Analytics**.  
It covers **Finance, Memberships, and Health Calculators** with a unique feature of **dynamic theme switching** (4 color preferences).  

---

## 🎨 Dynamic Color Themes
This dashboard includes a **custom theme switcher** with **4 color palettes**.  
When a theme is selected, the **entire dashboard auto-updates**, including charts, cards, and visuals.  

**Benefits:**
- Personalized viewing experience.  
- Better contrast in different environments (dark/light).  
- Professional look for client presentations.  

*(Add screenshots of the 4 themes here)*  

---

## 📑 Features
- 🔄 **Dynamic Color Themes (4 presets)**  
- 📊 **Finance Analysis** → Revenue, Expenses, Profit, Monthly Trends  
- 🧍 **Membership Analysis** → Active vs Expired, Membership Types, Churn Rate  
- ⚡ **Health Calculators** → BMI, BMR, TDEE, Calorie Targets  
- 🎨 **Custom Visuals** → SVG progress bars, conditional formatting, dynamic titles  
- 📅 **Calendar Table & Parameters** for interactivity  

---

## 📊 Dashboard Pages
### 1️⃣ Homepage
- High-level KPIs (Users, Revenue, Profit, Active Members)  
- User growth trend with **conditional colors**  
- Last Refresh Time  

### 2️⃣ Finance Page
- Revenue, Expenses, and Profit  
- Monthly Profit Trend line chart  
- Profit Margin % calculation  
- (Optional) Expense breakdown by category  

### 3️⃣ Calculator Page
- **BMI Calculator** with labels (Underweight, Normal, Overweight, Obese)  
- **BMR & TDEE** with activity multipliers  
- **Calorie Targets** (Maintain, Mild Loss, Loss, Extreme Loss)  
- Interactive sliders (Age, Height, Weight, Gender, Activity)  

### 4️⃣ Members Page
- Membership distribution (Platinum, Gold, Silver)  
- Active vs Expired breakdown  
- Membership trend over time  
- **Churn Rate**  
- Filters: Membership Type, Gender, Age Group  

---

## 🧮 Key DAX Highlights

```DAX
-- Users Count
Users_Count = DISTINCTCOUNT(Users[UserID])

-- Profit
Profit = [Revenue] - [Expenses]

-- Profit Margin %
Profit Margin % = DIVIDE([Profit], [Revenue], 0)

-- Churn Rate
Churn Rate =
DIVIDE(
    [Platinum_Expired] + [Gold_Expired] + [Silver_Expired],
    [User_Platinum] + [User_Gold] + [User_Silver],
    0
)

-- Custom SVG Progress Bar
SVG_BarChart =
VAR ProgressValue = [ProgressPercent]
VAR BarWidth = 260
VAR ProgressWidth = BarWidth * (ProgressValue / 100)
RETURN
"data:image/svg+xml;utf8,
<svg ...>"   -- shortened for brevity
````

---

## 🚀 How to Use

1. Clone this repository.
2. Open the `.pbix` file in **Power BI Desktop**.
3. Connect to your dataset (`Users`, `Payments`, `Expenses`).
4. Select your preferred **theme (4 options)**.
5. Explore the dashboard pages.

---

## 📌 Future Enhancements

* 💡 What-If analysis for gym pricing scenarios
* 🔎 Drill-through pages for member profiles
* 📱 Optimized mobile layout

---


