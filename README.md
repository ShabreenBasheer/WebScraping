# WebScraping

Estimize is an open-source platform that provides financial metrics for various companies(ticker). The various metrics are revenue and EPS. The website also provides estimates from multiple analysts for the same. <br>
 
The data from the website was obtained using the web scraping technique, specifically python implementation of automated web scrapping package Selenium was utilized. Initially, a list of 50 different tickers was imported in python. Seven functions were created to collect the data for these 50 tickers. Within each of these functions, collected data were appended to lists and different lists were zipped together. Zip-created tuples were then exported to an excel sheet. <br>

# Function Description:
# 1) getCompanyInformation	
    Input: ticker List.
    Gets basic Company information - ticker, name, sector, industry, number of followers, number of analysts;
    Appends all values to a list 
# 2)	getEPSInformation	
    Input: ticker.
    Gets EPS information of the ticker - ticker, quarter, reported earning, estimize consensus, estimize mean, Wall Street consensus; Appends all the collected data to a list.
# 3)	getEPSAnalystsEstimation	
    Input: ticker, quarter List.
    Gets all EPS estimations of analysts - ticker, quarter, analysts display name, analysts secondary name, analyst EPS estimations; Appends all the collected data to a list.
# 4)	get_Analyst_Information	
    Gets analysts basic information - analyst name, roles, joining date, analyst confidence rate, error rate, accuracy percentile, points, points per estimates, stocks, pending estimates; 
    Appends all collected data to a list. 
# 5)	get_Stocks_Covered	
    Input: Analyst name
    Gets information on stocks covered by the analysts – analyst name, ticker, report, quarter, points, points per estimates, error rate, accuracy; Appends all collected data to a list.
# 6)	get_Pending_Estimates	
    Input: Analyst name
    Gets information on pending estimates of analysts – analyst name, ticker, report, quarter, published, EPS, revenue; Appends all collected data to a list.
# 7)	get_Scored_Estimates	
    Input: Analyst name
    Gets information on scored estimates of analysts – analyst name, ticker, report, quarter, rank, EPS, revenue, total points; Appends all collected data to a list

# Data Cleaning:
    Replaced N/A and empty string columns with NULL in the exported dataset.

# Database Creation:
    Step 1: Created a Database in MySQL workbench named MSA_ESTIMIZE
    Step 2: Created tables in database MSA_ESTIMIZE. Created the following tables in the database
          1.	COMPANYINFORMATION
          2.	ANALYSTINFORMATION
          3.	EPSINFORMATION
          4.	EPSANALYSTESTIMATION
          5.	STOCKSCOVERED
          6.	PENDINGESTIMATION
          7.	SCOREDESTIMATION
    Step 3: Insert the values as obtained in the excel workbook into the tables created using insert statements.

