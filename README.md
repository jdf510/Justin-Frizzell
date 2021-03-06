Justin Frizzell's Final Year Maths Project
===============
This is the program I used to carry out my analyses. It contains functions to carry out the Elo and Glicko updates and parameter optimisation. There are three data files. training.txt contains all the games to be analysed (from month 1 to 95) and some extra games, the results of which are ignored (they are only used to generate a vector containing every player to be considered). test1.txt and test2.txt contain the games to be tested from months 96 to 100. The program that splits all the test games from month 96 to 100 into two separate files can be found in the repository: https://github.com/jdf510/Split

In order to speed up the runtime of the program I created a “converter” application which takes the raw data files as they appear on Kaggle (rows of data entries separated by commas) and generates a text file with each data entry on a separate row. This is only done once and the data files that appear in this directory are in that format. This process does not affect the data itself, just the format. The program which does this can be found in the repository: https://github.com/jdf510/Converter

Once the program is compiled and executed, with the data sets in the same directory , the program will begin to update all the players' Elo and Glicko ratings with optimised parameters. The players are then put into rank order according to Glicko rating (so the order will appear different to Table 3). The program then finds the RMSE and Binomial Deviance (BD) of each optimised system and the results should be the same as those in table 5. 

c can be changed by altering the value of the third argument in the GlickoUpdate() function. The k-factor can be changed by altering the value of k in the Player object constructors in proj.cpp

The kfactortest(players,training,test1) function can be used to optimise the k-factor, this may take ~30mins to run and will generate the csv files used to make the plots in the report. 

The ctest(players,training,test1) function can be used to optimise c, which may also take ~30mins and will produce a csv file which was used to create the c plots in the report. 

The play() function in proj.cpp contains commented out code which was used to generate the convergence plot for Elo and the GlicoUpdate() function contains commented out code which generates the convergence plot for Glicko. 
