# beemfit

Beemfit is a fitting routine for spectra measured with ballistic electron emission microscopy (BEEM), which determines the Schottky barrier height of a metal-semiconductor interface.  It linearizes the data and searches over all possible fits to find the best fit.  It outputs the Schottky barrier height in eV and amplitude of the spectra, as well as the linearization parameters.


## Usage

beemfit is run from the command line.  The file with the data `data.csv` should be in a two column CSV format (tip bias V , BEEM current in pA), where blank lines and lines that begin with '#' are ignored.  For example:

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

To fit this data type:
```
beemfit --input_filename=data.csv
```
The output will appear
```
beemfit v 1.1.0 BEEM Spectroscopy Fitter
Copyright (C) V.P. LaBella 2007-2024 [Nov 4 2024 15:49:43]
Filename             :  FBEEM_spectra.dat
BEEM Type            :  Forward BEEM
Points               :  200
*** Fit Found ***
Schottky             :  0.85 eV
n (power)            :  2
R_squared            :  1
R_squared_full       :  1
amplitude            :  20
b                    :  -3.80132
b_error              :  1.72718e-15
b_fractional_error   :  4.54364e-16
m                    :  -4.47214
m_error              :  1.81951e-15
m_fractional_error   :  4.06855e-16
Fit Start Bias       :  -0.85 V
Window Size          :  0.2 V
Lin Start Bias       :  -0.655 V
Lin Start Current    :  0 pA
Lin Start Sep        :  0.195 V
Schottky Sep         :  0 V
Max Lin Start Sep    :  0.2 V
Max Schottky Sep     :  0.15 V
Fit Filename         :  FBEEM_spectra_fit.dat
Fit Param. Filename  :  FBEEM_spectra_parameters.dat
```

Two additional files will be created, one with the original data and corresponding fit and another with the parameters of the fit, that is displayed on the screen.  Several other options are available and can be seen with the `--help` command.

# Acknowledgment

If you utilize this routine in your presentations or publications I would appreciate a mention of beemfit in the acknowledgements.  This routing was developed over several years and fitting hundreds of thousands of BEEM spectra taken be nuermous hard working graduate students.  The original linearization algorithm was first implemented by Robert Balsano and utilized in the following publication: Schottky barrier height measurements of Cu/Si(001), Ag/Si(001), and Au/Si(001) interfaces utilizing ballistic electron emission microscopy and ballistic hole emission microscopy, Robert Balsano, Akitomo Matsubayashi, Vincent P. LaBella, AIP Advances, 3 112110 (2013). DOI: 10.1063/1.4831756.  The algorithm in its current form has been modified and improved upon since that time and has been used to fit spectra from numerous different M/S interfaces.
