# alert_tools
collection of tooling for working with the ZTF alert stream



### Light curve features calculated in the `summary` table

| Field | Type | Contents |
|:--------|:-------|:--------|
| `objectId` |  long | unique identifier for the object |
| `meanRA` | double | mean of the RA values for all the g, r, and i-band; J2000 [deg] |
| `meanDec` | double | mean of the Dec values for all the g, r, and i-band; J2000 [deg] |
| `gNobs` | int | number of observations for the g-band data  |
| `rNobs` | int | number of observations for the r-band data |
| `iNobs` | int | number of observations for the i-band data |
| `gMeanAB` | float | weighted mean value of the g-band magnitudes; AB [mag] |
| `rMeanAB` | float | weighted mean value of the r-band magnitudes; AB [mag] |
| `iMeanAB` | float | weighted mean value of the i-band magnitudes; AB [mag] |
| `gStdAB` | float | sample standard-deviation of the g-band magnitudes  |
| `rStdAB` | float | sample standard-deviation of the r-band magnitudes |
| `iStdAB` | float | sample standard-deviation of the i-band magnitudes |
| `gMeanJy` | double | weighted mean value of the g-band fluxes [Jy] |
| `rMeanJy` | double | weighted mean value of the r-band fluxes [Jy] |
| `iMeanJy` | double | weighted mean value of the i-band fluxes [Jy] |
| `gStdJy` | double | sample standard-deviation of the g-band fluxes |
| `rStdJy` | double | sample standard-deviation of the r-band fluxes |
| `iStdJy` | double | sample standard-deviation of the i-band fluxes |
| `gRB` | float | mean value of the g-band real-bogus data |
| `rRB` | float | mean value of the r-band real-bogus data |
| `iRB` | float | mean value of the i-band real-bogus data |
| `gClasstar` | float | mean value of the g-band Classtar data [(Galaxy) <-- 0 < Classtar score < 1 --> (Star)] |
| `rClasstar` | float | mean value of the r-band Classtar data [(Galaxy) <-- 0 < Classtar score < 1 --> (Star)] |
| `iClasstar` | float | mean value of the i-band Classtar data [(Galaxy) <-- 0 < Classtar score < 1 --> (Star)] |
| `Distnr` | float | distance to nearest source in reference image PSF-catalog within 30 arcsec [pixels] |
| `gMagnr` | float | g-band magnitude of nearest source in reference image PSF-catalog within 30 arcsec [mag] |
| `gDmagnr` | float | 1-sigma uncertainty in gMagnr within 30 arcsec [mag] |
| `rMagnr` | float | r-band magnitude of nearest source in reference image PSF-catalog within 30 arcsec [mag] |
| `rDmagnr` | float | 1-sigma uncertainty in rMagnr within 30 arcsec [mag] |
| `iMagnr` | float | i-band magnitude of nearest source in reference image PSF-catalog within 30 arcsec [mag] |
| `iDmagnr` | float |  1-sigma uncertainty in iMagnr within 30 arcsec [mag] |
| `gChinr` | float | DAOPhot chi parameter of nearest source in the g-band reference image PSF-catalog within 30 arcsec |
| `rChinr` | float | DAOPhot chi parameter of nearest source in the r-band reference image PSF-catalog within 30 arcsec |
| `iChinr` | float | DAOPhot chi parameter of nearest source in the i-band reference image PSF-catalog within 30 arcsec |
| `gSharpnr` | float | DAOPhot sharp parameter of nearest source in the g-band reference image PSF-catalog within 30 arcsec |
| `rSharpnr` | float | DAOPhot sharp parameter of nearest source in the r-band reference image PSF-catalog within 30 arcsec |
| `iSharpnr` | float | DAOPhot sharp parameter of nearest source in the i-band reference image PSF-catalog within 30 arcsec |
| `Distnrps1` | float | Distance of closest source from PS1 catalog; if exists within 30 arcsec [arcsec] |
| `gMagps1` | float | g-band PSF magnitude of closest source from PS1 catalog; if exists within 30 arcsec [mag] |
| `rMagps1` | float | r-band PSF magnitude of closest source from PS1 catalog; if exists within 30 arcsec [mag] |
| `iMagps1` | float | i-band PSF magnitude of closest source from PS1 catalog; if exists within 30 arcsec [mag] |
| `Sgscoreps1` | float |  Star/Galaxy score of closest source from PS1 catalog [(Galaxy) <-- 0 < Classtar score < 1 --> (Star)] |
