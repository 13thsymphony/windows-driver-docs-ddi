---
UID : NS:rilapitypes.RILGSMNMR
title : RILGSMNMR
author : windows-driver-content
description : This structure represents RILGSMNMR, which is a GSM network measurement report.
old-location : netvista\rilgsmnmr.htm
old-project : netvista
ms.assetid : 397d882d-c82a-4686-b9ca-58a2fade5256
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILGSMNMR, rilapitypes/RILGSMNMR, *LPRILGSMNMR, netvista.rilgsmnmr, RILGSMNMR structure [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILGSMNMR, RILGSMNMR"
req.product : Windows 10 or later.
---

# RILGSMNMR structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILGSMNMR, which is a GSM network measurement report.

## Syntax
````
struct RILGSMNMR {
  DWORD dwParams;
  DWORD dwMobileCountryCode;
  DWORD dwMobileNetworkCode;
  DWORD dwLocationAreaCode;
  DWORD dwCellID;
  DWORD dwARFCN;
  DWORD dwBaseStationID;
  DWORD dwRxLevel;
};
````

## Members


`dwARFCN`

Absolute radio frequency channel number of serving cell (0...1023)

`dwBaseStationID`

Base station ID of serving cell (0..63)

`dwCellID`

GSM Cell ID (0...65535)

`dwLocationAreaCode`

Location area code (0…65535)

`dwMobileCountryCode`

Mobile country code (0...999)

`dwMobileNetworkCode`

Mobile network code (0...999).

`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilgsmmnmrparammask.md">RILGSMMNMRPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`dwRxLevel`

Received signal strength of serving cell (0...63) where:

(x=0, RSS &lt; -110dBm

x=63, RSS &gt; -49dBm

0 &lt;x &lt;63, -110+x &lt; RSS &lt; -109+x)


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILGSMNMR structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>