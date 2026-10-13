# Basics

users : who have some ratings

items : which user rate

```
A recommender system is a personalised decision support system that estimates the usefulness
of items for a user and presents a ranked set of suitable options.
```

Problems to solve

1. rating/utility prediction or unknown item by a user
2. getting top k ranked item for a user (generally from unsceen ratings)

How it differes from search


| aspect         | search                   | RS                                  |
| -------------- | ------------------------ | ----------------------------------- |
| starting point | keyword/query            | history, context, profile, activity |
| intention      | stated by user           | incomplete, exploratory             |
| core match     | query to item            | user to item                        |
| output         | matching results         | ranked list                         |
| user mind      | knows what to ask        | need assistence in discovery        |
| failures       | poor query interpretaton | poor preference,bias                |


3. Operational goals
  1. relevence : recommendation should fit user interest
  2. novelty : help user discover unknown items
  3. serendipity : useful and non obvious result
  4. diversity : avoidlist of near duplicate items
  5. coverage : exposes more catelogueand serves more user
  6. trust : system should be understandableand dependable
  7. robustness : resist noise, manipulation and malicious bihaviour
  8. scalability : operatae under large volume
4. Pipeline 
  1. collect data
  2. represent data
  3. learn
  4. score
  5. filter
  6. rank
  7. present
  8. evaluate
5. Types

  | type             | primary evidence                      | main strength | main weakness |
  | ---------------- | ------------------------------------- | ------------- | ------------- |
  | collaborative    | user-item interaction                 |          |          |
  | content-based    | item attribute, user history          |          |          |
  | knowledge-based  | user requirement and domain knowledge |          |          |
  | demography based | group attributes                      |          |          |
  | content-aware    | user item and situation               |          |          |
  | hybrid           | multiple evidence score               |          |          |

6. Type details
  1. colaborative
    1. user-based
    2. item-based
    3. model-based : latent factor
  2. content-based
  3. knowledge-based
    1. constraint based : logical constraint on features
    2. case based : retrieve items or past cases based on stated needs
  4. demographic
  5. context
  6. hybrid
7. Data sources
  1. empty doesn't mean dislike most of the time
  2. User data : persistent long term profile, short term session, social relational data
  3. Item data : structured, text, image/audio/video, knowledge relation
  4. Interaction data : 
    1. explicit feedback : rating, review, feedback, statment  (unambiguous but less in amount)
    2. implicit feedback : views,clicks,time, rewatches,etc  (ambiguous but abundant)
  5. Contexual and temporal data : useful in chonological ordering of data
    1. current situation may differ from past
    2. evaluation shoudl be based on past data only
8. User-item matrix
  1. very sparse : sparcity = unobsered entry / m x n (m:users n:items)
9. Exposure and slection bias
  1. obsereved results is based on what got shown to user and what user chose to see, so it is not random
  2. bias source
    1. exposure : user only iteract with item he has ppotunity with
    2. selection : user chosses which item to rate
    3. popularity : more popular, more interaction
    4. position : early gets more attention
    5. survivorship : removed, unavialable may not get considered
    6. feedbackloop : early recc, influece later
10. Data preprocessing
  1. purpose
  2. interaction data schema
  3. cleaning : remove currupt data. handle duplicate, standardize time, feasable item iteraction (which can be done in future)
  4. transformation of explicit rating : gloabls scaling, user-mean centering, threshholding,   
  5. transformation of implicit events : weathed sum
  6. preparing item features : categorical, numerical, text, 
  7. filtering sparse users and items
11. Evaluation
  1. offline testing : historical train/test/validation testing
  2. online testing : A/ B testing
  3. RMSE, MAE
  4. precision : relevent recommendation / all recommendation
  5. recall : relevent recommendation given / total relevent recommendations
  6. f1 = 2pr / p+r
  7. precision@5 : out of top 5 recommended how many are relevent
  8. recall@10 : out of top 10 recommended how can are from relevent set
  9. hitrate@10 checks weather atleast 1 relevant item apears in top 10 (1 if atleast 1 came else  0)
  10. normalized discounted cummulative gain = DCG@K / IDGC@K
    1. DGC@K = sum (2^rel_i  -1)/(log_2 i+1)     for predicted ranking
    2. IDGC@K = best possible relevent ranking
  11. Mean Reciprocal Rank = avg(1/rank)  of first relevent item for each query
  12. Fairness
  13. Coverage
  14. Novelity = -log_2(P(i))    P(i) proportaion of users who interacted with i
  15. Diversity : ILD@K

 