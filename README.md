# Genetically determined susceptibility to malaria
Report describing the work is in `report.pdf` file.

To reproduce our results:
1. Download dataset from [here](https://drive.switch.ch/index.php/s/mtQ2F0dYc7dHOtQ) and put it under "data" directory in the repo root.
2. Create conda environment from `environment.yml` and activate it by running:
    ```
   conda env create -f environment.yml
   conda activate ntds_2019 
   ```
3. Execute the jupyter notebooks in the following order:
    1. `baseline_phenotype_predictor.ipynb`
    2. `coexpression_graph_construction.ipynb`
    3. `coexpression_graph_exploration.ipynb`
    3. `SNP_expression_imputation.ipynb`

### Stages of the project
1. Exploratory Data Analysis
    - Obtain PhenoID for diseases of interest (Malaria and Influenza)
    - Get phenotype value associated to the PhenoID of interest for each mouse
    - Check distribution of phenotype values obtained previously
    - Select single phenotype for simplicity: malaria susceptibility
    - Normalize the data: subtract mean and divide by standard deviation
    - Building a dataframe of all (SNP expression, tissue) pairs for all mice for constructing the coexpression graph
2. Setting a baseline
    - Building a regression model, ridge regression and random forests, to predict phenotype values given genes expression. We take all expressions and filling missing values with mean
3. Building co-expression graph
    - (Genes, Tissue) as node and we use the expression values of each mouse to compute the distance metric. 
5. Imputation of SNP expression on co-expression graph using Tikhonov filter
    - Smoothing for filling missing values for SNP expression
6. Prediction of phenotype values using additional expression data from 5.
    - Using the best method, comparing with baseline.
7. Building graph with mice as nodes, expression data as distance metric and phenotype value as label
    - Identifying communities
