# Recommendation_Engines
Recommendation Engines Developed with LightFM

An E-Commerce company tailored towards customized apparel and products is doing well. However, the top five sellers for the company represent approximately 30% of all sales since January 2019. These five sellers generated about 2 million orders and most of those orders included the sale of a single item. To generate more revenue for sellers, and in turn, generate more revenue for the company, it makes sense to have a recommender engine that will help influence customers to increase their basket sizes by 1. If 10% of customers move from purchasing 1 item to 2 items, it could potentially mean an increase of $3.5MM for these sellers. This should make it easier to get sellers on board in implementing the recommendation engine. And once the recommendation engine is implemented, this translates to an increase in profit forthe company of over $1MM.

The recommendation engine will serve up products customers want without having to ask as well as serve up products customers did not know they wanted, but when exposed to, do want. To do this, I looked at various user and item level collaborative filtering methods. Filtering methods were based on collecting and analyzing data on customer activities and predicting what they will like based on the similarity with other customers or items. This approach assumes that customers who bought in the past will buy again in the future and that they will like similar kinds of items as they bought in the past.

Customer collaborative filtering involves looking for lookalike customers and offering products based on what his/her lookalike has chosen. For example, if customer A likes t-shirts, mugs, and posters and customer B likes mugs, posters, and canvas art then they have similar interests and customer A should like canvas art and customer B should like t-shirts.

Item collaborative filerting is like customer collaborative filtering, but instead of finding customers, we are finding an item lookalike, this approach can be used to show related products to boost sales. For example, if a customer likes white short-sleeve t-shirts, this algorithm will suggest items like blue short-sleeve t-shirts or white long-sleeve t-shirts. This algorithm requires far fewer resources than customer collaborative filtering.

To perfrom the various methods, I leveraged LightFM. LightFM is a package that leverages a hybrid latent representation recommender model where the model learns embeddings, or latent representations in a high-dimensional space, for customers and items in a way that encodes customer preferences over items. When multiplied together, these representations produce scores for every item for a given customer with high scoring items more likely to be interesting to the customer. The documentation then describes that the customer and item representations are expressed in terms of their features - an embedding is estimated for every feature, and these features are then summed together to arrive at representations for customers and items. The embeddings are learned through stochastic gradient descent methods and the models were tested with four loss functions: 
●	Logistic
●	Bayesian Personalized Ranking (BPR) pairwise loss
●	Weighted Approximate-Rank Pairwise (WARP loss. Maximizes the rank of positive examples by repeatedly sampling negative examples until rank violating one is found. 
●	k-OS WARP: k-th order statistic loss which is a modification of WARP that uses the k-th positive example for any given user as a basis for pairwise updates.

Most models served up feasible results. Because of this, it is suggested to test the models with A/B testing on the site to show the recommendations derived by the different models to different segments of website visitors at the same time. The performance of each recommendation engine can then be measured to see which drives more conversion and should be implemented across sellers. 
