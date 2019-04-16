**[ZTF FEATURES](#ztf-features)** ||
**[ASSASN VARIABILITY](#assasn-variability)** ||
**[CESIUM_GENERAL](#cesium-general)** ||
**[CESIUM CADENCE](#cesium-cadence)** ||
**[CESIUM LOMB-SCARGLE](#cesium-lomb-scargle)** 


#### ZTF10: all sources (grouped by pbjectId) in the ZTF Alert Database with nobs >= 10.
#### We cross-matched ZTF10 with ASSASN Variablity Catalog using a matching radius of 2.0''.


```
Source for the CESIUM Features: http://cesium-ml.org/docs/feature_table.html
```

---

### ZTF FEATURES

| ZTF Features | Description |
|:--------|:-------|
| objectId | Observation Julian date at start of exposure [days] |
| ra | Right Ascension of candidate; J2000 [deg] |
| dec | Declination of candidate; J2000 [deg] |
| axsdis | Distance in [rad] between ZTF10 and ASSASN Variability Catalog sources using AXS (radius=2.0")|
| filter | Filter ID (1=g; 2=r; 3=i) |
| jd | Observation Julian date at start of exposure [days] |
| magpsf | magnitude from PSF-fit photometry [mag] |
| sigmapsf | 1-sigma uncertainty in magpsf [mag] |
| diffmaglim | 5-sigma mag limit in difference image based on PSF-fit photometry [mag] |
| rb | RealBogus quality score; range is 0 to 1 where closer to 1 is more reliable |
| isdiffpos | t or 1 => candidate is from positive (sci minus ref) subtraction; f or 0 => candidate is from negative (ref minus sci) subtraction |
| magnr | magnitude of nearest source in reference image PSF-catalog within 30 arcsec [mag] |
| sigmagnr | 1-sigma uncertainty in magnr within 30 arcsec [mag] |
| distnr |  distance to nearest source in reference image PSF-catalog within 30 arcsec [pixels] |
| classtar | Star/Galaxy classification score from SExtractor |
| sgscore1 | Star/Galaxy score of closest source from PS1 catalog 0 <= sgscore <= 1 where closer to 1 implies higher likelihood of being a star |
| distpsnr1 | Distance of closest source from PS1 catalog; if exists within 30 arcsec [arcsec] |
| pid | Processing ID for image |
| magzpsci | Magnitude zero point for photometry estimates [mag] |
| magzpsciunc | Magnitude zero point uncertainty (in magzpsci) [mag] |
| NOTE: | Please see this Jupyter notbooked on DIRAC GitHub for the following calcuted featurs: https://github.com/dirac-institute/alert_tools/blob/master/notebooks/ZTF_LCs_PhotometryCorr_Compare_MatchFiles.ipynb |
| ref_flux | Calculated flux of the source in reference image: 10**( 0.4* ( 'magzpsci' - 'magnr') ) |
| ref_sigflux | Calculated flux uncertainty of the source in reference image: 'sigmagnr'/1.0857 * 'ref_flux' |
| difference_flux | Calculated flux of the source in difference image: 10**( 0.4* ('magzpsci' - 'magpsf') ) |
| difference_sigflux | Calculated flux uncertainty of the source in difference image |
| dc_flux | Calculated flux of the source in science image: 'ref_flux' + 'isdiffpos' * 'difference_flux' |
| dc_sigflux | Calculated flux uncertainty of the source in science image |
| dc_mag | Calculated magnitude of the source in science image: 'magzpsci' - 2.5 * log10('dc_flux') | 
| dc_sigmag | Calculated magnitude uncertainty of the source in science image: 'dc_sigflux' / 'dc_flux' * 1.0857 |

---

### ASSASN VARIABILITY

| ASSASN Variability Features | Description |
|:--------|:-------|
| ASAS-SN_Name | ASASSN Name |
| Other_Names | Other Names |
| LCID | ASSASN light curve ID |
| Type | EW, SR, RRAB, EA, M, EB, RRC, ROT, HADS, DCEP, VAR, L, YSO, UG, ... (please check "The ASAS-SN Catalog of Variable Stars II: Uniform Classification of 412,000 Known Variables " (https://arxiv.org/abs/1809.07329) |
| Mean_VMag | Mean of V-band magnitudes |
| assasn_amplitude | ASSASN's derived amplitude based on V-band light curve |
| Period | ASSASN's derived period based on V-band light curve |
| Url | URL address to data source | 
| Reference | The ASAS-SN Catalog of Variable Stars: I or II |
| Dist | Probabilistic distance estimates (in pc) from Bailer-Jones et al. (2018) |
| Parallax | Gaia DR2 parallax |
| Parallax_Error | Gaia DR2 parallax error |
| Gmag | Absolute Gaia DR2 G-band magnitude |
| Bpmag | Gaia DR2 BP-band magnitude |
| Rpmag | Gaia DR2 RP-band magnitude |
| Jmag | 2MASS J-band magnitude |
| Hmag | 2MASS H-band magnitude |
| Kmag | 2MASS K-band magnitude |
| W1mag | WISE W1 magnitude |
| W2mag | WISE W2 magnitude |
| W3mag | WISE W3 magnitude |
| W4mag | WISE W4 magnitude |
| BP-RR | Gaia DR2 G_BP - G_PR color |
| J-K | 2MASS J - Ks color |
| W1-W2 | WISE W1 - W2 color |
| W3-W4 | WISE W3 - W4 color |
| Sllk_Statistic | String Length Lafler Kinman (SLLK) statistic |
| RF_Regression_Score | Regression score of the implemented random-forest Model by ASSASN |
| Classification_Probability | Probability of the assigned type/class |
| Epoch_HJD |  |

---
