# edna2obis workflow

## Introduction
**Rationale:**

DNA derived data are increasingly being used to document taxon 
occurrences. To ensure these data are useful to the broadest possible 
community, [GBIF](https://www.gbif.org/) published a guide entitled "[Publishing DNA-derived 
data through biodiversity data platforms](https://docs.gbif-uat.org/publishing-dna-derived-data/1.0/en/)." 
This guide is supported by the [DNA derived data extension](https://tools.gbif.org/dwca-validator/extension.do?id=http://rs.gbif.org/terms/1.0/DNADerivedData) 
for [Darwin Core](https://dwc.tdwg.org/), which incorporates [MIxS](https://gensc.org/mixs/) 
terms into the Darwin Core standard. 

This use case draws on both the guide and the extension to illustrate 
how to incorporate a DNA derived data extension file into a Darwin Core
archive. 

For further information on this use case and the DNA Derived data extension
in general, see the recording of the [OBIS Webinar on Genetic Data](https://obis.org/2021/10/13/gendatawebinar/).

**Project abstract:**

Seawater was collected on board the NOAA ship Ronald H. Brown as part of the fourth Gulf of Mexico Ecosystems and Carbon Cycle (GOMECC-4) cruise from September 13 to October 21, 2021. Sampling for GOMECC-4 occurred along 16 coastal-offshore transects across the entire Gulf of Mexico and an additional line at 27N latitude in the Atlantic Ocean. We also collected eDNA samples near Padre Island National Seashore (U.S. National Parks Service), a barrier island located off the coast of south Texas. Vertical CTD sampling was employed at each site to measure discrete chemical, physical, and biological properties. Water sampling for DNA filtration was conducted at 54 sites and three depths per site (surface, deep chlorophyll maximum, and near bottom) to capture horizontal and vertical gradients of bacterial, protistan, and metazoan diversity across the Gulf. The resulting ASVs, their assigned taxonomy, and the metadata associated with theircollection are the input data for the OBIS conversion scripts presented here.

## Published data
- [GBIF](https://www.gbif.org/dataset/9012def0-bd87-48a0-ac9e-e0e78dd37689)
- [OBIS](https://obis.org/dataset/210efc7c-4762-47ee-b4b5-22a0f436ef44)

## NOAA Omics MIMARKS-based metadata template
This code was developed to convert a custom Google Sheet metadata template developed by NOAA Omics at AOML. To use the sheet for your own data, copy the Google Sheet to your Google Drive. Note that we have not tested the data validation functionality when downloading the Google Sheet to use as an Excel file.
[AOML_MIMARKS.survey.water.6.0 v1.0.0](https://docs.google.com/spreadsheets/d/1jof9MBEll7Xluu8-_znLRBIP9JpyAd_5YvdioZ-REoY/edit?usp=sharing)

## Repo structure
```
.
+-- README.md                   :Description of this repository
+-- LICENSE                     :Repository license
+-- .gitignore                  :Files and directories to be ignored by git
|
+-- raw
|   +-- gomecc-16S-asv.tsv      :Source data containing 16S ASV sequences, taxon matches, and number of reads
|   +-- gomecc-18S-asv.tsv      :Source data containing 18S ASV sequences, taxon matches, and number of reads
|   +-- gomecc4_AOML_MIMARKS.survey.water.6.0.xlsx     :Source data containing metadata about samples, DNA preparation, and analysis
|   +-- gomecc_AOML2DwC standards.xlsx     :Data dictionary file mapping metadata terms to DarwinCore
|
+-- src
|   +-- edna2obis_conversion_code   :Darwin Core mapping Jupyter Notebook
|   +-- WoRMS_matching.py           :Functions for querying the World Register of Marine Species
|
+-- processed
|   +-- occurrence.csv          :Occurrence file, generated by conversion_code
|   +-- dna_extension.csv       :DNA Derived Data Extension file, generated by conversion_code

```

