# UNIPLU-BR
Unified Brazilian Rainfall Dataset (UNIPLU-BR): A Standardized National Database of Point Precipitation from Major Brazilian Monitoring Networks (1885 – 2025)

Filipe Carvalho Lemos, Emerson da Silva Freitas, Victor Hugo Rabelo Coelho, Dirceu Silveira Reis Júnior, Eduardo Gonçalves Patriota, Marcela Antunes Meira, José Lindemberg Vidal-Barbosa, Cinthia Maria de Abreu Claudino, Gerald Souza da Silva, Daniel Conceição do Nascimento, Geraldo Moura Ramos Filho, Ana Paula Martins do Amaral Cunha, Luna Gripp Simões Alves, Luis Marcelo de Mattos Zeri, Germano Gondim Ribeiro Neto, Guillaume Francis Bertrand, Javier Tomasella, Saulo Aires de Souza, Alexandre Abdalla Araújo, Cássio Guilherme Rampinelli, Cristiano das Neves Almeida

This dataset is the first unified and standardized national database of point precipitation (non-interpolated) in Brazil, consolidating raw data from five primary monitoring networks:
  1.	**CEMADEN**: National Center for Monitoring and Early Warning of Natural Disasters.
  2.	**INMET**: National Institute of Meteorology.
  3.	**ANA (Hidroweb)**: National Water and Sanitation Agency.
  4.	**Telemetria**: Telemetry system for hydrological monitoring.
  5.	**ICEA**: Institute of Air Space Control.

The primary contribution of this work is overcoming the high fragmentation of rainfall data in Brazil through a rigorous curation process:

<p>•	Structural and Nominal Standardization: Harmonization of column names, attributes, and storage formats, addressing historical changes in data protocols and formats within the same agency.
<p>•	Time Zone Adjustment: Standardization of timestamps based on the station's geographical location (UTC offset).
<p>•	Temporal Resolution: Records ranging from 10-minute intervals to 1-day resolution.


**Data Quality Disclaimer**: The processing of this dataset is strictly focused on structural standardization. No qualitative assessment, physical consistency checks, or outlier filtering were performed. The rainfall values remain as originally reported by the agencies, now organized into a unified, analysis-ready structure.


#### Impressive numbers:

The dataset covers the period from 1885 to 2025, highlighted by the presence of stations with historical series exceeding a century. With broad national coverage, the database consolidates approximately 2.2 billion precipitation records from over 21,000 stations. This information features varied temporal resolutions, ranging from 10-minute intervals to 24-hour totals. 
The distribution of these records among the main Brazilian monitoring networks is detailed below.

| Source | Potential average number of years | Quantity | Initial and Final Year |
| :--- | :---: | :---: | :---: |
| CEMADEN | 7,99 | 5.061 | 2014 - 2025 |
| Hidroweb | 32,38 | 12.087 | 1885 - 2025 |
| ICEA | 33,19 | 183 | 1951 - 2025 |
| INMET daily | 45,03 | 627 | 1889 - 2025 |
| INMET sub-daily | 15,87 | 629 | 2000 - 2025 |
| Telemetria | 6,63 | 2.819 | 2014 - 2025 |
| **Total** | **—** | **21.406** | **—** |

<p align="left">
  <img src="https://github.com/LARHENA/UNIPLU-BR/blob/main/img/Imagem1.png?raw=true" alt="Spatial distribution of the rainfall gauge stations in Brazil across different data sources" width="650">
  <img src="https://github.com/LARHENA/UNIPLU-BR/blob/main/img/Imagem2.png?raw=true" alt="Temporal evolution of the number of available rainfall stations in Brazil from 1855 to 2025: (Top) stations with daily resolution; (Bottom) stations with sub-daily resolution." width="650">
</p>


**Accessing the Data**

The data is stored in compressed ZIP files, which function as optimized containers. Each ZIP file internally contains two files in Parquet format: table_info.parquet (station metadata) and table_data.parquet (rainfall time series).
The primary advantage of this structure is that, using Python or R, you can read the data directly from memory. This eliminates the need to manually decompress files to the disk, saving storage space and accelerating processing within automation workflows.
Within these files, the gauge_code (station code) serves as the primary key that links the registration information to the measurement data.


**Metadata**


*Rainfall gauge information (table_info)*

This dataframe functions as the 'identity document' for the rain gauge stations. It contains the static characteristics of each monitoring point:

| COLUMN | DESCRIPTION |
| :--- | :---: | 
| **gauge_code** | Unique station identifier (ID). This serves as the link to table_data | 
| **city / state** | The administrative location of the station (e.g. João Pessoa, PB) | 
| **lat / long** | Geographic coordinates in decimal degrees | 
| **elevation** | The station's altitude above mean sea level (meters) | 
| **time_step** | Estimated temporal resolution of the data (1440 minutes = 24 hours/daily) |
| **network** | Data network source (e.g. Hidroweb) |
| **responsible** | The agency responsible for operations (ANA or SGB-CPRM) |
| **utc** | Local time zone relative to the Greenwich Meridian (-3 for Brasília Time) |


*Time Series (table_data)*

Whilst table_info defines the location and identity of the station, table_data records the rainfall measurements. It contains the following columns:

| COLUMN	| DESCRIPTION | 
| :--- | :---: | 
| **gauge_code**	| Unique station identifier (ID). This serves as the link to table_info | 
| **datetime**	| The date and time of the reading | 
| **rain_mm**	| The volume of precipitation recorded during that interval, measured in millimeters (mm) |


*Script Examples*

Examples of scripts for accessing and filtering data, as well as generating plots, can be found at the following link: https://github.com/LARHENA/UNIPLU-BR/blob/main/Scripts%20UNIPLU-BR.ipynb



**How to Cite**

Lemos, F. C., Freitas, E. S., Coelho, V. H. R., Reis Júnior, D. S., Patriota, E. G., Meira, M. A., Vidal-Barbosa, J. L., Claudino, C. M. A., Silva, G. S., Nascimento, D. C., Ramos Filho, G. M., Cunha, A. P. M. A., Alves, L. G. S., Zeri, L. M. M., Ribeiro Neto, G. G., Bertrand, G. F., Tomasella, J., Souza, S. A., Araújo, A. A., Rampinelle, C. G., & Almeida, C. N. (2026). Unified Brazilian Rainfall Dataset (UNIPLU-BR): A Standardized National Database of Point Precipitation from Major Brazilian Monitoring Networks [Data set]. Zenodo. https://doi.org/10.5281/zenodo.18883358


**Main papers published by the group**

Das Neves Almeida, C., Francis Bertrand, G., Carvalho Lemos, F., da Silva Freitas, E., Lins Silva, A., Vidal Barbosa, J. L., ... & Coelho, V. H. R. (2025). The design of the Brazilian Sub-Daily Rainfall dataset (BR-SDR): two decades of high-time-resolution data in Brazil. Hydrological Sciences Journal, 70(11), 1850-1862. https://doi.org/10.1080/02626667.2025.2506193

Vidal-Barbosa, J. L., Lemos, F. C., da Silva Freitas, E., Coelho, V. H. R., da Silva, G. N. S., Patriota, E. G., ... & das Neves Almeida, C. (2025). BRain-D: A quality-controlled methodology for constructing the BRazilian Daily rainfall gridded data. Atmospheric Research, 108552. https://doi.org/10.1016/j.atmosres.2025.108552

Freitas, E. D. S., Coelho, V. H. R., Bertrand, G. F., Lemos, F. C., & Almeida, C. D. N. (2024). IMERG BraMaL: An improved gridded monthly rainfall product for Brazil based on satellite‐based IMERG estimates and machine learning techniques. International Journal of Climatology, 44(11), 3976-3997. https://doi.org/10.1002/joc.8562

Lemos, F. C., Coelho, V. H. R., Freitas, E. D. S., Tomasella, J., Bertrand, G. F., Meira, M. A., ... & Almeida, C. D. N. (2023). Spatiotemporal distribution of precipitation and its characteristics under tropical atmospheric systems of Brazil: Insights from a large sub‐hourly database. Hydrological Processes, 37(11), e15017. https://doi.org/10.1002/hyp.15017

Ramos Filho, G. M., Coelho, V. H. R., da Silva Freitas, E., Xuan, Y., Brocca, L., & das Neves Almeida, C. (2022). Regional-scale evaluation of 14 satellite-based precipitation products in characterising extreme events and delineating rainfall thresholds for flood hazards. Atmospheric Research, 276, 106259. https://doi.org/10.1016/j.atmosres.2022.106259

Meira, M. A., Freitas, E. S., Coelho, V. H. R., Tomasella, J., Fowler, H. J., Ramos Filho, G. M., ... & Almeida, C. D. N. (2022). Quality control procedures for sub-hourly rainfall data: An investigation in different spatio-temporal scales in Brazil. Journal of Hydrology, 613, 128358. https://doi.org/10.1016/j.jhydrol.2022.128358

Freitas, E. D. S., Coelho, V. H. R., Xuan, Y., de CD Melo, D., Gadelha, A. N., Santos, E. A., ... & Almeida, C. D. N. (2020). The performance of the IMERG satellite-based product in identifying sub-daily rainfall events and their properties. Journal of Hydrology, 589, 125128. https://doi.org/10.1016/j.jhydrol.2020.125128


