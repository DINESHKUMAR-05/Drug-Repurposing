# Drug Repurposing using Knowledge Graphs

The project addresses the need for rapid drug discovery by proposing the construction and analysis of a comprehensive Drug Repurposing Knowledge Graph (DRKG) to facilitate the identification of potential treatments for Covid-19 and other diseases. Drug Repurposing invloves finding new therapeutics uses for existing drugs, accelerating drug devolpment and reducing cost.


### Approach

Formulating Drug Repurposing as Knowledge Graph Completion:

#### Graph Representation: 
Formulate DR as a link prediction task on the Drug Repurposing Knowledge Graph (DRKG) using Knowledge Graph Embedding (KGE) models.

#### Link Prediction:
Predict new links between drug entities and disease entities (treat links) or between drug entities and gene entities (inhibit/bind links) associated with the disease of interest.

#### Embedding Learning: 
Employ a TransE KGE model on DRKG, utilizing L2 distance optimization to obtain vector embeddings (400 × 1) for biological entities and relations.

#### Scoring Function: 
Define a scoring function, f(h, r, t) = γ − ||h + r − t||², where γ is a model parameter (set to 12.0). Higher scores indicate greater confidence in the connection between head (h) and tail (t) entities under relation (r).

#### Evaluation for Covid-19:
Assess DRKG performance in drug repurposing for Covid-19, considering corona-virus diseases (SARS, MERS, SARS-COV2) as target diseases.

#### Formulations for DR Task:

##### Formulation 1: 
Predict direct links between disease entities and drug entities in DRKG.

##### Formulation 2: 
Predict links among gene entities inhibited by drug entities, where genes are associated with the target disease.

#### Candidate Selection: 
Choose FDA-approved drugs from Drugbank as candidates, excluding drugs with a molecular weight less than 250 daltons.

#### Validation with Clinical Trials: 
Collect 32 clinical trial drugs for Covid-19 to validate predictions.

#### Result Analysis: 
Evaluate the overlap between predicted drugs and those used in clinical trials, demonstrating the efficacy of the DRKG in identifying potential drug candidates.

### Dataset
Drug Repurposing Knowledge Graph (DRKG) comprises 97,238 entities across 13 types and 5,874,261 triplets across 107 edge types, integrating data from six databases and recent publications, facilitating comprehensive exploration and analysis for drug repurposing efforts, including those related to Covid-19.

### Trans-E Model
The TransE model optimizes an objective function to learn embeddings. The objective function is designed to minimize the energy or scoring function associated with triplets (h, r, t), where h is the head entity, r is the relation, and t is the tail entity. ![image](https://github.com/DINESHKUMAR-05/Drug-Repurposing-using-Knowledge-Graphs/assets/111517362/e9575f3c-ae31-459b-8a29-8fc0530af019)



