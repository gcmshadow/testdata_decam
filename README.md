testdata_decam
==============

This package includes data used by some unit tests
in [obs_decam](https://github.com/lsst/obs_decam).
The data files are edited version of publicly available data
from [NOAO Science Archive](http://www.portal-nvo.noao.edu) and
[DECam Community Pipeline Calibration Files](http://www.ctio.noao.edu/noao/content/decam-calibration-files).

The file `rawData/raw/c4d_150227_012718_ori-stripped.fits.fz` is taken from [ap_verify_hits2015](https://github.com/lsst/ap_verify_hits2015), with all of the image data set to 0 to reduce file size.
This file contains all HDUs in the original file, and is useful for testing handling of "normal" multi-HDU DECam data.
The `rawData/raw/c4d_150227_012718_ori-stripped-shuffled.fits.fz` is identical to the above except that the HDU ordering has been randomly shuffled.
This file is useful for testing reading of files that may not have the "typical" HDU ordering.

The file `rawData/raw/raw.fits` contains the imaging data from two detectors (1 and 25).

The `hits2015-zeroed` directory contains files from the `ap_verify_ci_hits2015` dataset that have had their image data set to the HDU number and then Hcompressed with `fpack` to reduce their size.
These files are not useful for testing pipelines, but they can be used to test butlers (ingestion and gen2 to gen3 conversion).
`calibingested/` is a gen2 calib repo linking to the hits2015 calibration files.
`ingested/` is a gen2 butler repo linking to the hits2015 raw files.

Git LFS
-------

To clone and use this repository, you'll need Git Large File Storage (LFS).

Our [Developer Guide](http://developer.lsst.io/en/latest/tools/git_lfs.html) explains how to setup Git LFS for LSST development.
