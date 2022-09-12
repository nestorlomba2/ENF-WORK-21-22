# Research project on the analysis of the geographical features of the electrical network frequency (ENF) signal

This repository aims to gather all the scripts related to the research project on the analysis of the geographical features of the ENF signal, that materalized in a Final Year Dissertation for the University of Vigo found also here.

This project has been made using MATLAB, and all the code is written in the MATLAB language.

The project is too big for github, so it can be downloaded here: https://mega.nz/folder/R18hAJTT#iRYcUBAMT_qOTfXu1ZHarQ

---
## Folder structure

**data** - original ENF signal data files, tables of distances and scripts to convert the original ENF files to .mat.

**media** - images and pdf maps of the networks.

**OLD_pipeline** - older version of this repository, just in case.

**results_TFG** - output figures generated for the final year dissertation (TFG in spanish)

**scripts** - signal processing and plotting of figures

**toolbox** - compilation of useful algorithms. THIS WORK IS NOT MINE, BUT WAS EITHER MADE BY SAMUEL FERNÁNDEZ MENDUIÑA ([Samuel – About me (sf219.github.io)](https://sf219.github.io/)). DO NOT USE OR SHARE WITHOUT HIS APPROVAL.

---
## How to generate the .mat ENF file (which is the only ENF signal structure used in the rest of the repository).
1. Go to data/*name_of_the_enf_set*/generate_enf_mat.m
2. Set variables **start** and **stop** to the desired beggining and ending sample of the desired fragment. Since the sample frequency for all three current sets is 50 Hz, taking the first hour would mean **start**=1 and **stop**=180000.
3. Run the script (generate_enf_mat.m). The .mat file will be generated in the enf_mat folder

---
## How to execute the *state of the art (SOA)* and *graph signal processing* (GSP) algorithms and generate the figures used in the final year dissertation

1. Go to the scripts folder.
2.  Do the desired changes to the algorithm, that is, to the file that you will run on step 3. (e.g. uncomment the high or low pass filtering or change the .mat file loaded: `load('../data/esp_sync_febrero/enf_mat/enfM_START_STOP.mat','enfM')`)
3. Run either:
	a. geo_2_OR.m for GSP algorithm with one of the spanish sets.
	b. geo_4_WU.m for SOA algorithm with one of the spanish sets.
	c. NORgeo_2_OR.m for GSP algorithm with the nordic set.
	d. NORgeo_4_WU.m for SOA algorithm with the nordic set.

---

## How to execute the link-weights optimizer. This was still work in progress.
1. Go to scripts/find_best_weights.m for the spanish set or scripts/NORfind_best_weights.m for the nordic set. If wanted, change the .mat file to load. The code is the same for both the spanish and nordic scripts, the only difference is on the initial constants.
2. Run it. The result weights will be in the adjacency matrix W.

### Plotting W (optional)
3. Go to Go to scripts/plot_weight_matrix.m for the spanish set or scripts/NORplot_weight_matrix.m for the nordic set. The code is the same for both the spanish and nordic scripts, the only difference is on the initial constants.
4. Run it. The graph overlayed on the map as well as a shortest-path product rule graph will be generated


