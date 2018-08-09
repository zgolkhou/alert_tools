```
source: The ZTF Science Data System (ZSDS)
        Pipelines, Definitions, Data Products & Access (Version 3.2, July 3, 2018)
        Frank J. Masci, et al.
```

### FILE FORMAT
```
The ZTF matchfiles are stored in HDF5 format, and are readable and 
writable by the pytables Python package.
```

### GROUPS WITHIN THE FILE
```
The HDF5 groups within each file is named “matches”. For example, the hierarchy 
in a file is store.root.matches where store is the pytables file handle.
```

### FILE LOCATIONS
```
The matchfiles are stored on the ZTF systems in subdirectories of /ztf/ops/srcmatch, 
where the subdirectories take the form rcNN/frNNNNNN-NNNNNN similar to the reference images.
```

### FILE NAMING CONVENTION
```
The matchfiles follow the naming convention of reference images, 
ztf_NNNNNN_zC_cNN_qN_match.pytable where the capital items are field number, 
filter letter, chip number and quadrant number.
```
---

# TABLES ACCESSIBLE AT THE MATCH GROUP LEVEL
Five tables are attached to the match group:
- ### Exposures
- ### Sources
- ### Sourcedata
- ### Transients
- ### Transientdata

---

### EXPOSURES TABLE

- The exposures table contains one row per exposure.
- The expid column is indexed with default pytables values.

Column Name | Data Type | Description |
|:--------|:-------|:--------|
| diq | Float32 | Derived image quality (fwhm) in arcseconds. Values of 0.0 indicate the PSF file could not be read.
| expid | Int32 | Exposure ID |
| fieldid | UInt32 | Field ID |
| filterid | UInt16 | Filter ID |
| fracday | Uint64 | YYYYMMDDdddddd Year, month, fractional day |
| infobits | Int32 | Quality indicators |
| ipac_pub_date | Float32 | IPAC publication date for this exposure, in modified Julian Date format |
| limitmag | Float32 | Limiting magnitude (faintest detectable) |
| magzp | Float32 | Magnitude zeropoint from photometric cal |
| magzprms | Float32 | Rms of magnitude zeropoint |
| magzpunc | Float32 | Uncertainty in magnitude zeropoint |
| nsources | Int32 | Number of sourcedata entries for this expid |
| nstars | Int32 | nsources + ntransients |
| ntransients | Int32 | Number of transientdata entries for this expid |
| obsmjd | Float64 | Modified Julian date of observation | 
| obshjd | Float64 | Heliocentric Julian date at mean coordinates |
| programid | UInt16 | Program ID |
| rcid | UInt8 | Readout-channel ID (0-63) |
| relphotsatmag | Float32 | Saturation magnitude from relative photometry |
| relphotsyserr | Float32 | Systematic uncertainty in relphot zero-point |
| relphotzp | Float32 | Relative photometry zero-point (delta-mag) |
| relphotzperr | Float32 | Uncertainty in relative photometry zero-point. If NaN, the relphotzp value is set to 0.0. |

---

### SOURCES TABLE
Each row in the sources table corresponds to an Object that appeared in the reference catalog that seeded the matchfile. Most of the columns are light curve statistics computed on the time series data in the sourcedata table. Note that several columns contain multidimensional arrays.
The x, y, z, and matched columns are indexed with pytables defaults (medium index).

Column Name | Data Type | Description |
|:--------|:-------|:--------|
| astrometricrms | Float64Col | [degrees] Root Mean Squared deviation in epochal positions relative to the object's ra,dec; effectively theroot-summed mean squared deviations along the ra and dec axes |
| bestastrometricrms | Float64Col | Same as astrometricrms, but usingonly nbestobs epochal detections usedto compute relative photometry|
| bestchisq | Float32Col | Same as chisq, but using only nbestobs epochal detections used to compute relative photometry |
| bestcon | Float32Col | Same as con, but using only nbestobs epochal detections used to compute relative photometry |
| bestlineartrend | Float32Col | Same as lineartrend, but using only nbestobs epochal detections used tocompute relative photometry |
| bestmagrms | Float32Col | Same as lineartrend, but using only nbestobs epochal detections used to compute relative photometry |
| bestmaxmag | Float32Col | Same as maxmag, but using only nbestobs epochal detections used to compute relative photometry | 
| bestmaxslope | Float32Col | Same as maxslope, but using only nbestobs epochal detections used to compute relative photometry |
| bestmeanmag | Float32Col | Same as meanmag, but using only nbestobs epochal detections used tocompute relative photometry| 
| bestmedianabsdev | Float32Col | Same as medianabsdev, but using only nbestobs epochal detections used tocompute relative photometry |
| bestmedianmag | Float32Col | Same as medianmag, but using only nbestobs epochal detections used tocompute relative photometry |
| bestminmag | Float32Col | Same as minmag, but using only nbestobs epochal detections used to compute relative photometry |
| bestnabovemeanbystd| UInt16Col, shape=(3,)| Same as nabovemeanbystd, but usingshape=(3,) only nbestobs epochal detections usedto compute relative photometry | 
| bestnbelowmeanbystd | UInt16Col, shape=(3,) | Same as nbelowmeanbystd, but usingshape=(3,) only nbestobs epochal detections usedto compute relative photometry | 
| bestnconsecabovemeanbystd | UInt16Col, shape=(3,) | Same as nconsecabovemeanbystd, butshape=(3,) using only nbestobs epochal detectionsused to compute relative photometry. |
| bestnconsecbelowmeanbystd | UInt16Col, shape=(3,) | Same as nconsecbelowmeanbystd, butshape=(3,) using only nbestobs epochal detectionsused to compute relative photometry |
| bestnconsecfrommeanbystd | UInt16Col, shape=(3,) | Same as nconsecfrommeanbystd, butshape=(3,) using only nbestobs epochal detectionsused to compute relative photometry |
| bestnmedianbufferrange | UInt16Col | Same as nmedianbufferrange, but using only nbestobs epochal detections used to compute relative photometry | 
| bestnpairposslope | UInt16Col | Same as npairposslope, but using only nbestobs epochal detections used tocompute relative photometry | 
| bestpercentiles | Float32Col, shape=(12,) | Same as percentiles, but using onlyshape=(12,) nbestobs epochal detections used tocompute relative photometry | 
| bestperiodsearch | Float32Col, shape=(5,2) | Same as period search but using onlyshape=(5,2) nbestobs epochal detections used tocompute relative photometry | 
| bestprobnonqso | Float32Col | Same as probnonqso, but using only nbestobs epochal detections used tocompute relative photometry | 
| bestprobqso | Float32Col | Same as probqso, but using only nbestobs epochal detections used tocompute relative photometry | 
| bestskewness | Float32Col | Same as skewness, but using only nbestobs epochal detections used tocompute relative photometry |
| bestsmallkurtosis | Float32Col | Same as smallkurtosis, but using onlynbestobs epochal detections used to |
| beststetsonj | Float32Col | Same as stetsonj, but using only nbestobs epochal detections used tocompute relative photometry | | beststetsonk | Float32Col | Same as stetsonk, but using only nbestobs epochal detections used tocompute relative photometry | 
| bestvonneumannratio | Float32Col | Same as vonneumannratio, but usingonly nbestobs epochal detections usedto compute relative photometry | 
| bestweightedmagrms | Float32Col | Same as weightedmagrms, but using only nbestobs epochal detections usedto compute relative photometry | 
| bestweightedmeanmag | Float32Col | Same as weighted meanmag, but using only nbestobs epochal detections usedto compute relative photometry | 
| chisq | Float32Col | Chi-square metric using nobs detections |
| con | Float32Col | fraction of nobs where three consecutive observations are morethan 2x RMS from the median magnitude, plus 1 | 
| dec | Float64Col | Declination (deg) |
| lineartrend | Float32Col | [mag/day] Slope from linear fit to nobs detections |
| magrms | Float32Col | [mag] Root Mean Squared deviation innobs magnitudes |
| matchid | Int32Col | Index into the source data table (forpulling out light curves) |
| maxmag | Float32Col | [mag] Maximum magnitude over nobs detections | 
| maxslope | Float32Col | [mag/day] Maximum pairwise slope over all consecutive nobs detections |
| meanmag | Float32Col | [mag] Mean magnitude over nobs detections |
| medianabsdev | Float32Col | [mag] Median absolute deviation inmagnitudes over nobs detections | 
| medianmag | Float32Col | [mag] Median magnitude over nobs detections |
| minmag | Float32Col | [mag] Minimum magnitude over nobs detections |
| nabovemeanbystd | UInt16Col, shape=(3,) | Number of lightcurve points that areshape=(3,) [1, 3, 5] standard deviations above themean magnitude over nobs |
| nbelowmeanbystd | UInt16Col, shape=(3,) | Number of lightcurve points that areshape=(3,) [1, 3, 5] standard deviations below themean magnitude over |
| nobsnbestobs | UInt16Col | Number of "clean" epochal detections used to compute relative photometric corrections across all observationepochs (= a subset of ngoodobs) |
| nconsecabovemeanbystd | UInt16Col, shape=(3,) | Number of consecutive lightcurveshape=(3,) points that are [1, 3, 5] standarddeviations above the mean magnitude |
| nconsecbelowmeanbystd | UInt16Col, shape=(3,) | Number of consecutive lightcurve shape=(3,) points that are [1, 3, 5] standarddeviations below the mean magnitude | 
| nconsecfrommeanbystd | UInt16Col, shape=(3,) | Total number of consecutiveshape=(3,) lightcurve points that are [1, 3, 5]standard deviations either above orbelow the mean magnitude |
| ngoodobs | UInt16Col | The number of epochal detections thatwere not flagged, masked, norassociated with bad pixels during thesource extraction process |
| nmedianbufferrange | UInt16Col | Number of points more than 20% ofthe lightcurve amplitude from the weighted mean 0 magnitude |
| nobs | UInt16Col | Total number of epochal detections(observation epochs) in the lightcurve for this object |
| npairposslope | UInt16Col | Number of positive slopes between all consecutive pairwise lightcurve points(mag[i+1] brighter than mag[i]) |
| percentiles | Float32Col, shape=(12,) | [mag] [5th, 10th, 17.5th, 25th, 32.5th, shape=(12,) 40th, 60th, 67.5th, 75th, 82.5th, 90th, 95th]percentiles in magnitude over nobs |
| periodsearch | Float32Col, shape=(5,2) | Periodogram peaks in [day], shape=(5,2) periodogram value |
| probnonqso | Float32Col | Probability of variability fit to non-quasar-like source |
| probqso | Float32Col | Probability of variability fit to quasar-like source |
| ra | Float64Col | Right Ascension (deg) | 
| refchi | Float32Col | Chi-sq from reference catalog |
| refmag | Float32Col | Magnitude from ref. catalog |
| refmagerr | Float32Col | Uncertainty in refmag |
| refsharp | Float32Col | Sharpness from ref. catalog |
| refsnr | Float32Col | SNR from reference catalog |
| skewness | Float32Col | Skew (third moment) in lightcurve magnitudes over nobs | 
| smallkurtosis | Float32Col | Kurtosis (fourth moment) in lightcurve magnitudes over nobs for smallsamples (http://www.xycoon.com/peakedness_small_sample_test_1.htm) |
| stetsonj | Float32Col | Stetson-J statistic for this filter only; measures degree of autocorrelation in magnitudes over nobs|
| stetsonk | Float32Col | Stetson-K statistic; proportional to the kurtosis of the magnitude distribution over nobs | 
| uncalibmeanmag | Float32Col | Mean of uncalibrated mags | 
| vonneumannratio | Float32Col | The von Neumann Ratio statistic overnobs; measure of epoch-to-epoch variability |
| weightedmagrms | Float32Col | [mag] Root Mean Square magnitudeover nobs using inverse-variance weighting. |
| weightedmeanmag | Float32Col | [mag] Inverse-variance weighted meanmagnitude over nobs | 
| x | Float64Col | cos(RA)*cos(Dec) | 
| y | Float64Col | sin(RA)*cos(Dec) | 
| z | Float64Col | cos(RA) |

---

### SOURCEDATA TABLE

The sourcedata table contains one row for each observation of an Object in the sources table. Thetime series photometry is stored here.The matchid column is indexed fully so that the table may be sorted by this column. The programidcolumn is indexed with default values.

Column Name | Data Type | Description |
|:--------|:-------|:--------|
| catflags | Int16Col | Catalog flags from PSF-fitting catalog |
| chi | Float32Col | Chi-squared |
| dec | Float64Col, | Declination (deg) |
| expid | Int32Col | Exposure ID (corresponds to exposures table) | 
| hjd | Float64Col| Heliocentric Julian Date (computed from mjd andthe mean ra and dec of the input catalog) |
| mag | Float32Col | Magnitude calibrated with relative photometry |
| magerr | Float32Col | Uncertainty in calibrated magnitude |
| matchid | Int32Col | Match ID corresponding to entries in sources |
| tablemjd | Float64Col | Modified Julian date |
|programid | UInt16Col | Program ID |
| psfflux | Float32Col | Flux from PSF-fitting  |
|psffluxerr | Float32Col | Uncertainty in flux | 
| psfmag | Float32Col | Magnitude from PSF-fitting (“uncalibrated”) | 
| psfmagerr | Float32Col | Uncertainty in PSF-fit magnitude |
|ra | Float64Col | Right Ascension (deg) | 
| relphotflags | Int16Col | Relative photometry flags | 
| sharp | Float32Col | Sharpness of source |
| sid | Int64Col | Source ID (sequential) | 
| snr | Float32Col | Signal-to-noise ratio |
| x| Float64Col | cos(RA)*cos(Dec) |
| xpos | Float32Col | x-center in pixels | 
| y | Float64Col | sin(RA)*cos(Dec) | 
| ypos | Float32Col | y-center in pixels | 
| z | Float64Col | cos(RA) |

---

### TRANSIENTS TABLE

Each row in the transients table corresponds to an Object that did not appear in the reference catalogthat seeded the matchfile. The columns are the same as for the sources table.

---

### TRANSIENTDATA TABLE

The sourcedata table contains one row for each observation of an Object in the transients table. Thetime series photometry is stored here. The columns are the same as for the sourcedata table.
