# LCS Data Scraping, Cleaning, Preparation, and Analysis Scripts

**Instructions**

To view the code and read the methodology, click into the relevant folder and click the name of one of the files. The `.ipynb` files will take a moment to load but will render inline. My comments are included therein.

Each directory contains python scripts or Jupyter Notebooks with python code used for the various components of the projects. The Jupyter Notebooks (mostly) contains Markdown blocks that document what I was doing and why I was doing it. This is the log of my methodology.


## vdc

The file `vdc_scraper.py` is the script that I used to pull data off of the VDC portal.

## wikipedia_timeline

The code that I used to extract the Syrian Civil War Timeline from wikipedia during the Summer of 2017.

## syria_portal

The code that I used to extract the articles from the Syria portal, which I subsequently pushed into the RDC Discourse website.

## uossm

Some work that I did (June 2017) to transform data provided by UOSSM into a SQLite database so that it could be more easily analyzed in Tableau.

## sams

This repository contains the series of Jupyter Notebooks (python) containing the code I used to import, clean, and process patient encounter data from the SAMS raw data files. The data itself is not included.

The only changes to the scripts that I made was to redact an API key for Airtable and the hash salts for PII because their inclusion would risk the security of my Airtable account and the PII of the patients that visited the SAMS clinics. 

Each notebook was designed with this process:

- Import the database produced by the final command in the previous notebook.
- Create a clone of it
- Use the clone as a working copy
- Save the clone in the last command as a "template" for use in the following notebook

This was done to make the research methods mostly reproducable. 

There were some sections in the earlier notebooks where direct human intervention in the database saved hours of time and therefore the changes were note recorded in the notebooks. I have the raw database files from each step, however, so if needed, I can identify the changes made by analyzing the differences between the versioned database clones.

I made the conscious decision to repeat code sections from notebook to notebook, in spite of this not being necessarily considered good practice under DRY coding principles. My thinking was that I wanted each notebook to have it's own independent code base and not rely on code shared other notebooks. If I had chosen to share chunks of code between notebook and had later decided to alter a code block, the effect of the change would ripple through all analysis in the event it needed to be repeated and potentially produce a different outcome. Therefore, there are places where I used certain functions in earlier notebooks only to use them again in a slightly modified way in later notebooks. Because each notebook has self-contained code, the earlier notebooks can be re-run using their own original versions of these functions. This is most notable with the methodology for generating the flagged datasets.