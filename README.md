RADAR
=======================

En este espacio se encontrara una introdución a los principios y aplicaciones de la detección remota por microondas. 
Incluye la tecnología de sensores, plataformas y portales de datos para recuperar datos. Se cubrirán las principales técnicas de procesamiento y las aplicaciones de datos de sensores remotos de microondas activos y pasivos


_**Principios básicos**_ 
* Introducción
  * Follow these [INSTALLATION](INSTALLATION.md) instructions to set up EBD's *openSAR*
* Historia del Radar 
* Conceptos matematicos

_**Sistemas de Radar**_ 



_**Conceptos avanzados**_ 



_**Aplicaciones**_ 








[Documentation](https://coded.readthedocs.io/en/latest/)



# openSAR
EARTH BIG DATA's open source repository for Synthetic Aperture Radar Image Processing. 

* Installation Instructions
  * Follow these [INSTALLATION](INSTALLATION.md) instructions to set up EBD's *openSAR*
  * [InstallationTest.ipynb](notebooks/InstallationTest.ipynb) is a notebook to test the installation
  * [testdata.zip](data/testdata.zip) are data to use with the installation test notebook
  * [conda_ebd.yml](conda_ebd.yml) is the conda environment file to use with the instructions (Experts can just go ahead and use this with conda.)
  
* notebooks
  * Collection of Jupyter [notebooks](notebooks) around all things SAR

* Data documentations
  * EBD SAR Time Series [Data Guide](documentation/EBD_DataGuide.md)

* Open source code
  * EBD SAR Time Series Plotting Tool as a [QGIS Plugin](code/QGIS/plugins/)

* Training
  * Material and Instructions for EBD [Training](training) Courses



# Continuous Degredation Detection (CODED)

CODED is an algorithm developed to monitor for low-magnitude forest disturbances using Landsat data. The algorithm is based upon previous developments in continuous land cover monitoring [(Zhu and Woodcock, 2014)](http://www.sciencedirect.com/science/article/pii/S0034425714000248) and tropical degradation monitoring using spectral unmixing models [(Souza et al., 2013)](http://www.mdpi.com/2072-4292/5/11/5493/html) and is built upon the [Google Earth Engine](https://earthengine.google.com/) processing and data storage system. CODED is designed to create a stratification for sample-based estimation of degraded forests. 

An updated repository with Javascript code to run the algorithm can be found [here](https://code.earthengine.google.com/?accept_repo=users/bullocke/coded). 

[Documentation](https://coded.readthedocs.io/en/latest/)
