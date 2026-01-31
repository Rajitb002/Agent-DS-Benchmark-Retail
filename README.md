# Agent-DS-Benchmark (Retail Challenge)

Read more about the challenge here:
https://agentds.org/about

"_Minnesota's diverse industrial landscape—spanning clinical triage, manufacturing, retail, agriculture, and more—provides an ideal testbed for evaluating how humans and AI can collaborate in specialized domains. By creating standardized benchmarks across these domains, we aim to accelerate the development of effective human-AI partnerships that augment domain expertise with AI's analytical capabilities._"

Team: 'agi'
- Challenges 1 and 2 for Retail Sector in the AgentDS Benchmark Challenge held by U Minnesota Twin Cities.
- We placed 11/19 in retail.

<img width="1583" height="640" alt="image" src="https://github.com/user-attachments/assets/4252bd79-e0d7-4312-8d42-13478df87203" />

## Problem:
Combat credit fraud and defaults by using AI agents and time series data (transactions) to predict them in the retail sector.

## Solution:
- We began by analyzing the synthetic dataset given by the hosts. Then we performed EDA, aggregated all our datasets into a master set and performed feature engineering.
  - We found that the fraud to not fraud feature imabalance was severe.
  - We removed any personal (fake) data. This made sure models did not overfit.
- After that we trained various models. We stuck with classical models due to the structured nature of the datasets. 
  - The prominent ones were: Random Forest, XGBoost, AdaBoost and Log Regression.

## Results:
- Our best performing model was **XGBoost** for both cases with a F1 score of **0.5211 and 0.7005** for Challenge 1 and 2 respectively. 
- We are proud of our results considering that we began the challenge 3-4 days (10 day duration) before its deadline.
<img width="1595" height="830" alt="image" src="https://github.com/user-attachments/assets/bc0ee937-34d8-4688-9025-b4b730b042cc" />

## Takeaways:
- Feature engineering led to the biggest increase in model performance compared to kfold cross validation.
  - Time series dataset allowed us to feature engineer even more — we added rolling windows and lagged features.
- Feature balancing using Imputation/SMOTE/interpolation did not lead to performance increase - a key suspect could be the limited size of the datasets and their synthetic nature.
- We also tried ensemble learning and neural nets but did not find much success compared to XGBoost.
- We saved time on training and cross validation using CUDA on Google Colab's higher end GPUs (Likely A100s and/or H100s..)
- We decided to ultimately abandon the agent based approach nature of the competition.
  - Agents don't have the greatest success rates for task completion (https://arxiv.org/html/2505.18878v1).
  - We also did not have the required domain knowledge for about two days to guide the agent yet.
    - This put us on a pedestal due to the time constraint (1-2 days remained). So we made an executive decision. 
