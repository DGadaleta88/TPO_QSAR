# QUANTITATIVE STRUCTURE-ACTIVITY RELATIONSHIP MODELING OF THE AMPLEX ULTRARED (AUR) ASSAY TO PREDICT TYROPEROXIDASE INHIBITORY ACTIVITY

Quantitative structure-activity relationship (QSAR) models to predict the TPO inhibitory potential of chemicals are presented. 

## TECHNICAL DETAILS

### DATA SOURCE
1. TPO inhibition data used to develop the QSAR models were retrieved from ToxCast (DOI: 10.1093/toxsci/kfw034). Data are related to the Amplex UltraRed-thyroperoxidase (AUR-TPO) assay (DOI: 10.1021/tx400310w). 
2. A selectivity (SEL) value was associated to positive hit-calls. SEL values were used to stratify active TPO inhibitors in non-selective (NSE) (i.e., SEL <0), low selective (LSE) (0≤ SEL <1) and high selective (HSE) (SEL ≥1).
3. Models were based only on HSE (153) and inactive (751, INA) samples.

### QSAR DETAILS
Two models are proposed, based on Dragon (v7.0.8) descriptors and two different algoritms:

1. **k-Nearest Neighbors**: based on 20 selected variables and the Syntetic Minority Oversampling Technique (SMOTE) (DOI: 10.1613/jair.953)
2. **Random Forest**: based on 160 selected variables. Undersampling was iteratively applied to samples in the majority category to account for inbalanced data.

## HOW TO USE THE MODELS

### REQUIREMENTS AND INSTALLATION
Python 3 should be installed with the following dependencies:

- sci-kit_ learn 0.23
- rdkit
- pandas
- numpy
- imbalanced-learn

It is possible to create a RDKit Python environmet fromt the Conda prompt, as follow:

```
conda activate my-rdkit-env
pip install -U scikit-learn
pip install --upgrade scikit-learn
conda install -c conda-forge imbalanced-learn

```
then select the new environment in KNIME (*File -> Preferences -> Path to Python 3 executable...*)

### SETTING PREFERENCES
1. Double click on the Metanode.
2. Select to predict 1) a single compound or 2) a list of compounds (batch).
3a. In case of a single compound, insert the SMILES in the field 'Single prediction'.
3b. In case of batch calculation, select the path of the input file in .xlsx format. The file should include two column, with the SMILES list ('SMILES') and the identifiers ('ID'). The coulmns should include headers named as above.
4. Specify if you have a Dragon licence or not (see the right box for details)

### DRAGON LICENCE
A. *The user has a Dragon licence:* 

1) Download the Dragon node (https://chm.kode-solutions.net/products_dragonknime.php). The node can be installed by copy-pasting the downloaded file in the "dropins" folder in the installation directory of KNIME

2) Modify the settings (executable location) by double-clicking on the metanode

3) Run the workflow

B. *The user does not have a Dragon licence:*

1) Load the spreadsheet with SMILES including additional columns with descriptors calculated previously in the Excel Reader. 1) ID column and 2) SMILES column should be included in this order. This option is only possible in case of batch calculation.

2) Run the workflow

## REFERENCE
Further details on the algorithms and on the statistical performance of models can be found in the reference pubblication:

Gadaleta, D., D'Alessandro, L., Marzo, M., Benfenati, E., Roncaglioni, A. (2020). Quantitative Structure-Activity Relationship Modeling Of The Amplex Ultrared (Aur) Assay To Predict Tyroperoxidase Inhibitory Activity. Submitted manuscript.

## CONTACT
Domenico Gadaleta, PhD

Computational Toxicology Unit

Laboratory of Environmental Chemistry and Toxicology

Department of Environmental Health Sciences

Istituto di Ricerche Farmacologiche Mario Negri IRCCS 

Via Mario Negri 2, 20156 Milano, Italy 

e-mail: domenico.gadaleta@marionegri.it

