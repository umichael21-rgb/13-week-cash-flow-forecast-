# 13-week-cash-flow-forecast-
This portfolio project is a simple, editable 13-week cash flow forecast for a fictional UK business. It demonstrates the foundations of short-term treasury analysis: forecasting cash receipts and payments, rolling opening and closing balances, monitoring a minimum cash buffer, and comparing actual cash movements with forecast. 

## Workbook structure
1. **Assumptions** — editable opening cash, forecast start date, weekly baseline receipts and payments, and minimum cash requirement. Yellow cells are inputs.
2. **13-Week Forecast** — weekly cash receipts and payments, total inflows/outflows, net cash flow, opening/closing balances and liquidity headroom. Weekly movement cells are editable; formula cells are blue.
3. **Dashboard** — headline liquidity measures and two charts. The dashboard is linked to the forecast and updates when forecast inputs change.
4. **Actual vs Forecast** — compares forecast inflows/outflows and closing balances with editable illustrative actuals. Replace the example actuals with real actual data in a real-world setting.

## What is a 13-week cash flow forecast?
A 13-week cash flow forecast estimates when money is expected to enter and leave a business over the next 13 weeks. It is a short-term liquidity tool: it focuses on cash timing and the ability to meet payments, rather than accounting profit.

Businesses often use 13 weeks because it gives a practical rolling view of roughly one quarter. It is long enough to identify upcoming pressure points, while short enough for weekly updates and discussions with operational teams.

### Key concepts in plain English
- **Cash inflows:** money expected to arrive, such as customer receipts or refunds.
- **Cash outflows:** money expected to leave, such as supplier invoices, payroll, rent and tax.
- **Opening cash:** the cash available at the start of a week.
- **Net cash flow:** total inflows minus total outflows for that week.
- **Closing cash:** opening cash plus net cash flow. The next week's opening cash is the previous week's closing cash.
- **Liquidity headroom:** closing cash less the minimum cash requirement. Positive headroom means the buffer is maintained; negative headroom means the forecast is below the required minimum.
- **Cash shortage monitoring:** identifying a potential shortfall early gives the business time to investigate timing, accelerate collections, defer non-critical spending where appropriate, or arrange funding with approval.

## Formula guide
The workbook deliberately uses basic, traceable Excel formulas:
- `=SUM(B10:B12)` — adds the three cash inflow lines for the week.
- `=SUM(B16:B21)` — adds the six cash outflow lines for the week.
- `=B13-B22` — calculates net cash flow (inflows less outflows).
- `=Assumptions!$B$5` — links Week 1 opening cash to the assumptions tab.
- `=B26` in the next week's opening balance — rolls forward the previous week's closing cash.
- `=B7+B24` — calculates the closing cash balance.
- `=B26-B27` — calculates liquidity headroom.
- `=IF(B28<0,"Below minimum","Within minimum")` — flags whether the cash buffer is breached.
- `=MIN(B26:N26)` — identifies the lowest weekly closing balance.
- `=Actual-Forecast` — calculates a variance in the Actual vs Forecast tab.

The workbook is set to recalculate when opened in Excel. All calculations are formulas, not typed-in calculated outputs. You can click a formula cell and inspect its formula in the formula bar.

## Where the information comes from in a real organisation
- **Opening cash:** bank statements, bank portal balances and cash position reports, reconciled for outstanding items.
- **Customer receipts:** accounts receivable ageing, invoice due dates, customer payment behaviour, collection forecasts and sales/credit-control updates.
- **Supplier payments:** accounts payable ageing, approved invoices, payment runs and agreed supplier terms.
- **Payroll:** payroll calendar and payroll team's confirmed payment totals.
- **Rent, utilities and operating expenses:** contracts, recurring payment schedules, purchase ledger and budget-owner input.
- **Tax:** VAT/PAYE/corporation tax calendars and information from the tax/finance team.
- **Actual movements:** bank statements and transaction reports, coded to the relevant cash flow categories.
- **Minimum cash requirement:** a management-approved liquidity policy or operating buffer.

## How a Treasury Analyst uses the model
A Treasury Analyst reviews the forecast against bank balances and expected receipts/payments, checks assumptions with teams, identifies weeks where cash may fall below the required buffer, and communicates the timing and size of any pressure. The analyst can then support decisions such as following up overdue customer balances, reviewing payment timing with Accounts Payable, or escalating a potential funding requirement. Decisions to delay payments or arrange finance must follow company policy and approval processes.

## Model limitations and sensible next steps
This is an intentionally introductory model. It uses simple weekly input lines and does not include complex debt facilities, interest, foreign exchange, scenario engines, automated bank feeds or working-capital sub-ledgers. In a live business, the forecast should be refreshed regularly and reconciled to actual bank activity.

## Excel skills demonstrated
- Cell references across worksheets
- `SUM`, `IF`, `MIN` and basic arithmetic
- Rolling balances and formula copying across 13 periods
- GBP number formatting
- Input/formula cell colour conventions
- Conditional formatting for liquidity thresholds
- Basic column and line charts
- Forecast-versus-actual variance analysis
```

## Build validation (illustrative base case)
The 13 weekly periods were independently recalculated from the editable sample inputs to check the rolling cash logic. The base-case figures are:
- Total forecast inflows: £1,342,900
- Total forecast outflows: £1,333,900
- Final forecast closing cash: £259,000
- Lowest weekly closing cash: £241,700
- Minimum cash requirement: £75,000
- Lowest-point liquidity headroom: £166,700

The Excel file contains formulas for these calculations and is configured to recalculate when opened in Excel. The validation above is an independent arithmetic check of the sample inputs, not a claim that Excel's formula engine was run inside this environment.
