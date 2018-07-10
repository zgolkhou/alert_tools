# alert_tools
collection of tooling for working with the ZTF alert stream



### ztf.alert.candidate

| Field | Type | Contents |
|:--------|:-------|:--------|
| `objectId` |  long | unique identifier for the object |
| `meanRA` | double | mean of the RA values for all the g, r, and i-band (J2000) |
| `meanDec` | double | mean of the Dec values for all the g, r, and i-band (J2000) |
| `gNobs` | int | number of observations for the g-band data  |
| `rNobs` | int | number of observations for the r-band data |
| `iNobs` | int | number of observations for the i-band data |
| `gMeanAB` | float | weighted mean value of the g-band magnitudes (AB mag) |
| `rMeanAB` | float | weighted mean value of the r-band magnitudes (AB mag) |
| `iMeanAB` | float | weighted mean value of the i-band magnitudes (AB mag) |
| `gStdAB` | float | sample standard-deviation of the g-band magnitudes  |
| `rStdAB` | float | sample standard-deviation of the r-band magnitudes |
| `iStdAB` | float | sample standard-deviation of the i-band magnitudes |
| `gMeanJy` | double | weighted mean value of the g-band fluxes (Jy) |
| `rMeanJy` | double | weighted mean value of the r-band fluxes (Jy) |
| `iMeanJy` | double | weighted mean value of the i-band fluxes (Jy) |
| `gStdJy` | double | sample standard-deviation of the g-band fluxes |
| `rStdJy` | double | sample standard-deviation of the r-band fluxes |
| `iStdJy` | double | sample standard-deviation of the i-band fluxes |
| `gRB` | float | mean value of the g-band real-bogus data |
| `rRB` | float | mean value of the r-band real-bogus data |
| `iRB` | float | mean value of the i-band real-bogus data |
| `gClasstar` | float | mean value of the g-band Classtar data [Galaxy <-- 0 <= Classtar score =<1 --> Star] |
| `rClasstar` | float | FLOAT |
| `iClasstar` | float |  FLOAT |
| `Distnr` | float | FLOAT |
| `gMagnr` | float | FLOAT |
| `gDmagnr` | float | FLOAT |
| `rMagnr` | float | FLOAT |
| `rDmagnr` | float | FLOAT |
| `iMagnr` | float | FLOAT |
| `iDmagnr` | float | FLOAT |
| `gChinr` | float | FLOAT |
| `rChinr` | float | FLOAT |
| `iChinr` | float | FLOAT |
| `gSharpnr` | float | FLOAT |
| `rSharpnr` | float | FLOAT |
| `iSharpnr` | float | FLOAT|
| `Distnrps1` | float | FLOAT |
| `gMagps1` | float | FLOAT |
| `rMagps1` | float | FLOAT |
| `iMagps1` | float | FLOAT |
| `Sgscoreps1` | float |  FLOAT |
