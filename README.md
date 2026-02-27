# Outdoor PV and ambient measurement data

Accompanying repository for the submitted dataset for Good Datasets for AI Model Training in the Power and Energy Domain Competition. 

---

## Overview
This dataset provides outdoor measurements of photovoltaic (PV) modules representing multiple commercial PV technologies, along with synchronized environmental and operational parameters. The dataset is intended to support AI model training, benchmarking, and validation for power and energy system applications, including PV modeling, performance prediction, fault detection and maximum power point tracking (MPPT).

## 📂 Project Organization

### Data Processing
- **RawToCSV.ipynb**: Notebook showcasing the process and decisions taken for converting raw I-V curves and ambient measurements to a single CSV file.
- **Dataset Curation.ipynb**: Notebook showcasing the filters used to eliminate extreme outliers and/or measurement errors. 

### Data Visualization
- **Data Visualization.ipynb**: Notebook with examples of visualization for the dataset.
- **figures**: Folder with figures from Datset Curation and Data Visualization.

### Examples
- **Module Temperature Predictor.ipynb**: Notebook with an example application to estimate module temperature based on ambient variables. Comparision of different ML techniques and the NOCT baseline.
- **Power Output Predictor.ipynb**:  Notebook with an example application to estimate module power output based on electrical and ambient variables. Comparision of different ML techniques and a formula baseline.

## License

This dataset is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

The data were collected within the MatER Research Group at the Pontificia Universidad Católica del Perú (PUCP). Users are free to share and adapt the data for any purpose, including research and commercial use, provided appropriate credit is given to the original authors and source.

