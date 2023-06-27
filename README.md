# DiSCoVeR-SuperCon-NOMAD-SMACT

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cseeg/DiSCoVeR-SuperCon-NOMAD-SMACT/blob/main/main.ipynb)

* this code uses the `DiSCoVeR` algorithm (Descending from Stochastic Clustering Variance Regression) ([[software](https://github.com/sparks-baird/mat_discover)], [[paper](https://dx.doi.org/10.1039/D1DD00028D)]) to predict chemically novel, high-temperature superconductors. The model trains on the [`SuperCon`](https://github.com/vstanev1/Supercon) data set and predicts through chunks of [a curated dataset snapshot](https://figshare.com/articles/dataset/NOMAD_Chemical_Formulas_and_Calculation_IDs/19319783) based on the `NOMAD` ([Novel Materials Discovery](https://nomad-lab.eu/)) database. A chemical validity label is assigned to each composition through [a modified version](https://github.com/txie-93/cdvae/blob/51383a9bf6477db01fb66b341ff75b5bad33ca90/scripts/eval_utils.py#L121-L162) of [`SMACT`](https://github.com/WMD-group/SMACT) (semiconducting materials by analogy and chemical theory) ported from [CDVAE](https://github.com/txie-93/cdvae).

* `dens_score.csv` and `peak_score.csv` are the expected output files after running `main.ipynb`. These contain a weighted score involving superconductor performance (maximize superconducting critical temperature) and chemical novelty, where chemical novelty is defined either using a density-based proxy or a peak-based proxy. These files are reduced to 100,000 formulas due to size.

* In the post processing file, `final_comps_withhighlights.csv` and `final_comps_nohighlights.csv` are similar to 'final.csv' but after considering the conditional thresholds defined in the paper (`is_valid== TRUE & predicted_e_above_hull <= 0.1 & is_theoretical >= 0.95`).

Below is a flowchart that depicts the workflow:
![flowchart](https://i.imgur.com/7Y6ifJg.png "flowchart")

## Citations
If you find this work useful, please consider citing the following works.

```bib
@article{baird_discover_2022,
	title = {{DiSCoVeR}: a materials discovery screening tool for high performance, unique chemical compositions},
	volume = {1},
	issn = {2635-098X},
	shorttitle = {{DiSCoVeR}},
	url = {http://xlink.rsc.org/?DOI=D1DD00028D},
	doi = {10.1039/D1DD00028D},
	language = {en},
	number = {3},
	urldate = {2022-08-05},
	journal = {Digital Discovery},
	author = {Baird, Sterling G. and Diep, Tran Q. and Sparks, Taylor D.},
	year = {2022},
	pages = {226--240},
}
```

```bib
@article{stanev_machine_2018,
	title = {Machine learning modeling of superconducting critical temperature},
	volume = {4},
	issn = {2057-3960},
	url = {http://www.nature.com/articles/s41524-018-0085-8},
	doi = {10.1038/s41524-018-0085-8},
	language = {en},
	number = {1},
	urldate = {2022-08-05},
	journal = {npj Computational Materials},
	author = {Stanev, Valentin and Oses, Corey and Kusne, A. Gilad and Rodriguez, Efrain and Paglione, Johnpierre and Curtarolo, Stefano and Takeuchi, Ichiro},
	month = dec,
	year = {2018},
	pages = {29}
}
```

```bib
@article{Baird2022,
	author = {Sterling G. Baird},
	title = {NOMAD Chemical Formulas and Calculation IDs},
	year = {2022},
	month = {3},
	url = {https://figshare.com/articles/dataset/NOMAD_Chemical_Formulas_and_Calculation_IDs/19319783},
	doi = {10.6084/m9.figshare.19319783.v3}
}
	
```

```bib
@article{draxl_nomad_2019,
	title = {The {NOMAD} laboratory: from data sharing to artificial intelligence},
	volume = {2},
	issn = {2515-7639},
	shorttitle = {The {NOMAD} laboratory},
	url = {https://iopscience.iop.org/article/10.1088/2515-7639/ab13bb},
	doi = {10.1088/2515-7639/ab13bb},
	language = {en},
	number = {3},
	urldate = {2022-08-05},
	journal = {Journal of Physics: Materials},
	author = {Draxl, Claudia and Scheffler, Matthias},
	month = jul,
	year = {2019},
	pages = {036001}
}
```

```bib
@article{xie2021crystal,
	title={Crystal diffusion variational autoencoder for periodic material generation},
	author={Xie, Tian and Fu, Xiang and Ganea, Octavian-Eugen and Barzilay, Regina and Jaakkola, Tommi},
	journal={arXiv preprint arXiv:2110.06197},
	year={2021}
	url = {http://arxiv.org/abs/2110.06197},
}
```

```bib
@article{davies_smact_2019,
	title = {{SMACT}: {Semiconducting} {Materials} by {Analogy} and {Chemical} {Theory}},
	volume = {4},
	issn = {2475-9066},
	shorttitle = {{SMACT}},
	url = {http://joss.theoj.org/papers/10.21105/joss.01361},
	doi = {10.21105/joss.01361},
	language = {en},
	number = {38},
	urldate = {2022-08-05},
	journal = {Journal of Open Source Software},
	author = {Davies, Daniel and Butler, Keith and Jackson, Adam and Skelton, Jonathan and Morita, Kazuki and Walsh, Aron},
	month = jun,
	year = {2019},
	pages = {1361}
}
```
