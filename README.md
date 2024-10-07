# FAIR Data Point Populator
## Introduction
The FAIR Data Point Populator was created to help people not very familiar with FAIR, to create metadata in Excel sheets, and have these published in a FAIR Data Point (https://www.fairdatapoint.org/). The FAIR Data Point Populator is a GitHub workflow, that reads the metadata from the repository, transforms this into RDF, and then publishes this on a FAIR Data Point.

## Set up
* If there is no FAIR Data Point yet, set one up locally (https://fairdatapoint.readthedocs.io/en/latest/deployment/local-deployment.html) or online (https://fairdatapoint.readthedocs.io/en/latest/deployment/production-deployment.html).
* Make a metadata repository like https://github.com/LUMC-BioSemantics/ejprd-wp13-metadata, for example, by cloning it. This repository is connected to the FAIR Data Point Populator GitHub repository.
* Connect the metadata repository to a FAIR Data Point by setting the following GitHub secrets in the metadata repository.
	* FDP URL (URL of the FAIR Data Point)
	* FDP Persistant URL (Persistant URL of the FAIR Data Point if available (e.g. w3id), URL of the FAIR Data Point otherwise.)
	* Username (username in the FAIR Data Point)
	* password (password in the FAIR Data Point)

## Set up alternative
Alternatively, [this](https://colab.research.google.com/drive/1YeARH-hBJbg5Nz2MMnCB3RmS0uvXOHyU?usp=sharing) Jupyter notebook can be used. This still requires a FAIR Data Point to be available.

## Use
* The **user** fills in the [FDP](https://github.com/LUMC-BioSemantics/EJP-RD-WP13-FDP-template) or [EJP RD](https://github.com/ejp-rd-vp/resource-metadata-schema/blob/master/template/EJPRD%20Resource%20Metadata%20template.xlsx) template.
* The **user** uploads the template to the metadata repository (or hands it over to the administrator for the administrator to upload).
* The **administrator** checks the metadata, and in the case of the FDP template, extracts a datasets.csv and distributions.csv file.
* The **administrator** sets the target metadata and target catalog in the config.yml file (see [the config file](https://github.com/jdwijnbergen/fdp-populator/blob/main/config.yml) for an example), and starts the workflow using the start workflow button.
* The **FDPP** converts the metadata from the Excel sheet into RDF documents.
* The **FDPP** publishes the RDF into the connected FAIR Data Point.

## EJP RD
The EJP RD version of this tool requires special configuration of the FAIR Data Point, following the [EJP RD metadata schema](https://github.com/ejp-rd-vp/resource-metadata-schema).
