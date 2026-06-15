# Project Cycle 4: Logistic Regression Analysis
## 專案循環 4：羅吉斯迴歸分析

### 👥 Team Information / 專案基本資訊
* **Member / 成員姓名:** 113370216 彭佳淳 (Jia-Chun Peng)
* **Project Repository:** 
* **Presentation Video:**

---

### 🎯 Selected Research Topic / 研究主題與核心問題

本專案基於美國 CDC 的 `YRBS_2007.csv` 數據集，將焦點集中於青少年遭受的極端創傷經驗，並建立具備深度推論能力的羅吉斯迴歸模型。

Our project utilizes the CDC's `YRBS_2007.csv` dataset, strictly focusing on severe trauma exposure among adolescents to build a highly inferential Logistic Regression model.

* **Project Title / 專案名稱:** The Compounding Effect of Intimate Partner Violence and Sexual Trauma on Adolescent Suicidal Ideation (青春期的隱形牢籠：青少年親密關係暴力與性創傷對自殺意念的加乘效應)
* **Core Research Question / 核心研究問題:** Do intimate partner violence and forced sexual intercourse significantly increase the probability of suicidal ideation among adolescents, and how does biological sex affect this vulnerability? (遭受親密關係暴力與強迫性行為等創傷，是否會顯著增加青少年考慮自殺的勝算？生理性別又在其中扮演何種脆弱性角色？)

---

### 🧪 Variables Definition / 變數定義與特徵工程

#### 1. Response Variable (Y) / 反應變數
* **Original Column / 原始欄位:** `ConsideredSuicide`
* **Binary Recoded Variable / 重編碼二元變數:** `Suicide_Binary`
* **1 (Yes / 高風險組):** Students who seriously considered attempting suicide in the past 12 months. (過去 12 個月內曾認真考慮自殺者)
* **0 (No / 對照組):** Students who did not consider suicide. (未考慮自殺者)

#### 2. Predictor & Control Variables (X) / 預測與控制變數
* **Primary Predictor: Composite Trauma Level / 複合創傷指標**
  * **Variable:** `Trauma_Level` *(Engineered from BoyfriendGirlfriendPhysicallyHurt and ForcedSexualIntercourse)*
  * **Groups:** * `Both Traumas` (雙重創傷)
    * `Either Trauma` (單一創傷)
    * `No Trauma` (無創傷 — *Regression Baseline / 模型基準組*)
* **Control Variable: Biological Sex / 生理性別**
  * **Variable:** `Sex_Label`
  * **Groups:** * `Female` (女性)
    * `Male` (男性 — *Regression Baseline / 模型基準組*)

---

### 🛠️ Statistical Methodology / 分析管線與統計方法

* **Data Cleaning Protocol / 資料清洗協議:**
  Enforced Listwise Deletion (`.dropna()`) on core target columns to eliminate missing values, ensuring a synchronized and perfectly aligned analytical matrix for regression modeling.
  
  針對核心目標欄位嚴格執行完全個案剔除法，排除所有缺失值，確保羅吉斯迴歸模型建立在完全乾淨且同步的數據矩陣上。

* **Exploratory Data Analysis / 探索性資料分析:**
  Aggregated descriptive proportions and generated a Compounding Effect Bar Chart alongside a Gender Interaction Heatmap to visually synthesize the extreme structural variations in risk.
  
  聚合計算描述性比例，並繪製創傷加乘效應長條圖與性別交互作用熱圖，直觀展現風險的極端結構性變異。

* **Statistical Inference / 統計推論方法:**
  Executed a Multiple Logistic Regression using `statsmodels`. We established logical baselines (No Trauma and Male) via Treatment contrast coding, transforming raw log-odds into actionable Odds Ratios (OR) with 95% Confidence Intervals to rigorously evaluate statistical significance.
  
  運用多元羅吉斯迴歸模型進行推論。透過對比編碼將無創傷與男性設為基準組，並將原始對數勝算轉換為具備實質解釋力的勝算比（OR）與 95% 信賴區間，嚴格評估統計顯著性。

---

### 📝 Conclusion & Policy Recommendations / 結論與政策建議

* **The Compounding Effect of Trauma / 毀滅性的創傷加乘效應:**
  The regression model confirms a massive compounding effect. Controlling for sex, adolescents exposed to Both Traumas exhibit an Odds Ratio of approximately 6.0 compared to the No Trauma baseline. Trauma impact is not merely additive; it is exponentially destructive.
  
  迴歸模型證實了巨大的加乘效應。在控制性別後，遭受雙重創傷的青少年，其產生自殺意念的勝算約為無創傷基準組的 **6.0 倍**。創傷的影響並非單純相加，而是呈指數級的破壞 ($1+1 > 2$)。

* **Structural Gender Vulnerability / 結構性的性別脆弱落差:**
  Female adolescents face a staggering baseline risk premium. Holding trauma exposure constant, females have an Odds Ratio of nearly 2.0 compared to males, highlighting severe internalizing vulnerability during the pubertal transition.
  
  女性青少年面臨極高的基準風險溢價。在承受同等創傷的條件下，女性考慮自殺的勝算幾乎是男性的 **2.0 倍**，凸顯了青春期極度嚴峻的情感內化脆弱性。

* **Policy Recommendation / 核心政策建議:**
  Public healthand educational sectors must shift toward trauma-informed protocols. Given the OR of 6.0 for dual exposure, counselors must actively screen for overlapping victimization rather than treating violent incidents in isolation. Furthermore, gender-sensitive support systems must be deployed immediately to address the disproportionate burden on young women.
  
  公衛與教育部門必須轉向「創傷知情（Trauma-informed）」的處理機制。鑑於雙重創傷極高的勝算比（$OR \approx 6.0$），輔導系統必須主動篩檢潛在的重疊受害史，傳統單一事件單一處理的消極思維。同時，必須立即部署具備性別敏感度（Gender-sensitive）的支持系統，以緩解年輕女性不成比例的心理與社會污名負擔。
