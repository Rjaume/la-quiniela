## LaQuiniela of LaLiga

Team members: Ferran Iglesias Cels - Pau Rodrigo Parés - Jaume Reixach Pérez

This repo contains a Random Forest based model in order to predict the results of LaLiga matches. This model uses 100 trees and 4 predictors: the name of the teams, and their current ranks. Training it with data from 1928 - 2018 and testing it with season 2019-2020 we have obtained an approximate 48% accuracy.

### Requirements

In order to run the model you will need to install the following  packages on the python environment you are using:

```
foo@bar:~$ pip install -r requirements.txt

```

The following commands can be used in order to train and predict using the model. For example with the following commands we would train using seasons from 2010-2011 to 2020-2021 and predict the results for the first division's third matchday of season 2021-2022:


```
foo@bar:~$ python cli.py train --training_seasons 2010:2020
foo@bar:~$ python cli.py predict 2021-2022 1 3
```


