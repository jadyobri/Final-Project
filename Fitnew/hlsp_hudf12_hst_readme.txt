The Hubble Ultra Deep Field 2012 (HUDF12) Treasury Program Data Release V1.0
============================================================================
Anton M. Koekemoer, STScI, 15 Nov 2012


Observational Summary
---------------------

The Hubble Ultra Deep Field 2012 Treasury program (HUDF12: Ellis
et al. 2012; Koekemoer et al. 2012) is a large HST program awarded
128 orbits (HST Program ID 12498; PI: R. Ellis), designed to probe
the contribution of early galaxies to cosmic reionization. The main
project website is accessible at    http://udf12.arizona.edu
This program significantly extends previous data on the main Ultra Deep
Field (UDF) with new deep observations using the HST WFC3/IR camera in
a range of filters that are crucial to addressing these questions.

Specifically, our new observations quadruple the exposure time of F105W
on the UDF main field by adding 72 new orbits to data obtained previously
in program ID 11563 (PI: G. Illingworth; see Bouwens et al. 2011), as well
as providing 30 orbits in the completely new F140W filter, and providing an
additional 26 orbits of depth in the F160W filter. The new observations are
obtained with observing strategies as consistent as possible with previous
observations, and are combined with these data along with all other existing
data on this field, as was committed to in the proposal, to deliver a
single, unified set of mosaics of the UDF providing a legacy dataset on
this field, of lasting scientific value.

    UDF12 Observing Summary (HST Program ID 12498)

    Field     Camera / Filter    Orbits    Exposures   Exposure time (s)
    --------  ---------------    ------    ---------   -----------------
    UDF-main:  WFC3/IR F105W        72        144            198423
               WFC3/IR F140W        30         60             82676
               WFC3/IR F160W        26         52             71652

    UDF-par2:  ACS/WFC F814W       128        256            322944


The WFC3/IR observations for the HUDF12 program 12498 were all obtained
during the period 4 August 2012 to 16 September 2012, at a spacecraft orient
of 264 degrees for all observations. This enabled all the parallel ACS
exposures to be placed on the UDF-par2 field, exactly overlapping the
previous ACS parallels on this field from program 11563. The full 128 orbits
of ACS observations on the UDF-par2 field were obtained in the F814W filter,
complementing the existing ACS coverage of this field to offer the most
efficient, deepest possible dropout selection of galaxies at z>6.5
(justified further in McLure et al. 2011). Each orbit was divided into two
WFC3/IR prime exposures, together with two corresponding ACS parallel
exposures. The WFC3/IR exposures were all obtained using the SPARS100
readout pattern with either 15 or 16 samples per exposure, depending on the
orbital visibility (thus yielding exposure times of either 1300s or 1400s,
after accounting for the additional two samples at the start of each
exposure).


The dither patterns followed a strategy that was matched to the previous
observations of the UDF, in particular including small sub-pixel dithers to
provide good sampling of the sub-pixel phase space, along with larger
dithers on scales of ~1-3 arcseconds to move sources around the detectors,
mitigating the impact of the ACS chip gap in the parallel observations as
well as moving around detector artifacts and areas of persistence in the
WFC3/IR observations.


Data Processing and Products

All the WFC3 and ACS data have been processed using the Mosaicdrizzle
pipeline (see Koekemoer et al. 2002, 2011 for further details about this
pipeline in general, and Koekemoer et al. 2012 in preparation, for details
about the HUDF12 processing in particular), which includes calibration,
astrometric alignment, bad pixel rejection, and final drizzle combination.
Initial calibrated versions of all the WFC3 and ACS exposures were produced
as a first-pass calibration, using the standard Pyraf/STSDAS calacs and
calwf3 routines. These enabled initial quality inspection of the data, prior
to subsequent refinemment. The WFC3/IR data were then recalibrated using
superdarks that we constructed from all the on-orbit darks observed in this
readout mode (providing a higher signal-to-noise dark file than the standard
reference files), and all pixels affected by persistence were masked out. In
addition, a fraction of the WFC3/IR exposures were affected by changing sky
backgrounds, for which further processing was necessary in addition to the
standard calwf3 up-the-ramp sampling, in order to ensure that the pixel
statistics in the final images were correct. The ACS images underwent
additional processing for correcting CTE losses and bias destriping, all of
which are incorporated into the calacs code distributed under Pyraf/STSDAS.
Further details of the processing are provided in Koekemoer et al. (2012).

Astrometric alignment of the all exposures was carried out within
Mosaicdrizzle using the published catalogs for the UDF main field (Beckwith
et al. 2006) as well as catalogs generated from the UDF-par2 data (Bouwens
et al. 2011), using in an iterative process that involves solving for shifts
and rotations using a combination of catalog-matching and cross-correlation.
Once the images were aligned, bad pixels and residual cosmic rays could be
rejected by comparing each image to a deep stack of the full set of images.
Satellite trails were also identified and masked. In addition, low-level
residual background structure in the WFC3/IR images was removed using median
filtering of the empty regions of all the images, restricting the spatial
scale of any subtracted structure to 5" or larger to ensure that small-scale
features were retained in the images. The final combination using drizzle
(Fruchter & Hook 2002) produces distortion-corrected mosaics consisting of
the weighted sum of all the input exposures (*_drz.fits), in units of
electrons/second, along with the correponding inverse variance weight files
(*_wht.fits). Correlated noise can be accounted for using the prescriptions
provided in Casertano et al. (2000). In addition, these mosaics combine the
new observations from the HUDF12 program (HST program ID 12498, PI: R.
Ellis) as well as the previous data from the HUDF09 program (HST program ID
11563, PI: G. Illingworth), together with exposures from other programs (in
particular CANDELS: HST program IDs 12060, 12061, 12062, PI. S. Faber and H.
Ferguson) although the latter only add a relatively small number of
additional orbits. This full-depth combination was committed to in the
original HUDF12 proposal, and provides a single, unified set of mosaics of
the UDF, constituting a lasting legacy dataset on this field.


    Final Combined Full-Depth UDF-main WFC3/IR mosaics (orbits)

    Camera / Filter     HUDF09     HUDF12     Other     Final*
    ---------------     ------     ------     -----     -----
    WFC3/IR F105W         24         72         4        100
    WFC3/IR F125W         34          -         5         39
    WFC3/IR F140W          -         30         -         30
    WFC3/IR F160W         53         26         5         84

    * Final combined WFC3/IR depth from all the following programs on the
      UDF-main field: HUDF09: HST Program ID 11563 (PI: G. Illingworth);
      HUDF12: HST Prorgram ID 12498 (PI: R. Ellis);
      Other: HST Program ID 12099 (PI: A. Riess) and CANDELS, HST Program
      ID 12060,12061,12062 (PI: S. Faber, H. Ferguson)


Data Download Options

The combined mosaics are being made available as part of the the STScI High-Level Science Products, via web browser and ftp.

Via web browser
        http://archive.stsci.edu/pub/hlsp/hudf12/
        is the starting navigation point to all the HUDF12 data.
FTP:
        ftp archive.stsci.edu and login as anonymous:
        cd /pub/hlsp/hudf12
        From there the data of interest can be directly downloaded.
WGET:
        The entire directory can be downloaded using wget commands such as:
        wget -q -nH --cut-dirs=3 -r -l0 -c -N -np -R 'index*' -erobots=off             http://archive.stsci.edu/pub/hlsp/hudf12/

References

Beckwith, S. V. W. 2006, AJ, 132,1729
Bouwens, R.  et al. 2011, ApJ, 737, 90
Casertano, S. et al. 2000, AJ, 120, 2747
Ellis, R. S. et al. 2012, ApJL, submitted
Fruchter, A. S and Hook, R. N. 2002, PASP, 114, 144
Grogin, N. A. et al. 2011, ApJS. 197, 35
Koekemoer, A. M. et al. 2002, HST Calibration Workshop, 337
Koekemoer, A. M. et al. 2011, ApJS, 197, 36
Koekemoer, A. M. et al. 2012, ApJS, in preparation
McLure, R. J. et al. 2011, MNRAS 218, 2074


