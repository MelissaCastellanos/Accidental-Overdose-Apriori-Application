# Accidental Overdose Drug Relationships
In the following project, the Apriori algorithm was used to determine the association rules in an accidental overdose dataset. Finding the association rules of a dataset helps define relationships between items in the dataset, in this case, different drugs involved in an accidental overdose. 

The Apriori algorithm first identifies frequent itemsets. In this case frequent itemsets are combinations of drugs that appear together in overdose cases over a specific threshold. It begins by scanning the dataset to find individual drugs (1-itemsets) that meet the minimum support threshold. Then, it combines these frequent 1-itemsets to form larger itemsets until no itemsets can be found. This ensures that only those itemsets that meet the support threshold are considered.

![Apriori Flow Example](https://iq.opengenus.org/content/images/2020/01/apriori-example.png)

The algorithm then generates association rules from these itemsets. Each rule's strength is evaluated using confidence and lift. Confidence measures the likelihood that Drug B is present given that Drug A is present, while lift assesses the strength of the association compared to what would be expected by chance. 

By analyzing these rules, we can uncover patterns in drug co-occurrence that may be critical for understanding and preventing accidental overdoses.  



## Conclusions
To select the top overall association rules three measures were considered: support, confidence, and lift. Support was used as a baseline rule for consideration. Only rules having a support value greater than 0.05 were considered significant (i.e. only itemsets that appeared with a frequency of 0.05 were considered "frequent enough" to form an association). This set the stage for evaluating the confidence and lift of each rule. Confidence was used to measure how frequently drugs (itemsets) appeared together. The higher the confidence the more likely a consequent was to occur given the antecedent. For example, Rule 1, with a confidence of 0.6250, indicated fentanyl had a 62.50% chance of appearing if both heroin and cocaine were present. Lift, on the other hand, was used to determine the strength of each rule. A higher lift (>1) indicated a strong positive relationship, while a low lift (<1) indicated a strong negative relationship. For example, Rule 2, with a lift of 1.1388, suggests that the relationship between alcohol, heroin, and cocaine is greater than what we expect from sheer coincidence. In essence, the processes filtered out rules with low support, selected those with high confidence, and ranked the remaining rules based on lift to identify which were more significant. 

### TOP 5 RULES OVERALL
#| Antecedent             | Consequent | Support | Confidence | Lift   
-| ---------------------- | ---------- | ------- | ---------- | -----
1| (Heroin, Cocaine)      | (Fentanyl) | 0.0733  | 0.6250     | 1.0963
2| (Alcohol, Heroin)      | (Cocaine)  | 0.0510  | 0.4800     | 1.1388
3| (Heroin, Alcohol)      | (Fentanyl) | 0.0550  | 0.4667     | 0.8312
4| (Fentanyl, Heroin)     | (Cocaine)  | 0.0531  | 0.4240     | 0.9805
5| (Cocaine, Fentanyl)    | (Heroin)   | 0.0716  | 0.4650     | 0.9914  


## Data Information
**Source:** Allegheny County Fatal Accidental Overdoses [Link to Dataset](https://catalog.data.gov/dataset/allegheny-county-fatal-accidental-overdoses)  

**Date:** May 14, 2023  

**Description:** Dataset is composed of closed-case accidental overdoses in Allegheny County. Attributes include age, gender, race, drugs present, zip code of incident, and zip code of residence. Originally collected through the medical examiner office.  

**Original Usage:** Intended for public access

**Size:** Baskets: 7024 | Items: Up to 10 different drugs found at the time of death. Up to 10 items per basket.  


  
## References 
[Data Cleaning](https://adamtheautomator.com/data-cleaning-python/)  
[Market Basket Analysis Example](https://github.com/ashishpatel26/Market-Basket-Analysis)  
[Apriori Algorithm Geeks for Geeks](https://www.geeksforgeeks.org/implementing-apriori-algorithm-in-python/)  
[Apriori Algorithm Implementation](https://hands-on.cloud/apriori-algorithm-python-implementation/)
