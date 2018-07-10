# alert_tools
collection of tooling for working with the ZTF alert stream



### ztf.alert.candidate

| Field | Type | Contents |
|:--------|:-------|:--------|
| `jd` | double | Observation Julian date at start of exposure [days] | 
| `fid` | int | Filter ID (1=g; 2=r; 3=i) | 
| `pid` | long | Processing ID for image | 
| `diffmaglim` | [float, null], default: null | 5-sigma mag limit in difference image based on PSF-fit photometry [mag] | 
| `pdiffimfilename` | [string, null], default: null | filename of positive (sci minus ref) difference image | 
| `programpi` | [string, null], default: null | Principal investigator attached to program ID | 
| `programid` | int | Program ID: encodes either public, collab, or caltech mode | 
| `candid` | long | Candidate ID from operations DB | 


| `objectId` |  varchar(20) | www |
| `meanRA` | double | www |
| `meanDec` | double | eee |
| `gNobs` | int | rrrr |
| `rNobs` | int | sss |
| `iNobs` | int | ddd |
| `gMeanAB` | float |  FLOAT |
| `rMeanAB` | float | FLOAT |
| `iMeanAB` | float | FLOAT |
| `gStdAB` | float | FLOAT |
| `rStdAB` | float | FLOAT |
| `iStdAB` | float | FLOAT |
| `gMeanJy` | double | DOUBLE |
| `rMeanJy` | double | OUBLE |
| `iMeanJy` | double | DOUBLE |
| `gStdJy` | double | DOUBLE |
| `rStdJy` | double | DOUBLE |
| `iStdJy` | double  DOUBLE |
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
| `Sgscoreps1` | float |  FLOAT|
