# MIAU 

*Florencia Grattarola <a dir="ltr" href="http://orcid.org/0000-0001-8282-5732" target="_blank"><img class="is-rounded" src="https://upload.wikimedia.org/wikipedia/commons/0/06/ORCID_iD.svg" width="15"></a>, Kateřina Tschernosterová, Petr Keil*

## An analysis-ready dataset on presence-only and presence-absence data of Neotropical carnivores (Mammalia: Carnivora) from 2000 to 2021

In the last decade, databases of records of species observed at the same location at different points in time over large spatial extents have been made available. Unfortunately, these sources are scarce in regions such as Latin America. We present a dataset of 60,179 point occurrences (i.e. presence-only data, PO) and 45,468 camera trap survey records (i.e. presence-absence data, PA) for 63 species of carnivores of the Neotropical region from 2000 to 2021. We collated the data from various sources, including 64 newly digitised bibliographic references. We cleaned, taxonomically harmonised, and standardised the data following the Darwin Core and Humboldt Core standards and present them here as csv files. We have also made these data fit for analyses by aggregating the data into two time periods (time1: 2000-2013 and time2: 2014-2021), with PO grid cell counts of 100 x 100 km, and PA polygons of varying size, presented as geopackage files. These data can be used for large-scale species distribution models, calculation of population trends, extinction risk analyses, and educational purposes.

--- 

**Disclaimer**: As the project has ended, we do not plan to update the dataset soon. However, with our data structure description, detailed data cleaning and standardisation workflow, and code available, we encourage future users to update the dataset as needed. 

## 1) **Source data**: the downloaded/digitised data sources

- 64 literature sources. See the files [`literature_all_references.ods`](metadata/literature_all_references.ods) for a complete list and [`literature_digitised_references.bib`](metadata/literature_digitised_references.bib) for the *BibTeX* bibliographical database.

- GBIF.org. (2024). 'Occurrence Download Neotropical Carnivores'. <https://doi.org/10.15468/dl.67zvau>. 

- Nagy-Reis et al. (2020). 'NEOTROPICAL CARNIVORES: A Data Set on Carnivore Distribution in the Neotropics'. *Ecology* 101(11): e03128. <https://doi.org/10.1002/ecy.3128> 

## 2) **Underlying data**: the data we generated


### Tables
- [`data/data_PO.csv`](data/data_PO.csv): a csv file with the cleaned, standardised and harmonised presence-only data.
- [`metadata/metadata_PO.csv`](metadata/metadata_PO.csv): a csv file with the column names, standard terms (e.g., [Darwin Core](https://dwc.tdwg.org) or [Humboldt Core](https://eco.tdwg.org)), and definitions for the presence-only data.

- [`data/data_PA.csv`](data/data_PA.csv): a csv file with the cleaned, standardised and harmonised presence-absence data.
- [`metadata/metadata_PA.csv`](metadata/metadata_PA.csv): a csv file with the column names, standard terms (e.g., [Darwin Core](https://dwc.tdwg.org) or [Humboldt Core](https://eco.tdwg.org)), and definitions for the presence-absence data.

- [`data/carnivores.csv`](data/carnivores.csv): a csv file with the carnivore species' list extracted from the [Mammal Diversity Database](https://doi.org/10.5281/zenodo.5945626), including the family, taxon key from GBIF and IUCN conservation status.

### Spatial files

- [`data/PO.gpk`](data/PO.gpk): a geopackage with 2 layers; `time1`: a multi polygon sf file with 2,265 grid cells of 100 x 100 km resolution with counts per species in the temporal period from 2000 to 2013, and `time2`: a multi polygon sf file with 2,265 grid cells of 100 x 100 km resolution with counts per species in the temporal period from 2014 to 2021. Projection: Lambert azimuthal equal-area projection; centre latitude 0°S and centre longitude 73.125°W. 

- [`data/PA.gpk`](data/PA.gpk): a geopackage with 2 layers; `time1`: a multi polygon sf file with 565 varying size polygons of presences/absences values for each species, area of the polygon, and sampling effort in days in the temporal period from 2000 to 2013, and `time2`: a multi polygon sf file with 1013 varying size polygons of presences/absences for each species  in the temporal period from 2014 to 2021, with the area of the polygon and sampling effort in days. Projection: Lambert azimuthal equal-area projection; centre latitude 0°S and centre longitude 73.125°W.  

- [`data/latam.gpk`](data/latam.gpk): a geopackage with 4 layers; `countries`: a multi polygon sf file for all 27 Latin American countries, `countries_land` a multi polygon sf file for the 21 landmass countries of Latin America (excluding islands), `latam` a single polygon that combines all the landmass countries of Latin America, and `latam_grids` a multi polygon sf file with 2,265 grid cells of 100 x 100 km resolution and `latam` as extension. Projection: Lambert azimuthal equal-area projection; centre latitude 0°S and centre longitude 73.125°W.

### Other files

- [`metadata/literature_digitised_references.bib`](metadata/literature_digitised_references.bib): BibTeX bibliographical database file with the 64 literature references digitised and included in our database. 

- [`literature_digitised_references.csv`](metadata/literature_digitised_references.csv): a csv file with the 64 literature references digitised and included in our database.

- [`metadata/literature_all_references.ods`](metadata/literature_all_references.ods): an open-source spreadsheet file with literature references (title and DOI or URL) including 4 sheets; `articles_EXCLUDED` articles that did not fulfil our assumptions and were excluded (reasons are reported in the column notes), `articles_DUPLICATED`: articles that were found in the reference lists of other datasets already digitised (e.g. Nagy-Reis et al., 2019), `articles_DIGITISED` articles that were digitised and included in the data, and `articles_TO_PROCESS`: articles that fulfil our assumptions but were not digitised.  


## 3) **Extended Data**: the code we used to process the data

- [`code/sources_species_and_countries.qmd`](code/sources_species_and_countries.qmd): an overview of the different sources, carnivore species and countries considered in the study.
- [`code/presence-absence.qmd`](code/presence-absence.qmd): an overview of the presence-absence records in the database, including the geographic, taxonomic and temporal coverage of the data.
- [`code/presence-only.qmd`](code/presence-only.qmd): an overview of the presence-only records in the database, including the geographic, taxonomic and temporal coverage of the data. 
- [`code/analysis_ready_data.qmd`](code/analysis_ready_data.qmd): a full descriptive code to reproduce the generation of `PO.gpk` and `PA.gpk`.

## LICENCE

**Data** are available under the terms of the Creative Commons Attribution 4.0 International licence CC-BY 4.0 (https://creativecommons.org/licenses/by/4.0/legalcode.en).   

**Code** is available under the terms of the GPL-3.0 licence (https://www.gnu.org/licenses/gpl-3.0.html). 

## CITATION

> Grattarola F., Tschernosterová K., & Keil P. (2024); POPANC: An analysis-ready database on presence-only and presence-absence data of Neotropical carnivores (Mammalia: Carnivora) from 2000 to 2021; Zenodo; [DOI from Zenodo provided once the GitHub repository is archived]. [Dataset] / [Code]

If you use our underlying data, please also cite the **source** data as well.
