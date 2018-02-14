---
UID: NS:rilapitypes.RILPOSITIONINFOLTE
title: RILPOSITIONINFOLTE
author: windows-driver-content
description: This structure represents the RILPOSITIONINFOLTE.
old-location: netvista\rilpositioninfolte.htm
old-project: netvista
ms.assetid: 40f4dfca-7ee6-48d2-b0a4-8a563587b2ab
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE, netvista.rilpositioninfolte, RILPOSITIONINFOLTE structure [Network Drivers Starting with Windows Vista], rilapitypes/RILPOSITIONINFOLTE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPOSITIONINFOLTE
product: Windows
targetos: Windows
req.typenames: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE"
req.product: Windows 10 or later.
---

# RILPOSITIONINFOLTE structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILPOSITIONINFOLTE.

## Syntax
````
struct RILPOSITIONINFOLTE {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwCellID;
  DWORD dwEARFCN;
  DWORD dwPhysCellID;
  DWORD dwTAC;
  DWORD dwRSRP;
  DWORD dwRSRQ;
  DWORD dwTimingAdvance;
};
````

## Members


`dwCellID`

Cell identity (28 bits)

`dwEARFCN`

Radio Frequency Channel Number of serving cell (0...65535)

`dwMobileCountryCode`

Mobile country code (0...999)

`dwMobileNetworkCode`

Mobile Network Code (0...999)

`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilpositioninfolteparammask.md">RILPOSITIONINFOLTEPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`dwPhysCellID`

Physical CellID (0...503)

`dwRSRP`

Average Reference Signal Received Power. Range (-1400 ... -440) in units of 0.1dBm.

`dwRSRQ`

Average Reference Signal Received Quality. Range (-200 ... -30) in units of 0.1dBm.

`dwTAC`

Tracking area code (0...65535)

`dwTimingAdvance`

Timing Advance (0...255) in bit periods, where a bit period is 48/13µs


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILPOSITIONINFOLTE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>