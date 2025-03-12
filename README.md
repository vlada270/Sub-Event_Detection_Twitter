# Sub-Event Detection in Twitter Streams 
**Authors:** Vlada Voronina and Lauren Ramanantsoa  
**Emails:** vlada.voronina@polytechnique.edu, lauren.ramanantsoa@polytechnique.edu  
**Team:** tLV

### About our project
We present our approach for detecting notable subevents in football games. We have 5 million labelled tweets of data from 16 games from 2010 and 2014 (see `train_tweets/`). Each tweet has an 'ID', a 'MatchID', 'PeriodID', 'EventType' (label) and a 'Timestamp'. Each tweet belongs to a 1-minute bin of time, labelled by 'ID'. We aim to predict whether or not an event happened for each bin of an unlabelled test set of 4 new games (see `eval_tweets/`) with the highest accuracy. With noisy data, we focus on preprocessing. We try classical machine learning and deep learning models to capture bin level and tweet-level natural language information. Finally, we propose a multi-level perceptron model yielding a test accuracy of 0.738 on Kaggle data from bin-level aggregation.


### Our files
- `'FinalCode.ipynb'` contains the code to run our final MLP model. It also includes Logistic Regression, k-Nearest Neighbors, Linear SVM, Gradient Boosting, Random Forest, Ridge, AdaBoost, Perceptron xgboost and catboost classifiers as a comparison.
- `'RNN_CNN.ipynb'` contains the code to run LSTMs and CNNs to process invidual tweets.

### Data placement
- **FinalCode.ipynb**
    - **Option 1:** You can connect to your kaggle account and upload all the data from the competition, so you dont need to upload anything directly. 
    - **Option 2:** 
                1) Open the script and locate the cell with the comment: # Read all training files and concatenate them into one dataframe
                2) Update the path in the following lines: 
                   for filename in os.listdir('PATH/train_tweets'):
                   df = pd.read_csv("PATH/train_tweets/" + filename)
                3) Locate the last cell in the script where the evaluation tweets are read and update the path in the following lines:
                   for filename in os.listdir('PATH/eval_tweets'):
                   df = pd.read_csv("PATH/eval_tweets/" + filename)
    
- **RNN_CNN.ipynb**
    - Place the `train_tweets/` and `eval_tweets/` folders in the top-level directory of the project. Ensure they are not inside any subdirectories and remain accessible from the root of the project structure. Run the cells labelled **#Import data from directory**.
