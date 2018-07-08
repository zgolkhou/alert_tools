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
