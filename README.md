# Docker + Flask

This tutorial show as create a flask api, put it in container and deploy on GCP.

Firt of all, I am using poetry here. To install dependencies

poetry install


## Flask api
The api.py file is a flask script that makes a request on yahoo finance. In the request on Yahoo Finance you set three parameters:

* tickers: stocks that will be returned in the request.
* interval: Valid intervals: 1m,2m,5m,15m,30m,60m,90m,1h,1d,5d,1wk,1mo,3mo. Intraday data cannot extend last 60 days.
* start: start date of the price time series that yahoo finance will return.
* end: and date of the price time series that yahoo finance will return.

yf.download(tickers, interval = str(freq_time), start=str(init_date), end= str(end_date)) 

The api return a json with the correlation values among the selected stocks.

![image](/images/docker_flask_json.png)

To run the api script locally it is recommended to use a virtual environment as explained earlier. when the environment is active go to the application folder and run.

poetry run python api.py

![image](/images/terminal1.png)

To make a request in the api it is necessary to open a browser and enter with an url like this

http://127.0.0.1:8080/returnjson?init_date=2022-01-01&end_date=2022-01-30&freq_time=1h&index=Close&tickers=SPY&tickers=AAPL&tickers=MMM

the url has fixed parts, such as:

**http://127.0.0.1:8080/returnjson?init_date=**

**&end_date=**

**&freq_time=**

**&index=**

**&tickers=**

the user needs to choose the parameter values.

