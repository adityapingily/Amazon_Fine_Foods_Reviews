# Amazon_Fine_Foods_Reviews

A series of NLP projects using the Amazon Fine Food Reviews dataset. This repository is a work in progress. I will add projects as inspiration comes. 

## Project One: Predicting Review Helpfulness Using Macro-Level Text Summary Statistics  
  

I marked a review as helpful if the number of times customers rated it as helpful divided by the total number of times they gave it any rating (positive or negative) was greater than or equal to 90%. Due to fairly dramatic changes in the data over time, I restricted the analysis to the most recent year of data, 2012. The data can be found here: [https://snap.stanford.edu/data/web-FineFoods.html](https://snap.stanford.edu/data/web-FineFoods.html). About 22% of the reviews were helpful. 

### Summary and Motivation  

The goal of this project is to determine if a review's helpfulness can be predicted without using word specific features (i.e. bag of words and its derivatives). Instead I used macro-level text summary statistics such as:  

1. Number of Sentences
2. Number of Words
3. Readability 
4. Sentiment Metrics

The motivations are multi-fold: I am curious about the predictive power of macro-level text summary statistics and using word-specific features can make training, storing, and deploying predictive models more computationally intensive. 

Stepping back, the whole exercise of predicting review helpfulness is worthwhile because it can improve customer satisfaction. A major annoyance from on-line shopping is the product will not be as satisfying as it is advertised. Many shoppers depend on helpful reviews to avoid buyer's remorse. Therefore placing helpful reviews front and center for as many products as possible can improve the shopping experience, customer retention, and eventually profits. 

Traditionally on-line businesses solve this problem by allowing customers to rate the product reviews of other customers, then rank the reviews by their ratings. This can be insufficient for very popular products where potentially highly helpful reviews are never rated by customers because they are drowned out by unhelpful or moderately helpful reviews. Also, for new or niche products, some potentially highly useful reviews can go unrated because customer volume to the product page is too low. Predictive models can step in to identify potentially highly helpful reviews and help the web design team ensure that customers can easily find them.  

Now given the potential business benefit of a review helpfulness model, why not spend as much resources as needed to train, store, and deploy one? Every resource spent on one project is a resource not spent on another project, therefore it is important to be aware of options for intelligently trading off the resources invested in a project with the terminal quality of that project.  

### Results 

The preliminary analysis shows that a reasonably predictive model can be built without word specific features:    

The area under the curve of the ROC (AUC ROC) of the best models, k-nearest neighbors, bagged trees, and random forest, were 0.8, 0.8, and 0.81 respectively. While these models are not "highly predictive" (AUC ROC of 0.9+), this is a proof of concept.  


### Next Steps

Next I want to improve the model performance by experimenting with:

1. Different measures of text readability
2. Using sentence, as oppose to whole-review level, measures of sentiment
3. Use vector representations of words to capture semantic summaries of reviews
4. Formally addressing the moderate class imbalance problem using SMOTE, over/under sampling, and Tomek Link removal
5. Use topic modeling to identify topics that are highly predictive of review usefulness

