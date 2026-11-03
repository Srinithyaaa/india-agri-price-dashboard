# India Agricultural Market Price Dashboard (Power BI)

An interactive Power BI dashboard that compares agricultural commodity prices across Indian states and markets, using a daily Agmarknet snapshot (1 Nov 2026).

## Questions it answers
- Which markets and states are cheapest or costliest for a commodity?
- How large is the gap between the cheapest and costliest market?
- Which commodities have the most unstable prices (price spread)?

## Dashboard pages
1. **Market Overview:** price by state and top 10 costliest markets for a selected commodity
2. **Price Insights:** price gap and spread across all commodities
3. **Key Insights:** findings and notes on the data

![Market Overview](page1_overview.png)
![Price Insights](page2_insights.png)

## Key insights
- Staples (wheat, bajra, mustard) have a price spread of only 2-4%, while perishables (guar, wet peas, spinach) reach 36-47%.
- Jasmine has the widest price gap: ₹400 to ₹1,150 per kg across 11 markets.
- Tomato ranges from ₹7 to ₹69 per kg across 266 markets; Maharashtra is cheapest on average.

## Data
- **Source:** Agmarknet daily mandi prices, via data.gov.in (snapshot of 1 Nov 2026)
- **Size:** 8842 rows after cleaning, 22 states

## Data cleaning (Power Query)
- Renamed columns and fixed the date format (dd/mm/yyyy, English-India locale)
- Removed rows with a modal price under ₹100 per quintal (suspected unit errors) and one garbled commodity name
- Trimmed text columns
- Added `Modal Price per kg` (₹/quintal ÷ 100) and `Price Spread` (max − min)

## DAX measures
Avg Price per kg, Cheapest Price per kg, Costliest Price per kg, Price Gap per kg, Avg Spread per kg, Spread %, Spread % (10+ markets), Total Markets, Total Commodities, Total States

## Limitations
- Single-day snapshot, so no price trends over time
- Tamil Nadu has the most markets reporting, so overall figures lean towards it
- Some units may still be inconsistent across markets

## Tools
Power BI Desktop, Power Query, DAX
