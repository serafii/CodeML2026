# Collection Equinoxe - 2026 Rent Forecast

This project estimates Collection Equinoxe's rent growth for 2026.

## Main result

- Central forecast: **2.46%**
- Planning range: **1.09% to 3.82%**
- Backtest mean absolute error: **1.36 percentage points**

The planning range is the central forecast plus or minus the backtest error. It is not a confidence interval.

## Method

- Match the same apartment across consecutive leases with `sPropCode + sUnitCode`.
- Keep lease gaps between 0.5 and 2.5 years.
- Measure annualized growth using effective rent, including concessions.
- Review renewals and tenant turnovers separately.
- Review Quebec and Ontario separately.
- Compare the internal results with CMHC and Statistics Canada data.
- Forecast 2026 with the mean of the previous three yearly results.

The method is intentionally simple so it can be checked and explained easily.

## Files

- `rent_forecasting.ipynb`: main analysis and forecast
- `Collection_Equinoxe_2026_Forecast.pptx`: jury presentation
- `starter.ipynb`: official challenge starter notebook
- `external_data/`: public CMHC Montreal and Ottawa workbooks
- `data/`: local challenge data

## Run the notebook

Install the required packages:

```bash
pip install pandas==3.0.6 numpy==2.5.3 matplotlib==3.11.2 openpyxl==3.1.5 jupyter
```

Then open `rent_forecasting.ipynb` and run all cells in order.

Tested with Python 3.12.6. No trained model is included because the forecast uses a simple three-year trailing mean.

## Data

The four CRM CSV files in `data/` are confidential and are not committed. Historical CMHC reports under`externall_data/` have also not been committed.

## Ontario note

The Met was first occupied in 2022. It is therefore generally exempt from Ontario's rent increase guideline, subject to confirmation with occupancy records. Ontario is still reviewed separately because its rules and market conditions differ from Quebec.

## External sources

- Canada Mortgage and Housing Corporation rental market tables
- Statistics Canada rent CPI, Table 18-10-0005-01
- Tribunal administratif du logement guidance
- Government of Ontario residential rent increase guidance

Claude and ChatGPT were used for drafting and code review. The calculations and conclusions were checked against the supplied data and cited public sources.
