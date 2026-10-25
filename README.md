================================================================================
RRD-OCT-Visual-Acuity (Tunisian RRD Cohort)
================================================================================

Pre-operative retinal Optical Coherence Tomography (OCT) images of patients
with Rhegmatogenous Retinal Detachment (RRD), labeled with the patient's final
post-operative visual acuity group (A, B or C).

This collection is part of the Retinal-OCT-Clinical-Dataset (AMD, DME, RRD,
healthy cases) and is intended to support research on predicting
post-operative visual outcome from pre-operative OCT.

--------------------------------------------------------------------------------
1. CLINICAL CONTEXT
--------------------------------------------------------------------------------

Source       : Service A of Ophthalmology, Hedi Raies Institute of
               Ophthalmology, Tunis, Tunisia
Population   : Patients with rhegmatogenous retinal detachment who consulted
               between 2013 and 2020
Cohort size  : 120 patients

Imaging      : OCT, Heidelberg Engineering Spectralis 
Images used  : Pre-operative OCT
Label        : Final post-operative visual acuity group (patient level)

--------------------------------------------------------------------------------
2. LABELS: FINAL VISUAL ACUITY GROUPS
--------------------------------------------------------------------------------

Group   Final visual acuity (decimal scale, /10)   LogMAR
-----   ----------------------------------------   ----------
A       1/100 to 1/10                              2.0 to 1.0
B       1.25/10 to 4/10                            0.9 to 0.4
C       5/10 to 10/10                              0.3 to 0.0

Group A corresponds to the poorest final visual acuity, group C to the best.

Labeling procedure
------------------
For each patient, the treating ophthalmologist determined, after surgery, the
group (A, B or C) corresponding to the patient's final post-operative visual
acuity. The result was recorded in SPSS. These labels (final visual acuity)
were then assigned to the PRE-OPERATIVE OCT images of the same patient, so
that a model can be trained to predict the post-operative visual outcome from
pre-operative imaging.

IMPORTANT: the label is attached to the PATIENT, not to each individual image.
Every image of a given patient inherits the same group.
--------------------------------------------------------------------------------
3. FOLDER STRUCTURE
--------------------------------------------------------------------------------

RRDAnonyme/
|-- groupeA/
|   |-- patient_001/
|   |   `-- <OCT images of this patient>
|   |-- patient_004/
|   `-- ...
|-- groupeB/
|   |-- patient_XXX/
|   `-- ...
`-- groupeC/
    |-- patient_XXX/
    `-- ...

- One folder per group (groupeA, groupeB, groupeC), corresponding to the final
  visual acuity groups above.
- One sub-folder per patient (patient_XXX), containing ALL OCT images of that
  patient.
- Patient identifiers are pseudonymous and numbered across the whole cohort;
  numbering inside a given group is therefore not contiguous.
- Each patient appears in exactly one group.
--------------------------------------------------------------------------------
4. ANONYMIZATION AND ETHICS
--------------------------------------------------------------------------------

- Patient identity has been replaced by pseudonymous identifiers
  (patient_XXX).
- Directly identifying information (names, burned-in text, dates) has been
  removed from images and file names

--------------------------------------------------------------------------------
5. DATA ACCESS
--------------------------------------------------------------------------------

Due to patient confidentiality, institutional regulations and ethical approval
constraints, the dataset is distributed under CONTROLLED ACCESS conditions.

Researchers interested in accessing the dataset for NON-COMMERCIAL scientific
purposes may request access via the official Zenodo repository:

DOI: https://doi.org/10.5281/zenodo.23629205

Access requests are evaluated to ensure compliance with ethical and data
protection requirements. The Data Agreement is available on the project GitHub
repository. Applicants must download the agreement, sign it, and send it by
email to zainab-haddad@hotmail.com. After approval, download access will be granted.

--------------------------------------------------------------------------------
6. INTENDED USE
--------------------------------------------------------------------------------

- Prediction of post-operative visual acuity group from pre-operative OCT
- Multiple Instance Learning (MIL) research, with the patient as a bag and the
  OCT images as instances
- Benchmarking of small-sample medical image classification methods
- Research on medical image analysis and clinical AI

--------------------------------------------------------------------------------
7. LIMITATIONS
--------------------------------------------------------------------------------

- Single-center cohort, small number of patients, no external validation set.
- Class imbalance (group C is the smallest).
- Variable number of images per patient; laterality information may be missing
  for part of the images.
--------------------------------------------------------------------------------
