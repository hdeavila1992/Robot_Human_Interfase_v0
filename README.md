# Robot_Human_Interfase

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

This project focuses on classifying Electromyography (EMG) signals acquired using an OpenBCI device at the LAM laboratory at Simón Bolívar University. The data was collected in a single continuous session, with each phase recorded for a specific duration: a 2-minute baseline state, followed by 1-minute intervals for forward neck movement, backward neck movement, right neck movement, left neck movement, and a state of resting thought. The goal is to develop an AI model capable of classifying these distinct states, enabling it to recognize a person's intended movement when the experiment is replicated

### How to Interpret the Data
Time is crucial here; what matters is how the experiment evolves.

- Basal state: 2 minutes (120 seconds) [0:120]
- Right state: 1 minute (60 seconds) [120:180]
- Center state: 1 minute (60 seconds) [180:240]
- Left state: 1 minute (60 seconds) [240:300]
- Center state: 1 minute (60 seconds) [300:360]
- Forward state: 1 minute (60 seconds) [360:420]
- Center state: 1 minute (60 seconds) [420:480]
- Backwards state: 1 minute (60 seconds) [480:540]
- Rest state: 2 minutes (120 seconds) [540:660]

so is importan to split data frame in correct fase. 

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         Robot_Human_Interfase_m0 and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── Robot_Human_Interfase_m0   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes Robot_Human_Interfase_m0 a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

## Algunos MWT:

Familia de Wavelet (Ejemplo)	Propiedades Clave	Ventajas	Desventajas	Aplicación EEG/BCI Típica
Daubechies (db4)	Ortogonal, Asimétrica, Soporte compacto	Eficiencia computacional, buena para detectar discontinuidades	La asimetría puede introducir distorsión de fase	
Descomposición DWT para extracción de características (energía, entropía) en MI y P300    

Symlets (sym9)	Ortogonal, Casi simétrica, Soporte compacto	Baja distorsión de fase, propiedades similares a Daubechies	Ligeramente mayor coste computacional que dbN	
Análisis DWT donde la preservación de la forma de la onda es importante    

Morlet	No ortogonal, Compleja, Soporte infinito	Excelente localización tiempo-frecuencia, forma similar a ritmos neuronales	Reconstrucción no perfecta, mayor coste computacional	
Análisis CWT para generar escalogramas como entrada para redes neuronales convolucionales (CNNs)    

Biorthogonal (bior2.4)	Biorthogonal, Simétrica, Fase lineal	Reconstrucción perfecta con filtros de fase lineal, flexibilidad en el diseño	No son estrictamente ortogonales	
Procesamiento y reconstrucción de imágenes y señales donde la fase es crítica    

Coiflets (coif1)	Ortogonal, Casi simétrica, Momentos de desvanecimiento para la función de escala	Buen equilibrio entre soporte compacto y momentos de desvanecimiento	Menos opciones de orden que Daubechies/Symlets	
Aplicaciones de descomposición DWT que requieren un buen compromiso de propiedades  1    
