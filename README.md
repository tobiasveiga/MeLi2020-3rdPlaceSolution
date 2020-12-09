# MeLi2020_3rd_PlaceSolution
MeLi 2020 challenge Winner Solution

The solution is a candidate generator and ranker approach.

The candidate generator turns each session into a bag of words of three data types (session items, session domains and session queries words) and uses KNN to get the 20 most simliar sessions. The KNN only fits on data where the bought item was in the session.

The ranker transforms the problem into a classification problem where we have to classify from all the candidate items, which one was bought. Each candidate item from each session in the database becomes a sample. The target is binary (1 - bought, 0 not bought). Here many features are added (item features, session features, Complex Network metrics, etc.). Three bosting models are used (XGBoost, LightGBM, CatBoost) and their probabilities predictions are summed. The items with higher summed probabilities of each session are selected as the top 1 recommendation.

Finally, a few more post-processing is done to rank the rest of the predictions.

## How to run the code

Create environment and install dependencies:

conda create --name <env> --file requirements_conda.txt python=3.7.9
  
To generate a solution, do the following:

1) Run the notebook KNN_GENERATOR.pynb
2) Run the notebook RANKER04.ipynb
3) Find the solution file at the submissions folder

OBS: I will improve the description and code of this solution in the following weeks. For now, that's all I can do. 
