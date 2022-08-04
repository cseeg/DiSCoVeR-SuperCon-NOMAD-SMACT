# DiSCoVeR-SuperCon-NOMAD
* this code uses the `DiSCoVeR` algorithm (Descending from Stochastic Clustering Variance Regression) to predict chemically novel, high-temperature superconductors. The model trains on the `SuperCon` data set and predicts through chunks of a curated data set taken from the `NOMAD` (Novel Materials Discovery) repository. The data is screened for chemical validity through `SMACT` (semiconducting materials by analogy and chemical theory) before training and testing.

* `dens_score.csv` and `peak_score.csv` are the expected output files after running `main.ipynb`. These contain the most chemically novel (`dens_score`) and highest performing (`peak_score`) formulas of superconductors that were predicted. These files are reduced to 100,000 formulas due to size.

Below is a flowchart that depicts the workflow:
![flowchart](https://i.imgur.com/7Y6ifJg.png "flowchart")
