# A drat system for the hyena project

We are using this repository for users to be able to install our R package using `drat` http://eddelbuettel.github.io/drat/.

The `drat` system allows for an easy installation of our packages.


## For users: how to install our R packages?

First make sure that the R package `drat` is installed on your system.
If that is not the case, install the R package by simply typing inside your R Console:

```r
install.packages("drat")
```

Once the R package `drat` is installed, you can simply install our packages by typing:

```r
drat::addRepo("hyenaproject")
install.packages("XXX") ## replace XXX by the name of the package!
```


## For the hyena project developers: how to add your own R package here?

To add a new package or a new version of a package on this `drat` folder, you first need to make sure that you have a local clone of this folder on your computer.

To clone the folder on your computer, simply type in your terminal (at the target location):

```
git clone https://github.com/hyenaproject/drat.git
```

Then, to add your package, make sure the R package `drat` is installed on your system (see above), and type in your R console:

Either the following (after creating a build version of the package (i.e. `*.tar.gz`) as usual):

```r
drat::insertPackage("the_path_of_your_tar.gz", repodir = "the_path_of_your_local_drat_folder")
```
and if so, make sure to replace the place holders by the correct text. 


Or, for {hyenaR} specifically, the better way is to use the following from within the hyenaR RStudio project:

```r
build_drat_update("/home/courtiol/GitHub_repos/drat/") # or no path on Windows and it will prompt you
```

Finally, commit and push using `git` from within your local drat folder:

```r
gert::git_add(".")
gert::git_commit(message = "Update hyenaR to version X.X.XXXX")
gitcreds::gitcreds_set()
gert::git_push()
```

Note: if you want to get rid of old package versions, within your drat project, use: 

```r
drat::pruneRepo(repopath = ".", remove = TRUE)
```