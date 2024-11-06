# beemfit

Beemfit is a fitting routine for spectra measured with ballistic electron emission microscopy (BEEM), which detemines the Schottky Barrier height of a metal-semiconductor interface.  It linearizes the data and searches over all possible fits to find the best fit.  It outputs the Schottky barrier heigh and amplitude of the spectra, as well as the linearization parameters.


## Usage

beemfit is a CLI application and is run from teh command line.  The file with the data should be in a two column CSV format (tip bias V , BEEM current in pA), where blank lines and lines that being with '#' are ignored.  For example:

```
# my BEEM data
# this is comment and will be ignored
#vtip,ibeem
-0.8,0,0
-0.805,0,0
-0.81,0,0
-0.815,0,0
-0.82,0,0
-0.825,0,0
-0.83,0,0
-0.835,0,0
-0.84,0,0
-0.845,0,0
-0.85,0,0
-0.855,0.0005,0
-0.86,0.002,0
-0.865,0.0045,0
-0.87,0.008,0


```

