# Project Design Writeup


### Project Problem and Hypothesis
* The goal of the project is to use data obtained from January 2015 to June 2016 regarding the proxy vote information for activist investors to classify the types of votes and actions taken at a board meeting - e.g. DIRECTOR_ELECTION, ENVIRONMENTAL_ACTION, STOCK_SPLIT, etc.
* This is a text analysis classification problem. The study will need to analyze labels created by different pension funds as well as other attributes such as country of domicile and company name to classify the type of vote taken.
* The classification and standardization of the different vote types among major activist investors (pension funds and hedge funds) will help with creating time series of voting records for further data analysis to both predict how an activist will vote and how votes change over time.
* While the region, language, and some standard factors might play a role, the text label assigned in unstandardized records will most likely serve as the best factor through which to classify the model.

### Datasets
* There are two main datasets: one is a large Excel spreadsheet maintained manually by an analyst at Bloomberg. The other is voting history disclosed by CalPERS (California Public Employees Retirement System), which was scraped by a proprietary webcrawling system from CalPERS.ca.gov. 
* It will be possilbe to obtain other data from other publically disclosed records for pension funds and the like via further webcrawling using the proprietary webcrawling system.

### Domain knowledge
* I currently do not have a large amount of experience dealing with Activist Investor data, but I do have knowledge of internal databases and storing of related types of finanical information. I will be working with a counterpart who has extensive domain knowledge of proxy voting systems. 
* My knowledge of internal webcrawling systems, internal proprietary databases, and ETL processes will add with data collection and aggregation, data preprocessiong, and storage upon completion of the classification. 
* My counterpart for this project got hired for the purpose of building out this product. His extensive knowledge will help guide the project. There are no benchmarks as this project has not been attempted before, but the vision for aggregating proxy voting data and selling as a new product to clients has been marked to teams with in the department.

### Project Concerns
* The first assumption is that the proxy voting records publically disclosed by  various pension funds and sources will have a some level of congruency. This breaks down however when the votes are disclosed for companies that reside outside of the US. For instance, if an activist investor has a lot of French holdings and votes in French board meetings, the French board meetings might have a different system of rules around voting that for which my model fails to account.
* Another concern is that the set of data collected might have some inconsitencies due to the manual data capture and human errors. 
* I am also concerned about how I will perform the text analysis on the labels. The labels are not large paragraphs, but instead short sentences and phrases. I do not know if the best method is to use term-frequency and inverse document frequency or to just use simple count vectorization when adding factors to my model.
* Project Caveats:
	* The project requires obtianing data from websites that do not have an API. A webcrawler must be used. Another bulk of the data was obtained by manual entry. 
	* There does not yet exist a good set of training data
	* Training data will have to be generated manually by myself and a few counterparts 
* Project Risks:
	* Some data might be incorrect due to human error when entering
	* Creating a model that incorrectly labels the types of voting when new proxy votes come in could lead to data inconsistencies that would be dentrimental to client relations. 

### Outcomes
* The outcome should be a model that can accurately tag the type of vote based on a set of factors such as the vote descrition, language, origin of disclosure, country, vote size, etc as new we discover new datasets.
* The output should be similar to the input but instead have an extra label that classifys/buckets the proxy vote into a predefined category. This is the expectation of the target audience as well.
* I expect that the label description and country of domicile in which the company held the boarding meeting will be enough to produce highly accurate results.
* Depending on the efficacy the model could be as simple as a Naive Bayes classifier or more complicated by using a Support Vector Machine or Random Forest. 
* The model should correctly predict the classification of a proxy vote aver 95% of the time. Anything less would create large inconsistencies, which would be unacceptable to release to clients.
* If this project is a bust, I will move to work on another project which involves filtering out non-actionable work items. This is a well documented case of spam classification for which I have limitless clean data. 

