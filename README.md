# ntds-project
mice genetics


### Project Roadmap

- 1. Exploratory Data Analysis
  - Obtain PhenoID for diseases of interest (Malaria and Influenza)
  - Get Phenotype value associated to the PhenoID of interest for each mouse
  - Check distribution of Phenotype values obtained previously
  - Building a dataframe that will be use for constructing the graph
  
- 2. Setting a baseline
  - Building a regression model (random forest, ridge regression) to predict phenotype values given genes expression values:
   - We take all expressions and filling missing values with median
   - We take only the expressions that are present
   
- 3. Building co-expression graph
  - (Genes, Tissue) as node and we use the expression values of each mouse to compute the distance metric (euclidian?)

- 4. Building inhibition graph
  - Same but with inverse distance 
  
- 5. Smoothing graphs using Tikhonov filter
  - Smoothing is for filling missing values expression

- 6. Prediction of phenotype values using additional expression data from 5.
  - Using same methods

- 7. Building graph with mice as nodes, expression data as distance metric and phenotype value as label
 - Identify communities
 - k-NN for label prediction
