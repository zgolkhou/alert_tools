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
