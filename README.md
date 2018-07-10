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
| `gMeanAB` | float | weighted mean value of the g-band magnitudes (mag) |
| `rMeanAB` | float | weighted mean value of the r-band magnitudes (mag) |
| `iMeanAB` | float | weighted mean value of the i-band magnitudes (mag) |
| `gStdAB` | float | sample standard-deviation of the g-band magnitudes  |
| `rStdAB` | float | sample standard-deviation of the r-band magnitudes |
| `iStdAB` | float | sample standard-deviation of the i-band magnitudes |
| `gMeanJy` | double | DOUBLE |
| `rMeanJy` | double | OUBLE |
| `iMeanJy` | double | DOUBLE |
| `gStdJy` | double | DOUBLE |
| `rStdJy` | double | DOUBLE |
| `iStdJy` | double |  DOUBLE |
| `gRB` | float | FLOAT |
| `rRB` | float | FLOAT |
| `iRB` | float | FLOAT |
| `gClasstar` | float | FLOAT |
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
