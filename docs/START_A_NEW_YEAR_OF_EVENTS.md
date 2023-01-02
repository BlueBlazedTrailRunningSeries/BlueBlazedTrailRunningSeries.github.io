# Setting up a new year

These are the steps required to set up a new year for races. This only has to be done once, at the beginning of the season.

To summarize, the following files need to be added:

- race list CSV file
- race list template 
- race JSON template 
- results CSV files 
- results list template
- update site config for the new year


## Add the races list CSV file

All event information on the webpage, including the 'Upcoming' list on the home page and the full list in the Races page, is ultimately generated from the races CSV file.

### CSV file location

The races list CSV file is placed in the _data/races directory

### File name

The CSV file should be named using the year: YYYY.csv

For example: 2023.csv

### File details

The races list CSV file expects the following format:

`date,race,distance,website`

The date is expected to be in ISO-8601 format (YYYY-MM-DD, with optional time)

An example of a complete CSV file is:

`date,race,distance,website
2023-04-15,Traprock Trail Races,17k,https://www.cttrailmixers.com/traprock-17-50k
2023-05-21T09:00,Soapstone Mountain Trail Races,24k,http://shenipsitstriders.org/club-races/soapstone-mountain-trail-races.html
2023-06-04,Goodwin Forest Trail Runs,10k,https://www.friendsofgoodwinforest.org/goodwin-forest-trail-run.html
2023-06-11T09:00,Nipmuck South Trail Race,14.5mi,http://shenipsitstriders.org/club-races/nipmuck-south-trail-race.html
2023-06-17,HMF Summer Solstice Trail Run,8mi,http://www.hartfordmarathon.com/summer-solstice-trail-run
2023-09-23,Tunxis Trail Race,30k,https://tunxisultra.wordpress.com
2023-10-01T08:00:00-04,NipMuck Trail Marathon,26.4mi,http://shenipsitstriders.org/club-races/nipmuck-trail-marathon.html
2023-10-22,Bimbler's Bluff,50k,https://bimblersound.com/WordPress/bluff/`


## Race list template

The race list template needs to be created for each new year. Without the template, the web page's race list HTML won't generate.

The easiest way to create the template is as follows:

In the _races directory, create a new directory for the current year.

Example directory path:

_races/2023

Then, copy one of the prior templates from a prior year into the current year's directory.

For example, *copy* _races/2022/index.html into the new _races/2023 directory, so you now have _races/2023/index.html

Edit the newly copied index.html file (example _races/2023/index.html) for the current year. Make sure that the 'year' and 'title' values are updated to reflect the new year.


## JSON file template

The 'Upcoming Races' list on the home page is updated from a JSON file, and a template for that JSON file needs to be created for the new year. Without the template, the JSON file won't generate.

The easiest way to create the template is as follows:

In the _api directory, create a new directory for the current year.

Example directory path:

_api/2023

Then, copy one of the prior templates from a prior year into the current year's directory.

For example, *copy* _api/2022/races.json into the new _api/2023 directory, so you now have _api/2023/races.json

Edit the newly copied races.json file (example _api/2023/races.json) for the current year. Make sure that the 'year' value is updated to reflect the new year.


## Add the results list CSV files

The results page is generated from the results CSV file.

### CSV file location

The races list CSV file is placed in the _data/results/YYYY for year directory. For example, _data/results/2023

### File name

There are two CSV files, one for the women's results and one for the men's. The file names are women.csv and men.csv.

An example of the full file path for the two files is:

- _data/results/2023/men.csv
- _data/results/2023/women.csv

### File details

There is no formatting requirement for the results csv files; any proper CSV file is accepted. One thing to note is that the list is automatically numbered when it is generated, so there is no requirement for numbering the rows (ie, place, 1, 2, 3, etc).

### Creating the files 

Having covered all of that info: make sure to create two empty csv files for the new year to avoid compile errors.

Example format:

_data/results/2022/men.csv

`FIRST,LAST,Traprock17,Soap24,Goodwin10,NipmuckSouth,Solstice8m,Peoples7m,Tunxis30,T2ACure8,Maced25,Nipmuck,Bimblers,Total`


_data/results/2022/women.csv

`FIRST,LAST,Traprock17,Soap24,Goodwin10,NipmuckSouth,Solstice8m,Peoples7m,Tunxis30,T2ACure8,Maced25,Nipmuck,Bimblers,Total`


## Result list template

The result list template needs to be created for each new year. Without the template, the web page's result list HTML won't generate. Note: if you're setting up the page prior to the season's start, and you want the prior year's results to remain the default displayed, then simply don't create the result template file until you have the results from the first race of the season. Until you create the 2023 results template, the 2022 results will be displayed.

The easiest way to create the template is as follows:

Copy one of the prior templates from a prior year.

For example, *make a copy of* _results/2022.html and rename the *copy* to _results/2023.html

Edit the newly copied results template file (example _results/2023.html) for the current year. Make sure that the 'year' and 'title' values are updated to reflect the new year.


## Update site config

In order for the year changes to take effect, the site config needs the year to be updated.

Edit the _config.yml file, updating the 'year' value to the new year.

