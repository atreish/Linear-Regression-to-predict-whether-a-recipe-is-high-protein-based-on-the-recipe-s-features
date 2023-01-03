# Linear Regression for recipe nutritional content

# Scenario
You are a team of data scientists and ML engineers working for a recipe website. Every day your website receives recipe submissions from users. The recipes are analyzed by a lab to ascertain their nutritional content. Then the recipe is posted on your website along with its nutrition information. Your company makes money by running ads along with the recipes. Recently, ad space on high-protein receipes has been in high demand, so the company is interested in maximizing the use of the high-protein recipes that users submit. The problem is that the lab generally can't analyze recipes as quickly as they are submitted, so their queue is always full. The good news is that the lab will let you push recipes to the front of the queue so that they will get processed sooner. If you suspect a recipe will, after analysis, be labeled "high protein", then it would be a good idea to push it to the front of the queue.

# Task
Your team's job is to build a model that predicts whether a recipe is high protein based on features of the recipe (ex., the ingredients). Each new recipe will be presented to your model. If you model predicts that it will be high protein, then that receipe will be pushed to the front of the lab's queue. Otherwise it will be pushed to the back ofthe lab's queue.

# Note
Predictions are great -- as a starting point. But no business ever got to IPO by saying, "We have the best mean-squared-error in our industry!" Instead, businesses survive and thrive by earning money. Since your team is part of a business, you'll need to understand the dollar value of your model: How much more money could your company earn if they deployed your model?

Fortunately, you have a simulator that can turn model predictions into ad revenue estimates. The simulator simulates the users' recipe submissions
pushing recipes onto the front or back of the lab's queue based on your model's predictions the lab's daily recipe analysis daily ad revenue from high- and low- protein ads. The simulator's not perfect, but it can used to evaluate your model is dollar terms. Doing this can help compare the value of your model to the value of other teams' efforts to improve the business -- whether they are building models, writing code, selling ads, designing web pages, or doing whatever else makes your business work.

The input to the simulator is hp_predictions_and_actuals, a list of tuples (prediction, actual). actual should be 1 if the recipe is high protein and 0 if the recipe is not high protein. prediction should be your model's prediction of actual, based on a recipe's features. (N.B.: simulate() doesn't use the recipe's features.)

hp_predictions_and_actuals might look like:

hp_predictions_and_actuals = [
    (1, 1),  # predict high-protein, actually high-protein
    (0, 1),  # predict low-protein, actually high-protein
    (0, 0),  # predict low-protein, actually low-protein
    (1, 1),  # predict high-protein, actually high-protein
    .
    .
    .
]
You could construct hp_predictions_and_actuals with hp_predictions_and_actuals = list(zip(predictions, actuals)) if you had a list (or an ndarray or a Pandas Series) of predictions and another of actuals.

To use simulate(), you'll probably create one entry in hp_predictions_and_actuals for each row in the data frame then call simulate(hp_predictions_and_actuals). This call will return an estimate of one year's revenue. Please see the comments in simulate() for more information.

Evaluate your model in dollar terms using simulate(). simulate()'s output is a random variable, so please report the standard error of your model's dollar value, too.
