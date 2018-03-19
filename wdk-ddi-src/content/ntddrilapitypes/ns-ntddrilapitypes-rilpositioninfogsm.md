---
UID: NS:ntddrilapitypes.RILPOSITIONINFOGSM
title: RILPOSITIONINFOGSM
author: windows-driver-content
description: This structure represents RILPOSITIONINFOGSM.
old-location: netvista\rilpositioninfogsm.htm
old-project: netvista
ms.assetid: 86b0510b-54ed-463e-b5d4-a34b0a98c00e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILPOSITIONINFOGSM, RILPOSITIONINFOGSM, RILPOSITIONINFOGSM structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfogsm, rilapitypes/RILPOSITIONINFOGSM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILPOSITIONINFOGSM
product: Windows
targetos: Windows
req.typenames: RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
---

# RILPOSITIONINFOGSM structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILPOSITIONINFOGSM.

## Syntax
````
struct RILPOSITIONINFOGSM {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwTimingAdvance;
  DWORD dwARFCN;
  DWORD dwBaseStationID;
  DWORD dwRxLevel;
};
````

## Members


`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfogsmparammask.md">RILPOSITIONINFOGSMPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`dwMobileCountryCode`

Mobile country code (0...999)

`dwMobileNetworkCode`

Mobile Network Code (0...999)

`dwLocationAreaCode`

Location Area Code (0…65535)

`dwCellID`

Cell ID (0...65535)

`dwTimingAdvance`

Timing Advance (0...255) in bit periods, where a bit period is 48/13µs

`dwARFCN`

Absolute radio frequency channel number of serving cell (0...1023)

`dwBaseStationID`

Radio base station ID of serving cell (0..63)

`dwRxLevel`

Received signal strength of serving cell (0...63) where:

(x=0, RSS &lt; -110dBm

x=63, RSS &gt; -49dBm

0 &lt;x &lt;63, -110+x &lt; RSS &lt; -109+x)


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h, Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>