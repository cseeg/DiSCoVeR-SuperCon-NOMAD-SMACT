# DiSCoVeR-SuperCon-NOMAD-SMACT
* this code uses the `DiSCoVeR` algorithm (Descending from Stochastic Clustering Variance Regression) ([[software](https://github.com/sparks-baird/mat_discover)], [[paper](https://dx.doi.org/10.1039/D1DD00028D)]) to predict chemically novel, high-temperature superconductors. The model trains on the [`SuperCon`](https://github.com/vstanev1/Supercon) data set and predicts through chunks of [a curated dataset snapshot](https://figshare.com/articles/dataset/NOMAD_Chemical_Formulas_and_Calculation_IDs/19319783) based on the `NOMAD` ([Novel Materials Discovery](https://nomad-lab.eu/)) database. A chemical validity label is assigned to each composition through [a modified version](https://github.com/txie-93/cdvae/blob/51383a9bf6477db01fb66b341ff75b5bad33ca90/scripts/eval_utils.py#L121-L162) of [`SMACT`](https://github.com/WMD-group/SMACT) (semiconducting materials by analogy and chemical theory) ported from [CDVAE](https://github.com/txie-93/cdvae).

* `dens_score.csv` and `peak_score.csv` are the expected output files after running `main.ipynb`. These contain a weighted score involving superconductor performance (maximize superconducting temperature) and chemical novelty, where chemical novelty is defined either using a density-based proxy or a peak-based proxy. These files are reduced to 100,000 formulas due to size.

Below is a flowchart that depicts the workflow:
![flowchart](https://i.imgur.com/7Y6ifJg.png "flowchart")

## Citations
@Article{D1DD00028D,
author ="Baird, Sterling G. and Diep, Tran Q. and Sparks, Taylor D.",
title  ="DiSCoVeR: a materials discovery screening tool for high performance{,} unique chemical compositions",
journal  ="Digital Discovery",
year  ="2022",
volume  ="1",
issue  ="3",
pages  ="226-240",
publisher  ="RSC",
doi  ="10.1039/D1DD00028D",
url  ="http://dx.doi.org/10.1039/D1DD00028D"

@Article{Stanev_2018,
	doi = {10.1038/s41524-018-0085-8},
	url = {https://doi.org/10.1038%2Fs41524-018-0085-8},
	year = 2018,
	month = {jun},
	publisher = {Springer Science and Business Media {LLC}
},
	volume = {4},
	number = {1},
	author = {Valentin Stanev and Corey Oses and A. Gilad Kusne and Efrain Rodriguez and Johnpierre Paglione and Stefano Curtarolo and Ichiro Takeuchi},
	title = {Machine learning modeling of superconducting critical temperature},
	journal = {npj Computational Materials}
}

@Article{D1DD00028D,
author ="Baird, Sterling G. and Diep, Tran Q. and Sparks, Taylor D.",
title  ="DiSCoVeR: a materials discovery screening tool for high performance{,} unique chemical compositions",
journal  ="Digital Discovery",
year  ="2022",
volume  ="1",
issue  ="3",
pages  ="226-240",
publisher  ="RSC",
doi  ="10.1039/D1DD00028D",
url  ="http://dx.doi.org/10.1039/D1DD00028D"

@Article{Draxl_2019,
	doi = {10.1088/2515-7639/ab13bb},
	url = {https://doi.org/10.1088/2515-7639/ab13bb},
	year = 2019,
	month = {may},
	publisher = {{IOP} Publishing},
	volume = {2},
	number = {3},
	pages = {036001},
	author = {Claudia Draxl and Matthias Scheffler},
	title = {The {NOMAD} laboratory: from data sharing to artificial intelligence},
	journal = {Journal of Physics: Materials}

@Article{xie2021crystal,
  title={Crystal diffusion variational autoencoder for periodic material generation},
  author={Xie, Tian and Fu, Xiang and Ganea, Octavian-Eugen and Barzilay, Regina and Jaakkola, Tommi},
  journal={arXiv preprint arXiv:2110.06197},
  year={2021}
}

@Article{davies2019smact,
  title={SMACT: Semiconducting materials by analogy and chemical theory},
  author={Davies, Daniel W and Butler, Keith T and Jackson, Adam J and Skelton, Jonathan M and Morita, Kazuki and Walsh, Aron},
  journal={Journal of Open Source Software},
  volume={4},
  number={38},
  pages={1361},
  year={2019}
}
