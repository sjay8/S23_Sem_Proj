# Write Up

1. In one or two sentences, present your project to us!

This project uses a BERT model to predict whether sarcasm exists in a newspaper article headline. 

2. Dataset: Indicate the dataset you chose to use, any preprocessing steps that were applied, as well as the reasoning behind these choices.

The dataset used is from Kaggle specifically the Sacrasm_Headlines_Dataset. The preprocessing steps that were used were (1) deleting the article links in my dataframe object since they are unnecessary for the task and increasing processing time. Another step was (2)getting the data ready for the BERT model. The headline strings  were changed into tokens with token ids with CLS and SEP along with padding to make all of the headlines uniform and to make the pooling scheme of BERT work. The  tokens were converted to tensors since that is the required data structure of most models.  Finally, testing and train dataset splitting was completed as well.

3. Model Development and Training: Discuss your model implementation choices, the training procedure, the conditions you settled on (e.g., hyperparameters), _and discuss why these are a good set for your task

I used 3 epochs since BERT best works on 2-4 epochs, I found 3 to perform better by 3% than 2 epochs but had a 30% shorter runtime than 4 epochs. I also used a learning rate of 3.5E6 after reading some research papers that recommended this as the optimal learning rate for BERT models. All other parameters were standard.

4. Model Evaluation/Results: Present the metrics you chose and your model evaluation results.

I also calculated the accuracy which came out to 94%. I used the Matthews Correlation Coefficient since this metric is best for binary classification evaluations. The value was calculated automatically and manually via confusion matrix values. The final value was 0.976 which means the observed and predicted values nearly always matched up or very strong positive correlation was exhibited. 

5. Discussion: 
How well does your dataset, model architecture, training procedures, and chosen metrics fit the task at hand? 

Given my high MCC, I think my dataset and training procedures and metrics fit the task at hand. Furthermore, BERT is a state-of-the-art model that has extremely high accuracy and is able to interpret complex linguistic datasets. 

6. Can your efforts be extended to wider implications, or contribute to social good? Are there any limitations in your methods that should be considered before doing so?

This model could be used in social media to better understand its users or refine fake news identification (prevent the unnecessary flagging headlines as fake news when they are actually sacrastic or satiricial). The limitation is the BERT pre-built dictionary needs to overlap with the dataset and a lanugage that BERT has been trained on only can be used.

7. If you were to continue this project, what would be your next steps?

I would  continue changing the other hyperparameters (LR, batchsize), gradient type,freezing the first few layers of the model (shown to improve processing time but maintain accuracy) or changing the test/train split ratio
