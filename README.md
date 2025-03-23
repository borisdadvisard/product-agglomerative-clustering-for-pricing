# product-agglomerative-clustering-for-pricing
AGGLOMERATIVE CLUSTERING FOR PRICING APPLICATIONS
###### Unsupervised agglomerative hierarchical clustering classification algorithm used for pricing applications


--------------------------
Business Context:  A major player in electronic part distribution based in the US uses pricing and sales-optimising solutions to improve financial performance. They sell hundreds of thousands of semiconductor-based electronic components (SKUs) and struggle with data consistency and dynamic price optimisation. I engaged with them to design, train, configure and deploy multiple specialised ML models feeding off of their products, customers, and sales historical data. Once combined, these models obtain good performance and accuracy results in predicting a reliable, profit-maximising price for each SKU with a high market adoption score. 

--------------------------
Machine Learning techniques:

1/ An unsupervised agglomerative hierarchical clustering classification algorithm is used to group individual products together based on similarity. I feed the distance metric with both categorical and numerical features of the products (product characteristics, product sales statistics). After several experimentations, the ward variance minimization method was selected against other simpler methods. The distance threshold parameter has been exposed to the user via a slider on the front-end interface. See Jupyter notebook for details.*
	
	*Note: Due to the confidential nature of this project, I provide a simplified and anonymised Jupyter notebook to give you a sense of the work I've produced. This notebook focuses solely on the training phase of the ML Lifecycle.
	
2/ A supervised regression algorithm based on decision trees is then used to obtain relevant initial market prices for each individual product in comparable micro-segments (not shown).
	
3/ A supervised Bayesian logistic regression algorithm is used to predict customer willingness-to-pay/price sensitivity and solve an optimisation problem under constraints (on IBM CPLEX solver) to find profitable recommended price changes (increase or decrease). Not shown.

--------------------------
Batch Inference Results:
After training, around 200k products have been grouped into a few thousand groups based on their similarity regarding sales patterns. Each black mark represents an SKU, and the coloured segments represent the hierarchical groupings obtained by the ML algorithm based on the distance metrics in the vector space.

![Image sans titre](https://github.com/user-attachments/assets/a1211b0f-8ce3-483d-b543-35bc51f81318)

Legend: X axis: Product_Id, Y axis: Distance metric 


--------------------------
Key Learnings: 
	
 - A/ Product groupings change every time you retrain the model. Retraining the model can lead to price jumps or segment price instability. Retrain the model only a couple of times a year and communicate the change to your user base.
	
 - B/ 80-20 rule: Fine-tuning and improving the model by an additional 10% takes as long as getting the initial 80% accomplished.
	
 - C/ Performance metrics: review model health and performance metrics for drift often to ensure the model still perform well post-deployment. 


