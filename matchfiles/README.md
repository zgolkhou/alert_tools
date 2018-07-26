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
| | programid | UInt16 | Program ID |
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
| astrometricrms | Float64Col[degrees] | Root Mean Squareddeviation in epochal positions relativeto the object's ra,dec; effectively theroot-summed mean squared deviationsalong the ra and dec axes |
| bestastrometricrms | Float64 | ColSame as astrometricrms, but usingonly nbestobs epochal detections usedto compute relative photometry|
| bestchisq | Float32 | ColSame as chisq, but using only nbestobsepochal detections used to computerelative photometry |
| bestcon | Float32 | ColSame as con, but using only nbestobsepochal detections used to computerelative photometry |
| bestlineartrend | Float32 | ColSame as lineartrend, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestmagrms | Float32 | ColSame as lineartrend, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestmaxmag | Float32 | ColSame as maxmag, but using onlynbestobs epochal detections used tocompute relative photometry | 
| bestmaxslope | Float32 | ColSame as maxslope, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestmeanmag | Float32 | ColSame as meanmag, but using onlynbestobs epochal detections used tocompute relative photometry| 
| bestmedianabsdev | Float32 | ColSame as medianabsdev, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestmedianmag | Float32 | ColSame as medianmag, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestminmag | Float32 | ColSame as minmag, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestnabovemeanbystd| UInt16Col, | Same as nabovemeanbystd, but usingshape=(3,)only nbestobs epochal detections usedto compute relative photometry | 
| bestnbelowmeanbystd | UInt16Col, | Same as nbelowmeanbystd, but usingshape=(3,)only nbestobs epochal detections usedto compute relative photometry | 
| bestnconsecabovemeanbystdU | Int16Col, | Same as nconsecabovemeanbystd, butshape=(3,)using only nbestobs epochal detectionsused to compute relative photometry. |
| bestnconsecbelowmeanbystd | UInt16Col, | Same as nconsecbelowmeanbystd, butshape=(3,)using only nbestobs epochal detectionsused to compute relative photometry |
| bestnconsecfrommeanbystd | UInt16Col, | Same as nconsecfrommeanbystd, butshape=(3,)using only nbestobs epochal detectionsused to compute relative photometry |
| bestnmedianbufferrange | UInt16Col | Same as nmedianbufferrange, butusing only nbestobs epochal detectionsused to compute relative photometry | 
| bestnpairposslope | UInt16Col | Same as npairposslope, but using onlynbestobs epochal detections used tocompute relative photometry | 
| bestpercentiles | Float32Col, | Same as percentiles, but using onlyshape=(12,)nbestobs epochal detections used tocompute relative photometry | 
| bestperiodsearch | Float32Col, | Same as periodsearch but using onlyshape=(5,2)nbestobs epochal detections used tocompute relative photometry | 
| bestprobnonqso | Float32Col | Same as probnonqso, but using onlynbestobs epochal detections used tocompute relative photometry | 
| bestprobqso | Float32Col | Same as probqso, but using onlynbestobs epochal detections used tocompute relative photometry | 
| bestskewness | Float32Col | Same as skewness, but using onlynbestobs epochal detections used tocompute relative photometry |
| bestsmallkurtosis | Float32Col | Same as smallkurtosis, but using onlynbestobs epochal detections used to |
| beststetsonj | Float32Col | Same as stetsonj, but using onlynbestobs epochal detections used tocompute relative photometry | | beststetsonk | Float32Col | Same as stetsonk, but using onlynbestobs epochal detections used tocompute relative photometry | 
| bestvonneumannratio | Float32Col | Same as vonneumannratio, but usingonly nbestobs epochal detections usedto compute relative photometry | 
| bestweightedmagrms | Float32Col | Same as weightedmagrms, but usingonly nbestobs epochal detections usedto compute relative photometry | 
| bestweightedmeanmag | Float32Col | Same as weightedmeanmag, but usingonly nbestobs epochal detections usedto compute relative photometry | 
| chisq | Float32 | ColChi-square metric using nobs detections |
| con | Float32 | Colfraction of nobs where threeconsecutive observations are morethan 2x RMS from the medianmagnitude, plus 1 | 
| dec | Float64 | ColDeclination (deg) |
| lineartrend | Float32Col | [mag/day] Slope from linear fit to nobs detections |
| magrms | Float32Col | [mag] Root Mean Squared deviation innobs magnitudes |
| matchid | Int32Col | Index into the sourcedata table (forpulling out light curves) |
| maxmag | Float32Col | [mag] Maximum magnitude over nobs detections | 
| maxslope | Float32Col | [mag/day] Maximum pairwise slopeover all consecutive nobs detections |
| meanmag | Float32Col | [mag] Mean magnitude over nobs detections |
| medianabsdev | Float32Col | [mag] Median absolute deviation inmagnitudes over nobs detections | 
| medianmag | Float32Col | [mag] Median magnitude over nobs detections |
| minmag | Float32Col | [mag] Minimum magnitude over nobs detections |
| nabovemeanbystd | UInt16Col, | Number of lightcurve points that areshape=(3,)[1, 3, 5] standard deviations above themean magnitude over nobs |
| nbelowmeanbystd | UInt16Col, | Number of lightcurve points that areshape=(3,)[1, 3, 5] standard deviations below themean magnitude over |
| nobsnbestobs | UInt16Col | Number of "clean" epochal detectionsused to compute relative photometriccorrections across all observationepochs (= a subset of ngoodobs) |
| nconsecabovemeanbystd | UInt16Col, | Number of consecutive lightcurveshape=(3,)points that are [1, 3, 5] standarddeviations above the mean | 
| magnitudenconsecbelowmeanbystd | UInt16Col, | Number of consecutive lightcurveshape=(3,)points that are [1, 3, 5] standarddeviations below the mean |
| magnitudenconsecfrommeanbystd | UInt16Col, | Total number of consecutiveshape=(3,)lightcurve points that are [1, 3, 5]standard deviations either above orbelow the mean |
| magnitudengoodobs | UInt16Col | The number of epochal detections thatwere not flagged, masked, norassociated with bad pixels during thesource extraction |
| processnmedianbufferrange | UInt16Col | Number of points more than 20% ofthe lightcurve amplitude from theweighted mean magnitudenobsUInt16ColTotal number of epochal detections(observation epochs) in the lightcurvefor this |
| objectnpairposslope | UInt16Col | Number of positive slopes between allconsecutive pairwise lightcurve points(mag[i+1] brighter than mag[i]) |
| percentiles | Float32Col, | [mag] [5th, 10th, 17.5th, 25th, 32.5th,shape=(12,)40th, 60th, 67.5th, 75th, 82.5th, 90th, 95th]percentiles in magnitude over | 
| nobsperiodsearch | Float32Col, | Periodogram peaks in [day],shape=(5,2)periodogram valueprobnonqsoFloat32ColProbability of variability fit to non-quasar-like |
| sourceprobqso | Float32Col | Probability of variability fit to quasar-like sourceraFloat64ColRight Ascension (deg) | 
| refchi | Float32Col | Chi-sq from reference catalogrefmagFloat32ColMagnitude from ref. |
| catalogrefmagerr | Float32Col | Uncertainty in refmagrefsharpFloat32ColSharpness from ref. catalog |
| nbelowmeanbystd | UInt16Col, | Number of lightcurve points that areshape=(3,)[1, 3, 5] standard deviations below themean magnitude over |
| nobsnbestobs | UInt16Col | Number of "clean" epochal detectionsused to compute relative photometriccorrections across all observationepochs (= a subset of ngoodobs) | 
| nconsecabovemeanbystd | UInt16Col, | Number of consecutive lightcurveshape=(3,)points that are [1, 3, 5] standarddeviations above the mean magnitude |
| nconsecbelowmeanbystd | UInt16Col, | Number of consecutive lightcurveshape=(3,)points that are [1, 3, 5] standarddeviations below the mean magnitude |
| nconsecfrommeanbystd | UInt16Col, |Total number of consecutiveshape=(3,)lightcurve points that are [1, 3, 5]standard deviations either above orbelow the mean magnitude | 
| ngoodobs | UInt16Col | The number of epochal detections thatwere not flagged, masked, norassociated with bad pixels during thesource extraction process |
| nmedianbufferrange | UInt16Col | Number of points more than 20% ofthe lightcurve amplitude from theweighted mean magnitude | |nobs | UInt16Col | Total number of epochal detections(observation epochs) in the lightcurvefor this object | 
| npairposslope | UInt16Col | Number of positive slopes between allconsecutive pairwise lightcurve points(mag[i+1] brighter than mag[i]) | 
| percentiles | Float32Col, | [mag] [5th, 10th, 17.5th, 25th, 32.5th,shape=(12,)40th, 60th, 67.5th, 75th, 82.5th, 90th, 95th] percentiles in magnitude over nobs |
| periodsearch | Float32Col, | Periodogram peaks in [day],shape=(5,2)periodogram |
| valueprobnonqso | Float32Col | Probability of variability fit to non-quasar-like sourceprobqsoFloat32ColProbability of variability fit to quasar-like |
| sourcera | Float64Col | Right Ascension (deg)refchiFloat32ColChi-sq from reference catalogrefmagFloat32ColMagnitude from ref. | 
| catalogrefmagerr | Float32Col | Uncertainty in refmagrefsharpFloat32ColSharpness from ref. catalog |
