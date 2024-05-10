# Drug Repurposing using Knowledge Graphs

Files Required for the project - https://drive.google.com/drive/folders/18R2rzZfK-V6MRhZx-EBCSw-zr1P4shW0?usp=sharing

The project addresses the need for rapid drug discovery by proposing the construction and analysis of a comprehensive Drug Repurposing Knowledge Graph (DRKG) to facilitate the identification of potential treatments for Covid-19 and other diseases. Drug Repurposing invloves finding new therapeutics uses for existing drugs, accelerating drug devolpment and reducing cost.


### Approach

Formulating Drug Repurposing as Knowledge Graph Completion:

- #### Graph Representation: 
  Formulate DR as a link prediction task on the Drug Repurposing Knowledge Graph (DRKG) using Knowledge Graph Embedding (KGE) models.

- #### Link Prediction:
  Predict new links between drug entities and disease entities (treat links) or between drug entities and gene entities (inhibit/bind links) associated with the disease of interest.

- #### Embedding Learning: 
  Employ a TransE KGE model on DRKG, utilizing L2 distance optimization to obtain vector embeddings (400 × 1) for biological entities and relations.

- #### Scoring Function: 
  Define a scoring function, f(h, r, t) = γ − ||h + r − t||², where γ is a model parameter (set to 12.0). Higher scores indicate greater confidence in the connection between head (h) and tail (t) entities under relation (r).

- #### Evaluation for Covid-19:
  Assess DRKG performance in drug repurposing for Covid-19, considering corona-virus diseases (SARS, MERS, SARS-COV2) as target diseases.

- #### Formulations for DR Task:

  - ##### Formulation 1: 
    Predict direct links between disease entities and drug entities in DRKG.

  - ##### Formulation 2: 
    Predict links among gene entities inhibited by drug entities, where genes are associated with the target disease.

- #### Candidate Selection: 
  Choose FDA-approved drugs from Drugbank as candidates, excluding drugs with a molecular weight less than 250 daltons.

- #### Validation with Clinical Trials: 
  Collect 32 clinical trial drugs for Covid-19 to validate predictions.

- #### Result Analysis: 
  Evaluate the overlap between predicted drugs and those used in clinical trials, demonstrating the efficacy of the DRKG in identifying potential drug candidates.


### Dataset
  Drug Repurposing Knowledge Graph (DRKG) comprises 97,238 entities across 13 types and 5,874,261 triplets across 107 edge types, integrating data from six databases and recent publications, facilitating comprehensive exploration and analysis for drug repurposing efforts, including those related to Covid-19.


### Trans-E Model
  The TransE model optimizes an objective function to learn embeddings. The objective function is designed to minimize the energy or scoring function associated with triplets (h, r, t), where h is the head entity, r is the relation, and t is the tail entity. 
  
![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/518ffad2-a73d-4046-a4c2-a356c2ac3e96)

Here,
  - f(h,r,t) is the energy or score associated with the triplet.
  - γ is a margin parameter.
  - ∣∣h+r−t∣∣2​ is the L2 norm (Euclidean distance) between the embeddings of h, r, and t.


### Evaluation Metrics

  - ##### Hit@K:
     Hit@K calculates the percentage of test cases where the correct entity is ranked within the top K predictions. It is often reported for different values of K (e.g., Hit@1, Hit@3, Hit@10). Higher Hit@K values indicate better performance.

  - ##### Normalized Discounted Cumulative Gain (NDCG):
     NDCG is a ranking evaluation metric that takes into account the position of the correct entity in the ranked list. It assigns higher scores to correct entities that appear higher in the ranking. Higher NDCG values indicate better performance.


### Results While Training the Model

![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/bddbcc26-cb5c-40b9-acab-5178332da76b)

  The TransE model generated drug scores and scaled scores for each drug, indicating their potential for repurposing in treating Covid-19. The higher the score, the better the suitability of the drug for repurposing. The scaled scores provide anormalized measure for comparison.

![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/0253c3e9-f6c6-4465-8626-3f7d58ad2494)

  Similar to TransE, the TransR model also produced drug scores and scaled scores. However, the projection mechanism used in TransR might lead to different interpretations compared to TransE. Analysis of these scores provides insights into drug repurposing candidates.

![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/84747602-27cb-4646-a224-1ab39b981999)

  The DistMult model's output includes drug scores and scaled scores, offering another perspective on drug repurposing. Understanding the significance of these scores requires considering the unique characteristics of the DistMult model and its implications for drug repurposing.

![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/a0868451-1d03-4b2a-a982-a7c6dca90693)

  Lastly, the Complex model's output provides additional drug scores and scaled scores, contributing to the comprehensive evaluation of potential drug repurposing candidates. Interpretation of these scores involves understanding the complex number representations used in the model.

### Final Result
In this study, we explored the effectiveness of various knowledge graph embedding models, including TransE, TransR, DistMult, and Complex, for drug repurposing in the context of Covid-19 treatment. The experimental evaluation revealed insights into the suitability of different drugs for repurposing based on their scores generated by each model. Future research can focus on integrating additional data sources and refining the models to enhance the accuracy and robustness of drug repurposing predictions in combating emerging diseases like Covid-19. By training a TransE model we have obtained a we have got an accuracy score of 91.04%, which indicates that TransE performs better than other model for the task of drug repurposing for Covid -19. We have obtained top 6 drugs which have capability to cure Covid-19 .

![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/61beb9ff-9dcc-4582-bb35-09a97436a9c4)












