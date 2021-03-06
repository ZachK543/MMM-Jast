# MMM-JaST - **J**ust **a**nother **S**tock **T**icker
This is just another stock ticker for [Magic Mirror](https://magicmirror.builders/).  
Click here for the Magic Mirror [Forum Thread](https://forum.magicmirror.builders/topic/12507/mmm-jast-just-another-stock-ticker)


## Features
- Multiple currencies
- Currency exchange support
- Vertical scrolling
- Horizontal scrolling
- Depot value growth summary

## Installing the Module
Navigate to the MagicMirror subfolder "modules" and execute the following command  
`git clone https://github.com/jalibu/MMM-Jast.git`

## Using the module
First, get your personal API Key for [Alphavantage here](https://www.alphavantage.co/support/#api-key)

To use this module, add it to the modules array in the `config/config.js` file:

### Sample
```javascript
{
	module: "MMM-Jast",
	position: "top_left",
	config: {
		updateIntervalInSeconds: 1800,
		fadeSpeedInSeconds: 3.5,
		stocks: [
		{ name: "BASF", symbol: "BAS.DE", quantity: 10 },
		{ name: "SAP", symbol: "SAP.DE", quantitiy: 15 },
		{ name: "Henkel", symbol: "HEN3.DE" },
		{ name: "Alibaba", symbol: "BABA", tradeCurrency: "USD", displayCurrency: "EUR" },
		],
		defaultCurrency: "EUR",
		apiKey: "<Insert your API Key>",
		scroll: "<none, vertical, horizontal>",
		maxWidth: "100%",
		showDepotGrowth: true
	}
}
```
### Options
| Field    					| Description 																	| Default 				|
| -------- 					| -------- 																		| -------- 				|
| updateIntervalInSeconds   | (Integer) Interval to refresh stock data from server   						| 1800 (30 minutes)   	|
| fadeSpeedInSeconds		| (Integer) Animation speed for ticker											| 3.5   				|
| stocks					| (Array<Stock>) Array of stocks to be displayed								| Sample set			|
| defaultCurrency			| (String) Default currency to display stock values								| "EUR"   				|
| apiKey					| (String) Alphavantage API key													| undefined				|
| scroll					| (String) Animation direction for ticker. Values: none, vertical or horizontal	| "vertical"  			|
| maxWitdth					| (String) CSS style to limit ticker width										| "100%"   				|
| showDepotGrowth			| (Boolean) Show depot value growth summary in ticker							| false   				|

### Stock Object
| Field    			| Description 														| Example 	|
| -------- 			| -------- 															| -------- 	|
| name   			| (String) Stock's display name   									| "Alibaba"	|
| symbol   			| (String) Stock's symbol/key   									| "BABA"   	|
| tradeCurrency   	| (String) Optional: If is not the same as defaultCurrency 			| "USD"   	|
| displayCurrency   | (String) Optional: If it should not be displayed in tradeCurrency	| "EUR"   	|
| quantity   		| (Integer) Optional: To calculate depotGrowth   					| 500   	|
