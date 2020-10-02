# main
information about the project


to run you must need to:


## Back End

###  user data store
    
 - **link**
	 - https://github.com/Primera-Generacion-AHK-Sistemas/SpringBootAuth0API
	 - heroku deployment: https://spring-boot-auth0-api.herokuapp.com
 - **to run**
	 - run app.class
 - **information**
	 - with the credential of auth0 save user data in the **postgresql** database 
	https://www.elephantsql.com/

###  historic data of actions
    
 - **link**
	 - https://github.com/Primera-Generacion-AHK-Sistemas/flask_yahoo_finance
 - **to run**
	 - python -m pip install -r requirements.txt
            python app.py
 - **information**
	 - access to historic prices of each company
            
	    Last price:
	    https://flask-yahoo-fin.herokuapp.com/api/live-price?ticker=MSFT
	    
	    List of prices between start_date & end_date
	    https://flask-yahoo-fin.herokuapp.com/api/price-between?ticker=MSFT&start_date=YYYY/MM/DD&end_date=YYYY/MM/DD
	    
	    List of prices between today - 365 days
	    https://flask-yahoo-fin.herokuapp.com/api/year-today-price?ticker=MSFT
	    

###  technical analysis
  - **link**
  	  - https://github.com/Primera-Generacion-AHK-Sistemas/tradingDataAndAnalisys



###  technical analysis only data (for testing purposes and configure graphs)
  - **link**
	  - https://github.com/Primera-Generacion-AHK-Sistemas/FastApi-Technical-Analysys-for-Shares
 - **demo**
  	  - https://pythonapiar.herokuapp.com/docs

 - **to run**
	 - ```git clone https://github.com/Primera-Generacion-AHK-Sistemas/FastApi-Technical-Analysys-for-Shares```
	 - ```cd FastApi-Technical-Analysys-for-Shares```
	 - ``` python3 -m pip install -r requirements.txt```
	 -  ``` python3 uvicorn fastapp:app --reload --port 5000```
 - **information**
	 - made in FastApi ajusted to use with apexcharts series
	 - to see more information about the api
		 - http://localhost:5000/docs
	 -to see the diferent indicators and tickers
		 - http://localhost:5000/data
	 - to request some indicator data about a ticker (in this case request the atx indicator of Apple)
		 - http://localhost:5000/api?ticker=AAPL&indicator=atx
## Front End

### webapp angular and auth0 
    
 - **link**
	 - https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard
 - **demo**
	 - https://argenshares.herokuapp.com (the domain of heroku can be changed )
 - **to run**
	 - git clone https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard
	 - cd AngularArgonDashboard
	 - npm install
	 - ng serve
 - **information**
	 - get credential from auth0 to connect with spring boot
	 - display graphs from the data of python apis (at the moment, in a future from spring boot)
     
     
## Infraestructure

### Networking

 - **CloudFlare**
	 - https://www.cloudflare.com/plans/
	 - https://support.cloudflare.com/hc/en-us/articles/200168256-Understand-Cloudflare-Caching-Level
	 - https://support.cloudflare.com/hc/en-us/articles/360021806811-Getting-Started-with-Cloudflare-Caching
     
### Domains
 - **Nicar**
   - https://nic.ar/
     - dot AR domain 
       - price : 540.00 AR$
     - dot COM dot AR domain 
       - price : 270.00 AR$
     - dot NET dot AR domain 
       - price : 270.00 AR$


### Cloud Services Providers
 - **Heroku**
   - for testing with limited capabilities
   - https://www.heroku.com/ 
 - **Azure**
   - App Service
     - https://azure.microsoft.com/en-us/pricing/details/app-service/windows/
   - API Service
     - https://azure.microsoft.com/en-us/pricing/details/api-management/
   - Containers
     - https://azure.microsoft.com/en-us/pricing/details/kubernetes-service/
   - Cost Calculator
     - https://azure.microsoft.com/en-us/pricing/calculator/
   - Mongo DB
     - https://www.mongodb.com/cloud/atlas

### user data store api info
![](Imagenes/RequestsSpringBoot.jpeg)
