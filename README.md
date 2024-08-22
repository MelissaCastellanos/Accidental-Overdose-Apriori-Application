# Accidental Overdose Drug Relationships
In the following project, the Apriori algorithm was used to determine the association rules in an accidental overdose dataset. Finding these association rules helps define the relationship between items in a dataset, in this case, different drugs involved in an accidental overdose. 

The Apriori algorithm first identifies frequent itemsets which are combinations of drugs that appear together in overdose cases over a specific threshold. It begins by scanning the dataset to find individual drugs (1-itemsets) that meet the minimum support threshold. Then, it iteratively combines these frequent 1-itemsets to form larger itemsets, ensuring that only those itemsets that meet the support threshold are considered. This continues until no itemsets can be found. 

![Apriori Flow Example](https://iq.opengenus.org/content/images/2020/01/apriori-example.png)

The algorithm then generates association rules from these itemsets. Each rule's strength is evaluated using confidence and lift. Confidence measures the likelihood that Drug B is present given that Drug A is present, while lift assesses the strength of the association compared to what would be expected by chance. 

By analyzing these rules, we can uncover patterns in drug co-occurrence that may be critical for understanding and preventing accidental overdoses.  



## Conclusions
### TOP 10 RULES OVERALL
#| Antecedent             | Consequent | Support | Confidence | Lift   
-| ---------------------- | ---------- | ------- | ---------- | -----
11| (Heroin, Alcohol)      | (Fentanyl) | 0.0550  | 0.4667     | 0.8312
12| (Heroin, Cocaine)      | (Fentanyl) | 0.0733  | 0.6250     | 1.0963
13| (Acetyl Fentanyl, Alcohol) | (Fentanyl) | 0.0460 | 0.8514     | 1.5115
14| (Acetyl Fentanyl)      | (Alcohol)  | 0.0460  | 0.5000     | 0.9181
15| (Acetyl Fentanyl, Cocaine) | (Fentanyl) | 0.0388 | 0.7250     | 1.2913
16| (Para-Fluorofentanyl, Alcohol) | (Fentanyl) | 0.0286 | 0.7143 | 1.2781
17| (Para-Fluorofentanyl, Cocaine) | (Fentanyl) | 0.0352 | 0.6667 | 1.2154
18| (Alcohol, Heroin)      | (Cocaine)  | 0.0510  | 0.4800     | 1.1388
19| (Fentanyl, Heroin)     | (Cocaine)  | 0.0531  | 0.4240     | 0.9805
20| (Cocaine, Fentanyl)    | (Heroin)   | 0.0716  | 0.4650     | 0.9914  

The selection of the best rules was based primarily on their lift, confidence, and support values. I prioritized lift first, as it incorporates both confidence and the overall dataset, making it a more comprehensive measure of rule strength. Thus, I gave lift more weight than confidence and support. For the second criterion, I focused on rules with a confidence value exceeding 0.60. This level of confidence, combined with a high lift, indicated rules that were both accurate individually and within the broader dataset. High confidence and lift together highlighted rules of significant interest. Finally, I considered support, but only rules with support values greater than 0.05 were included. Support was the baseline for rule consideration, setting the stage for evaluating confidence and lift.


 
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
