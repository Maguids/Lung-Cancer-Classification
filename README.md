# Lung Cancer Classification

This project was developed for the "Artificial Intelligence and Data Science Laboratory" course and aims to **correctly classifiy lung cancer using computed tomography (CT) data**. First Semester of the Third Year of the Bachelor's Degree in Artificial Intelligence and Data Science.

<br>

## Requirements:

	- Python 
	- Numpy -> version ~= 1.19.5
	- Matplotlib -> version ~= 3.4.3 
	- Pandas -> version ~= 1.3.5
	- Pylidc -> version ~= 0.2.3
	- Pydicom -> version ~= 2.0.0
	- Pyradiomics -> version = v3.0.1
	- Scikit-image
	- Scipy
	- Scikit-learn
	- Seaborn
	- SimpleITK
	- opencv-python (cv2)
	- Xgboost
	- Pyswarm
	- Statsmodel

<br>

## The Project
The proposed project consists on **the classification of pulmonary nodules**, through detailed data analysis and implementation of AI models, **using computed tomography (CT) images**. The **data used comes from the LIDC-IDRI dataset**, available at https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI. Throughout this project, solutions will be proposed for its analysis and processing, **based on studies and projects already carried out in the area**, which are referenced throughout the document. The **classification of pulmonary nodules will be performed using different techniques and algorithms**, which will **be compared and evaluated** in order to determine which model best suits the proposed problem.

<br>

### The Dataset:
As previously stated, the dataset used in this project was taken from the following link:
https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI
This will give you access to several files, from csv files with information about diagnoses, the number of nodules in each patient, notes about the nodules, to CT scans.

After **analyzing the various files**, we realized that some of them were **irrelevant**, so we ended up **extracting data directly from the CT scans using <u>pylidc</u>** and comparing them with the csvs in order to understand whether the information was consistent or not, but this entire process is explained in the project.

<br>

### Image Pre-Processing and Feature Extraction 
To extract the required data from the displayed images, we used Pyradiomics. Howerver, before extracting its features, we need to prepare the images by standardizing them to **Hounsfield Units (HU)** and then **normalizing** them. 

In this project we decided to extract 2d and 3d features and compare them. In order to do so, we had to segmentate the images accordingly:
- 2D Segmentation: We use only one slice, which is obtained from the centroid of the nodule.

<p align="center">
  <img width="700" height="350" src="https://github.com/user-attachments/assets/6c0d3b57-53c0-4a1d-9d0f-0e542141cb4b">
</p>

- 3D Segmentation: For three-dimensional (3D) images, we use multiple slices of CT scans. These images contain information in three dimensions (x, y and z), resulting in a volumetric representation of the objects.

<p align="center">
  <img width="700" height="500" src="https://github.com/user-attachments/assets/f43f1c7c-7136-4024-bfd0-bb4dd6ecfbec">
</p>

<br>

### Models and Results Comparison
Once we had the features, we decided to use different models and feature selection, using the following:

**Models:**
- Support Vector Machine (SVM)
- Random Forest
- XGBoost 

**Feature Selection**
- Without feature selection
- PCA
- T-test
- Random Forest for feature selection

We tested each kind of the feature selections above in every proposed model for 2D and 3D features. In order to then understand which was the best approach we made the following tests and comparisons:
- **Comparison between different models for the same feature selection method**: to do so we used the ANOVA test and Tukey's Multiple Comparisons Test (Post Hoc);
- **Comparison between different feature selection methods for the same classification model**: to do so we used the ANOVA test and Tukey's Multiple Comparisons Test (Post Hoc);
- **Comparison between 2D and 3D:** to do so we used Paired samples t-test;

<br>

## About the repository:

- datasets ➡️ Folder with the created datasets;
- Extração_Dados_Pylidc.ipynb ➡️ Jupyter Notebook with the code used to extract data from the CT scans; 
- Implicações éticas e legais no diagnóstico de cancros de pulmão.pdf ➡️ Is a pdf file that debates the ethical and legal implications of using AI in lung cancer detection;
- Lab_IACD_Project1.pdf ➡️Project statement
- T1_LabIACD_Project1.pdf ➡️ More information on how to develop the project;
- Project.ipynb ➡️ The project in jupyter notebook format;
- notebook.pdf ➡️The project in pdf format.

<br>

## Link to the course: 

This course is part of the **<u>first semester</u>** of the **<u>third year</u>** of the **<u>Bachelor's Degree in Artificial Intelligence and Data Science</u>** at **<u>FCUP</u>** and **<u>FEUP</u>** in the academic year 2024/2025. You can find more information about this course at the following link:

<div style="display: flex; flex-direction: column; align-items: center; gap: 10px;">
  <a href="https://sigarra.up.pt/fcup/pt/ucurr_geral.ficha_uc_view?pv_ocorrencia_id=529878">
    <img alt="Link to Course" src="https://img.shields.io/badge/Link_to_Course-0077B5?style=for-the-badge&logo=logoColor=white" />
  </a>

  <div style="display: flex; gap: 10px; justify-content: center;">
    <a href="https://sigarra.up.pt/fcup/pt/web_page.inicial">
      <img alt="FCUP" src="https://img.shields.io/badge/FCUP-808080?style=for-the-badge&logo=logoColor=grey" />
    </a>
    <a href="https://sigarra.up.pt/feup/pt/web_page.inicial">
      <img alt="FEUP" src="https://img.shields.io/badge/FEUP-808080?style=for-the-badge&logo=logoColor=grey" />
    </a>
  </div>
</div>
