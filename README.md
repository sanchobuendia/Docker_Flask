# Docker + Flask

This tutorial show as create a flask api, put it in container and deploy on GCP.

Firt of all, it is strongly recommended to create a virtual environment. I use MacOS and to crate the virtual environment you can follow tha next staeps 

create a new folder

mkdir docker_flask_venv

inside the docker_flask_venv folder

virtualenv venv

and active the virtual environment 

source venv/bin/activate

## Flask api
The api.py file is a flask script that makes a request on yahoo finance. In the request on Yahoo Finance you set three parameters:

* tickers: stocks that will be returned in the request.
* interval: Valid intervals: 1m,2m,5m,15m,30m,60m,90m,1h,1d,5d,1wk,1mo,3mo. Intraday data cannot extend last 60 days.
* start: start date of the price time series that yahoo finance will return.
* end: and date of the price time series that yahoo finance will return.

yf.download(tickers, interval = str(freq_time), start=str(init_date), end= str(end_date)) 

The api return a json with the correlation values among the 
