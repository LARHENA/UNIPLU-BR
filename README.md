# UNIPLU-BR
Unified Brazilian Rainfall Dataset (UNIPLU-BR): A Standardized National Database of Point Precipitation from Major Brazilian Monitoring Networks (1885 – 2025)

Filipe Carvalho Lemos, Emerson da Silva Freitas, Victor Hugo Rabelo Coelho, Dirceu Silveira Reis Júnior, Eduardo Gonçalves Patriota, Marcela Antunes Meira, José Lindemberg Vidal-Barbosa, Cinthia Maria de Abreu Claudino, Gerald Souza da Silva, Daniel Conceição do Nascimento, Geraldo Moura Ramos Filho, Ana Paula Martins do Amaral Cunha, Luna Gripp Simões Alves, Luis Marcelo de Mattos Zeri, Germano Gondim Ribeiro Neto, Guillaume Francis Bertrand, Javier Tomasella, Saulo Aires de Souza, Alexandre Abdalla Araújo, Cássio Guilherme Rampinelle, Cristiano das Neves Almeida

This dataset is the first unified and standardized national database of point precipitation (non-interpolated) in Brazil, consolidating raw data from five primary monitoring networks:
  1.	CEMADEN: National Center for Monitoring and Early Warning of Natural Disasters.
  2.	INMET: National Institute of Meteorology.
  3.	ANA (Hidroweb): National Water and Sanitation Agency.
  4.	Telemetria: Telemetry system for hydrological monitoring.
  5.	ICEA: Institute of Air Space Control.

The primary contribution of this work is overcoming the high fragmentation of rainfall data in Brazil through a rigorous curation process:
•	Structural and Nominal Standardization: Harmonization of column names, attributes, and storage formats, addressing historical changes in data protocols and formats within the same agency.
•	Time Zone Adjustment: Standardization of timestamps based on the station's geographical location (UTC offset).
•	Temporal Resolution: Records ranging from 10-minute intervals to 1-day resolution.
Data Quality Disclaimer: The processing of this dataset is strictly focused on structural standardization. No qualitative assessment, physical consistency checks, or outlier filtering were performed. The rainfall values remain as originally reported by the agencies, now organized into a unified, analysis-ready structure.

Data Quality Disclaimer: The processing of this dataset is strictly focused on structural standardization. No qualitative assessment, physical consistency checks, or outlier filtering were performed. The rainfall values remain as originally reported by the agencies, now organized into a unified, analysis-ready structure.


Impressive numbers:
The dataset covers the period from 1885 to 2025, highlighted by the presence of stations with historical series exceeding a century. With broad national coverage, the database consolidates approximately 2.2 billion precipitation records from over 21,000 stations. This information features varied temporal resolutions, ranging from 10-minute intervals to 24-hour totals. 
The distribution of these records among the main Brazilian monitoring networks is detailed below.


### Resumo das Fontes de Dados

| Fonte | Média de Anos (Potencial) | Quantidade | Período (Início - Fim) |
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
