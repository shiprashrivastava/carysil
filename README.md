Carysil-PBI
We Are Looking For Dashboard where we can check our Financial Performance and various financial metrics to judge our business.

Power Bi Report For carysil Project : <a href "https://github.com/shiprashrivastava/carysil/blob/main/shipra.pbix"
Data : <a href "https://github.com/shiprashrivastava/carysil/blob/main/Copy%20of%20Formula%20For%20Dim1.xlsx"
Power Bi Report PDF: <a href "https://github.com/bhargavmehta93/Carysil-PBI/blob/main/Carysil%20Project%20PDF.pdf"
Power Bi Report Screenshort: <a href "https://github.com/shiprashrivastava/carysil/tree/main/Screenshots"
Carysil Financial Analysis
Understanding The Business Understand the Data First To Understand the Business in Better Way….Excel

# Data Preparation
Data Arrangement : Dimension & Fact able • P&L=INDEX('Profit & Loss'!$A$4:$L$20,MATCH('P&L Fact'!C2,'Profit & Loss'!$A$4:$A$20,0),MATCH('P&L Fact'!E2,'Profit & Loss'!$A$4:$L$4,0)) • BS=INDEX('Balance Sheet'!$A$3:$L$36,MATCH('BS Fact'!E2,'Balance Sheet'!$A$3:$A$36,0),MATCH('BS Fact'!G2,'Balance Sheet'!$A$3:$L$3,0))
Data Modelling : Relationship Development for Insight
# Client Requirement
We Are Looking For Dashboard where we can check our Financial Performance and various financial metrics to judge our business

Financial Statement Data Arrangement
Financial Performance & Analysis
Ratio Analysis
# Financial Performance Analysis
Overall Sales, Gross, Profit, EBITDA, PAT
Growth YoY Change
Assets Distribution & Common Sizing of Balance Sheet
Profitability Flow
Sales Trend with Rev Change
Trend of Efficiency Metrics
Margin Analysis & Revenue Bifurcation
# Statement Analysis
P&L Statement
P&L Breakup
CAGR % with Trend
Target Sales Metrics
Comparison GP Vs PAT
Dept & Interest % of Sales
Cost Breakup
# Balance Sheet Visuals
Balance Sheet Visuals
Assets Breakup & Liabilities Breakup
Balance Sheet Health
Balance Sheet Deep Insight
# Cash Flow Statement Analysis
CFS Visuals
CFO/EBITDA Trend
Free Cash Flow Trend
Used Chart
• Slicer • Visual card • 100% Stacked Bar Chart • Funnel Chart • Line And Clustered Column Chart • Line Chart • Donut Chart • Matrix • Treemap Chart • Gauge Chart • Clustered Column Chart • Stacked Area Chart

DAX
# Profit & Loss
Target Revenue = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Sales")*1.15
Sales LY = CALCULATE([Sales], SAMEPERIODLASTYEAR(Date_Dim[Date].[Date]) )
Sales % = ([Sales]-[Sales LY])/ [Sales LY]
Sales = CALCULATE(SUM('P&L_Fct'[Values]),'P&L_Dim'[P&L_Main_Head]="Sales")
ROE % = [Actual Total PAT]/[Total Equity]
ROCE% = [EBIT]/([Total Equity]+[Total Debt])
Rev CAGR % = ([Ending Rev]/[Begining Rev])^(1/5) -1
PAT CAGR % = ([Ending PAT]/[Begining PAT])^(1/5)-1
PAT % = [Actual Total PAT]/[Sales]
No.of Share = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="No. Of Share")
Interest % = (CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Interest"))/[Sales]
Gross Profit = [Sales]-[Actual Total COGS]
GP % = [Gross Profit]/[Sales]
Finacial Levrage = [Total Assets]/[Total Equity]
EPS = [Actual Total PAT]/ [No.of Share]
Ending Rev = (CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Sales",Date_Dim[Year]=2024))
Ending PAT = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Net Profit +",Date_Dim[Year]=2024)
Ending EBITDA = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head] = "Operating Profit", Date_Dim[Year] = 2024)
EBITDA CAGR % = ([Ending EBITDA]/[Begining EBITDA])^(1/5)-1
EBITDA % = [Actual Total EBITDA]/[Sales]
EBIT = [Actual Total EBITDA]-[D&A]
Dep % = (CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Depreciation"))/[Sales]
D&A = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Depreciation")
BVPS = [Total Equity]/ [No.of Share]
Begining Rev = CALCULATE(SUM(BS_Fct[Value]), 'P&L_Fct'[P&L_Main_Head]="Sales",Date_Dim[Year]=2019)
Begining PAT = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Net Profit +",Date_Dim[Year]=2019)
Begining EBITDA = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head] = "Operating Profit", Date_Dim[Year] = 2019)
Actual Value_PY = CALCULATE(SUM('P&L_Fct'[Values]),SAMEPERIODLASTYEAR(Date_Dim[Date].[Date]))
Actual Value = CALCULATE(SUM('P&L_Fct'[Values])) 30 Actual Total PAT = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Net Profit +")
Actual Total EBITDA = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="Operating Profit")
Actual Total COGS = CALCULATE(SUM('P&L_Fct'[Values]), 'P&L_Fct'[P&L_Main_Head]="COGS")
% Change = DIVIDE(([Actual Value]-[Actual Value_PY]),ABS([Actual Value_PY]),0)
# Balance Sheet
Working Capital = [Trade Receivables]+[Inventories]-[Trade Payables]
Trade Receivables = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Node Head]="Trade receivables")
Trade Payables = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Node Head] = "Trade Payables")
Total Equity = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Group_Head] = "Equity")
Total Debt = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Node Head] = "Borrowings -")
Total Assets = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Node Head]="Total Assets")
Inventories = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Node Head]= "Inventories")
D/E = [Total Debt]/[Total Equity]
Current Ratio = [Current assets]/ [Current Liabilities]
Current Liabilities = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Group_Head] = "Current Liabilities")
Current assets = CALCULATE(SUM(BS_Fct[Value]), BS_Dim[BS_Group_Head] = "Current Assets")
Assets Turnover = [Sales]/[Total Assets]
# cash Flow
FCF = [CFO]+[CAPEX]
FCF = [CFO]+[CAPEX]
CFO = CALCULATE(SUM(CFS_Fct[Value]), CFS_Fct[CFS_Sub Head]="Cash from Operating Activity -")
CAPEX = CALCULATE(SUM(CFS_Fct[Value]), CFS_Fct[CFS_Sub Head]="Fixed assets purchased")
