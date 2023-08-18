# Advertisement_result
##	Data understanding

•	country: Country name
•	article: 6-digit article number, as the unique identifier of an article
•	sales: total number of units sold in the respective retail week
•	regular_price: recommended retail price of the article
•	current_price: current selling price (weighted average over the week)
•	ratio: price ratio as current_price/regular_price, such that price discount is 1-ratio
•	retail week: start date of the retail week
•	promo1: an indicator for media advertisement, taking 1 in weeks of activation and 0 otherwise
•	promo2: an indicator for store events, taking 1 in weeks with events and 0 otherwise
•	customer_id: customer unique identifier, one id per customer
•	product group: product group the article belongs to
•	category: product category the article belongs to
•	cost: total costs of the article (assumed to be fixed over time)
•	style: description of article design
•	sizes: size range in which the article is available
•	gender: gender of the target consumer of the article
•	rgb_main_color: intensity of the red (r), green (g), and blue (b) primaries of the article‘s main color, taking values [0,250]
•	rgb_sec_color: intensity of the red (r), green (g), and blue (b) primaries of the article‘s secondary color, taking values [0,250]

•	label: advertisement result after offering/sending/presenting the offer to the customer. 0 means the customer did not buy and 1 means the customer did buy.  

##	EDA
•	Drop duplicates and non-important features (article, customer_id)
•	No null in data
•	outliers: no outliers in numerical data.
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/11b0308c-7124-4745-911b-6e6e06218690)

•	The shown outliers in graphs of sales, and prices, it's logical for this problem and shouldn’t consider outliers  
•	The data has unbalanced labels, the customer who didn't buy is a major class in the data
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/adb7f457-aa8a-4a2d-972f-50155807ccff)

•	The distribution of promo1 is low for taking media advertisement ![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/c5dee28c-546e-4193-9156-d7453cdec011)

•	 The distribution of promo2 is low for taking events![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/5c042d39-eee8-4b78-89db-bdc45aba5158)




##	Insights
•	Major country: the customer's major country is Germany and France is the lowest
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/e3a218d1-4f4a-43b4-b16d-54eb195a656d)

•	Major product: the major product is shoes
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/f162f084-9208-4a7a-ab9e-18c28a6298ac)

•	Major product category: Training
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/df9af7b5-f7cd-4796-bd69-534f1c3de3bb)

•	article Style: slim is the major
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/a51f41df-edab-408a-8ab2-d8b3e3eb058e)

•	target gender: main target gender of the article is women
![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/50eb87b1-a335-443c-b383-ee38d61de802)

•	main size: the main size in the article is (xxs, xs, s, m, l ,xl, xxl )
 ![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/138a2591-a7f2-4136-ba20-d0468cf6e820)

•	buying the article or not all most the same in all article id
 ![image](https://github.com/doaa-sala7/Advertisement_Result/assets/61519327/da67f6f5-035a-4f04-bd70-2eb44f451d7c)

•	regular_price and current price have correlation = 0.84 so dropped  regular_price
 

•	Data preprocessing
•	Convert the 3 columns of RGB for the main and second color to color code which gets 
•	Apply Normalization (StandardScaler)
•	Apply one-hot encoding for categorical features
•	Split Data to 80% train and 20% test
•	Resample unbalanced data by randomly
•	Modelling
•	Using Random Forest Classifier to fit the data
•	The training accuracy is 1.0
•	prediction accuracy

