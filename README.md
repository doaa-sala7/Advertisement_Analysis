# Advertisement_Analysis
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
•	product group: The product group the article belongs to
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
•	The data has unbalanced labels, the customer who didn't buy is a major class in the data
•	The distribution of promo1 is low for taking media advertisement
•	 The distribution of promo2 is low for taking events


##	Insights
•	Major country: the customer's major country is Germany and France is the lowest
•	Major product: The major product is shoes
•	Major product category: Training
•	Article Style: Slim is the major
•	Target gender: The main target gender of the article is women
•	Main size: The main size in the article is (xxs, xs, s, m, l ,xl, xxl ) 
•	buying the article or not all most the same in all articles id
•	regular_price and current price have correlation = 0.84 so dropped  regular_price
 

##	Data preprocessing
•	Convert the 3 columns of RGB for the main and second color to color code which gets 
•	Apply Normalization (StandardScaler)
•	Apply one-hot encoding for categorical features
•	Split Data to 80% train and 20% test
•	Resample unbalanced data by randomly

##	Modelling
•	Using a Random Forest Classifier to fit the data

