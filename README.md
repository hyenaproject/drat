# drat
This drat folder is where you need to go to install our R packages

# Install our R packages using drat

We are using this repository for users to be able to install our R package using ```drat``` http://eddelbuettel.github.io/drat/.

The ```drat``` system allows for an easy installation of our packages.

After installing the R package ```drat``` on their system, you can simply install one of our packages by typing:

```{r}
drat::addRepo("hyenaproject")
install.packages("XXX") ## replace XXX by the name of the package!
```

This is work in progress but our packages will be added there progressively.
