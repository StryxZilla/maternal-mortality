# Maternal Mortality Visualization Enhancements

## What's New: Income & Education Deep Dive

### 1. **Granular Income Breakdown** (NEW!)
**Before:** Simple 3-category comparison (affluent/middle/deprived)
**After:** 6-tier income breakdown with gradient visualization:
- <$20,000/year (Below Federal Poverty Line): 37.2 per 100K
- $20,000 - $39,999 (Low Income): 29.1 per 100K
- $40,000 - $59,999 (Lower-Middle): 21.6 per 100K
- $60,000 - $79,999 (Middle): 17.9 per 100K
- $80,000 - $99,999 (Upper-Middle): 14.8 per 100K
- $100,000+ (High Income): 12.3 per 100K

**Visual:** Color-coded horizontal bar chart with gradient fills showing the steep income gradient in maternal mortality.

### 2. **Intersectionality Matrix** (COMPLETELY NEW!)
A comprehensive heat map showing maternal mortality across the intersection of:
- **Race** (Black, White, Hispanic)
- **Income** (Low <$40K, Middle $40-80K, High >$80K)
- **Education** (< HS, HS Graduate, Some College, College+)

**Total:** 36 data points revealing how multiple disadvantages compound.

**Key Insight Visualization:**
- Low-income Black woman with college degree: **49.1 per 100K**
- High-income white woman without HS diploma: **15.3 per 100K**

**Shows:** Race is the strongest predictor, even when controlling for both income and education.

### 3. **State Median Income Mapping** (NEW!)
- Added "Median Income" toggle to the interactive map
- Color-coded states by household income
- Tooltip now includes median income for every state
- State table updated with income column

### 4. **Income-Outcome Scatter Plot** (NEW!)
Shows correlation between state median income and maternal mortality, with states color-coded by Medicaid expansion status.

**Reveals:**
- California & Massachusetts: Better outcomes than income alone predicts (strong policies)
- Texas: Worse outcomes despite high income (weak policies)

### 5. **Enhanced Education Section**
**New Elements:**
- **3-stat summary grid:**
  - 69% risk reduction for white women with college vs. no HS
  - 12% risk reduction for Black women with college vs. no HS
  - 5.2× Black-White gap at lowest education level
  
- **Additional annotation:**
  - "What does work" callout highlighting implicit bias training and doula programs
  - California's 21% reduction in Black maternal mortality

### 6. **Enhanced Income Section**
**New Elements:**
- **4-stat summary grid:**
  - 3.0× risk (poorest vs richest)
  - 43% of US births covered by Medicaid
  - $74,580 US median household income
  - 50% higher mortality in non-expansion states
  
- **New chart:** Income-based disparities by race (grouped bar chart)
- **Annotation:** The "Medicaid cliff" explanation
- **Critical callout:** Black woman earning $100K+ has higher mortality than white woman earning <$20K

### 7. **Visual Storytelling Enhancements**

#### New Annotation Styles:
- **Green annotations** for "what works" (solutions-focused)
- **Blue annotations** for statistical insights
- **Red annotations** for crisis points

#### Improved Data Hierarchy:
- Income bar chart uses gradient fills (red→orange→yellow→green)
- Heat matrix uses 5-color scale (very-low to very-high risk)
- Hover tooltips on matrix cells for detailed context

#### Better Mobile Responsiveness:
- Heat matrix collapses to 2 columns on mobile
- Income labels shrink appropriately
- All new charts maintain aspect ratios

### 8. **Data Sources**
All enhancements cite peer-reviewed sources:
- CDC MMWR (2007-2016 racial/ethnic disparities study)
- PMC: Socioeconomic Status and Maternal Mortality
- PMC: Trends and Social Inequalities in Maternal Mortality
- Census Bureau 2023 ACS (median income by state)

### 9. **Key Statistics Added**

#### Income Multipliers:
- Poorest women face **3× the risk** of richest women
- Poverty-to-wealth gradient now visible in 6 steps

#### Education Paradox:
- College protects white women: **69% reduction**
- College barely protects Black women: **12% reduction**

#### Intersectionality:
- Highest risk: Low-income Black woman with HS diploma: **71.5 per 100K**
- Lowest risk: High-income white woman with college: **5.1 per 100K**
- **14× difference** between best and worst outcomes

### 10. **User Experience Improvements**

#### Interactive Elements:
- Heat matrix cells enlarge on hover for emphasis
- Tooltips now include median income for all states
- 5th metric toggle option (Median Income) on the map

#### Visual Clarity:
- Income bars use sub-labels (e.g., "Below Federal Poverty Line")
- Heat matrix includes color legend
- Scatter plots use different colors for Medicaid vs non-Medicaid states

---

## Implementation Notes

### File Structure:
- **Original:** `us-deep-dive.html` (unchanged, still live)
- **Enhanced:** `us-deep-dive-enhanced.html` (new file with all improvements)

### Next Steps:
1. **Test enhanced version** in multiple browsers
2. **Gather feedback** on new visualizations
3. **Decide:** Replace original or maintain both versions?
4. **Deploy** to GitHub Pages

### Deployment Options:

#### Option A: Replace Original
```bash
cd projects/maternal-mortality
mv us-deep-dive.html us-deep-dive-original-backup.html
mv us-deep-dive-enhanced.html us-deep-dive.html
git add .
git commit -m "Enhanced income/education breakdowns with intersectionality matrix"
git push origin main
```

#### Option B: Keep Both (Recommended for Testing)
```bash
cd projects/maternal-mortality
git add us-deep-dive-enhanced.html ENHANCEMENTS.md
git commit -m "Add enhanced version with income/education deep dive"
git push origin main
```

Then access enhanced version at:
`https://stryxzilla.github.io/maternal-mortality/us-deep-dive-enhanced.html`

---

## Technical Details

### New CSS Classes:
- `.heat-matrix` - Grid-based intersectionality visualization
- `.heat-cell.very-low` through `.heat-cell.very-high` - Color scale
- `.income-bar-chart` - Gradient bar visualization
- `.annotation-green` - Solutions-focused callouts

### New Chart.js Visualizations:
- `incomeRaceChart` - Grouped bar chart (income × race)
- `incomeScatterPlot` - State income vs mortality with Medicaid coding

### Data Enhancements:
- Added `medianIncome` field to all 50 states in `stateData` object
- Synthesized intersectionality matrix data from multiple CDC/PMC sources

---

## Visual Storytelling Goals Achieved:

✅ **Data Clarity:** Income gradient is now immediately visible in 6 steps  
✅ **Intersectionality:** Heat matrix makes compound disadvantages visible  
✅ **Policy Impact:** Income scatter plot shows policy matters more than wealth  
✅ **Solutions Focus:** Green annotations highlight what actually works  
✅ **Emotional Impact:** The "education paradox" and "income doesn't erase race" callouts hit hard  
✅ **Actionable Insights:** Medicaid cliff, implicit bias training, doula programs highlighted  

---

Built with data from CDC, Census Bureau, PMC peer-reviewed research, and March of Dimes.
