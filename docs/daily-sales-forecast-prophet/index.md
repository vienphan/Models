# Daily Sales Forecast with Prophet  
*A practical forecasting example for retail decision-making (Vietnam calendar, with Tết effect)*

## Why this project exists

In retail, we usually don’t lack data.  
What we often lack is a **clear baseline of future daily sales** to support decisions on inventory, staffing, and cash-flow—especially around major events like **Tết**.

This page tells the story end-to-end:
- what the input data looks like  
- what the model does (in plain language)  
- what outputs it produces (embedded below)

---

## What question does this model answer?

> “Based on past daily sales and the retail calendar, what is a reasonable expectation for future daily sales?”

This is a **baseline forecast** (a reference line).  
It helps you separate:
- underlying trend (up/down)
- weekly shopping rhythm (weekday vs weekend)
- major calendar disruptions (especially **Tết**)

It does **not** guess promotions, price wars, or competitor moves.

---

## Input data

The input is intentionally simple:
- **Date** (daily)
- **Total sales value** of that day

### Sample data preview (first 14 rows)

| Date (ds) | Sales (y) |
| --- | --- |
| 2019-01-01 | 8,833,506 |
| 2019-01-02 | 6,458,954 |
| 2019-01-03 | 6,990,356 |
| 2019-01-04 | 7,435,801 |
| 2019-01-05 | 8,435,844 |
| 2019-01-06 | 11,360,416 |
| 2019-01-07 | 9,885,382 |
| 2019-01-08 | 8,118,239 |
| 2019-01-09 | 7,431,196 |
| 2019-01-10 | 7,159,485 |
| 2019-01-11 | 8,268,896 |
| 2019-01-12 | 9,703,927 |
| 2019-01-13 | 11,468,597 |
| 2019-01-14 | 10,111,542 |

*(Tip: you can keep a full downloadable CSV in your repo too, but the preview above is enough for a non-technical reader.)*

---

## How the model works (plain language)

1. **Learn from your history**  
   It learns trend and repeatable patterns from daily sales (not from assumptions).

2. **Capture weekly rhythm**  
   Retail usually has a strong weekday/weekend profile. The model learns that automatically.

3. **Embed Vietnam holidays (with Tết emphasis)**  
   Vietnam retail is not “normal seasonality” around Tết.  
   This model explicitly marks the Tết period so the forecast reflects the real demand distortion.

4. **Produce a future baseline forecast**  
   The output is a future daily curve plus an uncertainty band—useful for planning ranges.

---

## Output 1 — Interactive Daily Forecast (embedded)

This is the main “forecast view”: past actuals + future baseline + uncertainty.

<div style="margin:16px 0; border:1px solid #e5e7eb; border-radius:14px; overflow:hidden;">
  <iframe
    src="reports/forecast_interactive.html"
    width="100%"
    height="720"
    style="border:0;"
    loading="lazy"
  ></iframe>
</div>

---

## Output 2 — Monthly & Yearly Sales Analysis (embedded)

This view aggregates daily sales into month/year, making it easier for executives to read:
- seasonality by month
- year-on-year movement (where applicable)
- long-term direction

<div style="margin:16px 0; border:1px solid #e5e7eb; border-radius:14px; overflow:hidden;">
  <iframe
    src="reports/sales_analysis_combined.html"
    width="100%"
    height="820"
    style="border:0;"
    loading="lazy"
  ></iframe>
</div>

---

## How a retail leader should interpret this

When you scroll the forecast, ask:
- Does the **trend direction** match what we feel in stores and online?
- Is the **weekly rhythm** realistic?
- Does the **Tết period** show an abnormal shape (as it should)?
- Where do we usually deviate from baseline—and why (promo, price, supply constraints, competitor)?

That deviation is where commercial strategy matters most.  
The forecast gives you the baseline so decisions are made on top of a stable reference point.

---

## What this model is best used for

- inventory readiness and buffer planning  
- staffing and delivery capacity planning  
- target setting and gap-to-plan discussions  
- cash-flow timing and operational preparedness  

---

## What this model is not

To avoid misunderstanding, this model does not:
- “predict promotions”
- “know competitor actions”
- replace commercial judgment

It is a **decision support baseline**, built to be simple, explainable, and reusable.
