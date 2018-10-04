# A drat system for the hyena project

We are using this repository for users to be able to install our R package using ```drat``` http://eddelbuettel.github.io/drat/.

The ```drat``` system allows for an easy installation of our packages.


## For users: how to install our R packages?

First make sure that the R package ```drat``` is installed on your system.
If that is not the case, install the R package by simply typing inside your R Console:

```{r}
install.packages("drat")
```

Once the R package ```drat``` is installed, you can simply install our packages by typing:

```{r}
drat::addRepo("hyenaproject")
install.packages("XXX") ## replace XXX by the name of the package!
```


## For the hyena project developers: how to add your own R package here?

To add a new package or a new version of a package on this ```drat``` folder, you first need to make sure that you have a local clone of this folder on your computer.

To clone the folder on your computer, simply type in your terminal (at the target location):

```
git clone https://github.com/hyenaproject/drat.git
```

Then, to add your package, create a build version of the package (i.e. ```*.tar.gz```) as usual, make sure the R package ```drat``` is installed on your system (see above), and type in your R console:

```
drat::insertPackage("the_path_of_your_tar.gz", repodir = "the_path_of_your_local_drat_folder")
```

Make sure to replace the placeholders by the correct text. 

Finally, commit and push using ```git``` from within your local drat folder.

Note: if you want to get rid of old package versions, check ```?drat::pruneRepo```.