# Bibliographic information integration option for NextStrain

The Zotero branch of ncov-ingest holds the metadata and scripts necessary to generate the paper_url and title annotation information for the SAS-CoV-2 Nextstrain annotations.tsv file.

The intention is for updating of genomic epidemiology bibliographic information to be done through the Zotero Web portal [here](https://www.zotero.org/groups/2512356/covid19_genomic_epidemiology_bibliography/library) 

This portal automatically fetches articles and provides titles, urls, DOIs, etc. and Paul Gordon (nodrogluap) has been manually adding virus names (e.g. Australia/VIC65/2020) to those records where appropriate.

Updated versions of the Zotero-stored information can be exported one hundred papers at a time to RDF files via the portal interface. These are the files epi_genomics_zotero_biblio_part_#.rdf

The can then made ready to import into NextStrain using the following command:

``
shell
../bin/add_zotero_rdf_biblio_annotations.pl annotations.tsv overriding_paper_urls_for_viruses.txt gisaid_hcov-19_2020_06_08.tsv epi_genomics_zotero_biblio_part_1.rdf epi_genomics_zotero_biblio_part_2.rdf
``

Where ```gisaid_hcov-19_2020_06_08.tsv``` is the GISAID patient status metadata TSV file (cannot be committed here due to GISAID license restrictions), and ```overriding_paper_urls_for_viruses.txt```
is a tab-delimited file of virus name -> url mappings that should override anything listed in the Zotero RDF files. 
