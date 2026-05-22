# Anomaly Detection in the Industrial Robotic Arms by leveraging Digital Twin and Explainable AI


## General info
The video below provides a brief overview of the proposed framework and a demonstration of the simulation.



https://github.com/h1548782/seleniumforest/assets/137823205/8cd7ae02-ea2a-4209-8dcb-6ee301cc4f49




	
## Technologies
The project is created with:
* Python 3.7.9

  Other Python versions caused dependency errors during module installation. Therefore, We recommend using 3.7.9.

* Microsoft Azure - Digital Twin Platform

* Microsoft Visual Studio Code IDE

## Data set
The data set (_right_arm_.csv) used during the simulation can be accessed under the following link:
https://www.kaggle.com/datasets/hkayan/industrial-robotic-arm-anomaly-detection

	
## Setup
To run this project, install the following modules locally by using pip or your package manager of choice:

```
%pip install shap
%pip install numpy
%pip install pandas
%pip install pyspark
%pip install matplotlib
%pip install azure.identity
%pip install azure.digitaltwins.core
```

In addition to an active Microsoft Azure account, the Microsoft Azure CLI is also necessary. It can be downloaded here:

[Azure CLI](https://ojuliuscoder.medium.com/installing-and-using-azure-cli-in-visual-studio-code-a382d2b09bfa)

Ensure the correct Digital Twin schema is set up on the Azure platform. Otherwise, parts of the code will not run properly. To set it up, use _digital-twin-schema.json_ in the upload model section. It already contains the five necessary sensor components to simulate a robotic arm.

## Algorithm Description

### Python Scripts

#### _digital_twin_azure.py_
This script contains all steps related to the Digital Twin instance on the Microsoft Azure platform. It contains a function to connect via the browser, gather available twin information, and, lastly, a function to send data to the Digital Twin. The script also includes the code for plotting a dashboard-like monitoring system. The system will display the current workload of the robotic arm´s components and the current anomaly state. Furthermore, it includes a visual alarm to display anomaly occurrences.

#### _anomaly_detection.py_
This file contains all the code necessary to train a prediction model and, furthermore, predict local instances. The function train_model() will create a random forest model, based on the provided input. Additionally, it will display the achieved accuracy score and show a confusion matrix. predict_model() can then be used to predict the anomaly state for current instances. 

#### _predictive_maintenance.py_
This script focuses on predictive maintenance. By using SHAP and its benefits for explainability in machine learning algorithms, the causes of anomalies can be pinpointed and countermeasures initiated. Here is an example for the generated SHAP beeswarm plot for the SHAP values of all predicted anomalies. Dots marked in red display high feature values, whereas those marked in blue display low feature values. 

Furthermore, it contains code for a SHAP partial dependence plot. That way, specific features can be analyzed in greater detail, providing deeper insight into the prediction process.


### Simulation
#### _simulation_robotic_arm.ipynb_
The scripts mentioned above are used to run simulations of a robotic arm in motion. The main notebook for this purpose is the simulation_robotic_arm.ipynb jupyter file. It imports the predefined functions from all of the available Python scripts. A detailed description of each function can be found within the script files.




## License agreement
This repository is copied from: https://github.com/h1548782/seleniumforest. The applied license can be found here:
[MIT License](https://github.com/h1548782/seleniumforest/blob/main/MIT-LICENSE.txt)
