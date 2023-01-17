## LaQuiniela of LaLiga

Team members: Ferran Iglesias Cels - Pau Rodrigo Parés - Jaume Reixach Pérez

This repo contains a Random Forest based model in order to predict the results of LaLiga matches. This model uses 100 trees and 4 predictors: the name of the teams, and their current ranks. Training it with data from 1928 - 2018 and testing it with season 2019-2020 we have obtained an approximate 48% accuracy.

### Repository structure

```
quiniela/
  ├─── analysis/				# Jupyter Notebooks used to explore the data
  │          ...
  ├─── logs/					# Logs of the program are written
  │          ...
  ├─── models/					# The place were trained models are stored
  │          ...
  ├─── quiniela/				# Main Python package
  │          ...
  ├─── reports/					# The place to save HTML / CSV / Excel reports
  │          ...
  ├─── .gitignore
  ├─── cli.py					# Main executable. Entrypoint for CLI
  ├─── laliga.sqlite			# The database
  ├─── README.md
  ├─── requirements.txt			# List of libraries needed to run the project
  └─── settings.py				# General parameters of the program
```

### How to run it

You are provided with a fully-functional dummy model. Once you've installed dependences (```pip install -r requirements.txt```), which is only Pandas in this dummy case, you can try it yourself:

```console
foo@bar:~$ python cli.py train --training_seasons 2010:2020
Model succesfully trained and saved in ./models/my_quiniela.model
foo@bar:~$ python cli.py predict 2021-2022 1 3
Matchday 3 - LaLiga - Division 1 - Season 2021-2022
======================================================================
         RCD Mallorca          vs            Espanyol            --> X
           Valencia            vs             Alavés             --> X
        Celta de Vigo          vs            Athletic            --> X
        Real Sociedad          vs            Levante             --> X
           Elche CF            vs           Sevilla FC           --> X
          Real Betis           vs          Real Madrid           --> X
          Barcelona            vs             Getafe             --> X
           Cádiz CF            vs           CA Osasuna           --> X
        Rayo Vallecano         vs           Granada CF           --> X
       Atlético Madrid         vs           Villarreal           --> X
```

Here, we call ```train``` to train the model using seasons from 2010 to 2020, and then we perfom a prediction of 3rd matchday of 2021-2022 season at 1st Division using ```predict```. Of course, that's a terrible prediction: that's why it's a dummy model!! Call to ```train``` did literally nothing, and ```predict``` always return ```X ```. It is your job to make something interesting.

Check out options on ```train``` and ```predict``` using ```-h``` option. You are free to add any other argument that you find necessary.


The data source is [Transfermarkt](https://www.transfermarkt.com/), and it was scraped using Python's library BeautifulSoup4.

