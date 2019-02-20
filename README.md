# Rock Facies Classification: A Machine Learning Approach with Physics-Motivated Feature Augmentation

Author: Yu (Jason) Zeng  &nbsp; &nbsp;| &nbsp; &nbsp; Email: yu.zeng.duke@gmail.com &nbsp; &nbsp; | &nbsp; &nbsp; Date: Feb. 8, 2019

This notebook contains sample codes to build and train a gradient boosted tree-based model for rock facies classification using geophysical well log data. Our work shows that the inclusion of physics-motivated feature augmentation can further improve the capability of machine learning in rock facies classification. We demonstrate this approach with the SEG 2016 machine learning contest dataset and the top winner's solution. The improvement is roboust and is ~5% better than current existing best F-1 score.

> This work is summarized in a paper entitled **Application of Machine Learning in Rock Facies Classification with Physics-Motivated Feature Augmentation** ([arxiv:1808.09856](https://arxiv.org/abs/1808.09856)) (co-author Jie Chen), and was presented in *2018 SEG Maximizing Asset Value through Artificial Intelligence and Machine Learning Workshop* ([2018 SEG Beijing Workshop](https://seg.org/Portals/0/SEG/Events/AIML_2018/Official_Program_AI_ML.pdf)). 

The main Jupyter notebook is posted here:
> [rock_class_xgboost_seg_fnl.ipynb](rock_class_xgboost_seg_fnl.ipynb)
  * This notebook covers data preparation, data QC, model training, model prediction, conclusion and discussion.
  
A discription of the well log measurements are given by the SEG Machine Learning Contest webpage ([link here](https://github.com/seg/2016-ml-contest)).

Suggestions or comments are welcome!

## 1. Data Loading and QC
QC items include: number of measurements at each well, distribution of facies in all wells, distribution of Resisitivity and distribution of Neutron Density Porosity.

## 2. Investigate relationship between Resistivity and Neutron Density Porosity
Some data exploration.

## 3. Construct new feature based on Archie's equation
We observed strong discrimination power using Archie's equation.

## 4. Feature augmentations
We used same feature augmentation as used in top winner's approach. This will be used as a benchmark for comparison. 

## 5. Model training
For fair comparison, we use the same algorithm (XGBoost) and the same parameters as the top winner to train our model.

## 6. Model prediction
Classification report shows our approach overally improved precision and recall, thus leading to an improved F-1 on test dataset.
A direct visual comparison of true facies and predicted faces, along with well log measurements are shown. Overall, our approach provides a better facies classification than benchmark (top winner approach), resulting in a ~5% improvement in F-1 score.

## 7. Conclusion and discussion
This experimentation shows feature augmentation incorporating domain knowledge can further improve the capability of Machine Learning. There is ultimately no replacement for the insights human beings can put into feature engineering.

Currently, the dataset we use only contains limited number of physical attributes. To further improve in future rock facies classiﬁcation tasks, additional types of well log measurements, including Vp, Vs, density etc., if provided, will probably further enhance machine learning’s capability in achieving better accuracy. For example,Vp/Vs is directly related to the Poisson’s ratio (Gercek, 2007), which measures the ratio of lateral strain to axial strain in a rock and can be served as another distinctive discriminator in facies classiﬁcation.

