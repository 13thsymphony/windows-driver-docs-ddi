---
UID: NS:wwan._WWAN_PCO_VALUE
title: "_WWAN_PCO_VALUE"
author: windows-driver-content
description: The WWAN_PCO_VALUE structure represents the PCO information payload from the network as defined in the 3GPP TS24.008 spec.
old-location: netvista\wwan_pco_value.htm
old-project: netvista
ms.assetid: 45A499CE-2C9A-4070-BEF8-880E7673FA8E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PCO_VALUE, PWWAN_PCO_VALUE, PWWAN_PCO_VALUE structure pointer [Network Drivers Starting with Windows Vista], WWAN_PCO_VALUE, WWAN_PCO_VALUE structure [Network Drivers Starting with Windows Vista], _WWAN_PCO_VALUE, netvista.wwan_pco_value, wwan/PWWAN_PCO_VALUE, wwan/WWAN_PCO_VALUE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	wwan.h
api_name:
-	WWAN_PCO_VALUE
product:
- Windows
targetos: Windows
req.typenames: WWAN_PCO_VALUE, *PWWAN_PCO_VALUE
req.product: Windows 10 or later.
---

# _WWAN_PCO_VALUE structure
The <b>WWAN_PCO_VALUE</b> structure represents the PCO information payload from the network as defined in the 3GPP TS24.008 spec.

## Syntax
```
typedef struct _WWAN_PCO_VALUE {
  ULONG         Size;
  WWAN_PCO_TYPE Type;
  BYTE          PcoData[WWAN_PCO_OCT_BUF_LEN];
} *PWWAN_PCO_VALUE, WWAN_PCO_VALUE;
```

## Members


`Size`

The length of the PCO value that is valid in <b>PcoData</b>, which will be octets 3 (octet 1 to 3) + m*protocol element length + n*container element length. This is defined in the 3GPP TS24.008 spec, Section 10.5, since PCO is Type 4 information.

`Type`

Indicates whether the PCO value being passed up is the original structure that was received by the modem or a subset of the full PCO structure and has the header synthesized. For more info, see <a href="https://msdn.microsoft.com/0AD10F14-EBDB-45F8-A435-1D0A6D6FEFFF">WWAN_PCO_TYPE</a>.

`PcoData`



## Remarks
Because some modems can currently only pass up operator specific PCO elements, the modem should pass up the information following the structure defined by 3GPP TS24.008 with the accurate synthesized header values for the content that is being passed up to the host.

For example, if the modem received a PCO with 3 protocols and 3 containers, and is only passing up the 2 operator specific element containers to the host, the modem will make changes to the header that indicates the length of the PCO structure. This is to reflect the fact that there are only the two containers by subtracting the length of the 3 protocols.

The following figure shows  	a full PCO structure as defined in the 3G TS24.008 spec.

<img alt="Full PCO structure" src="images/pco_structure_small.png"/>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-protocol-configuration-operations--pco-">MB Protocol Configuration Operations (PCO)</a>



<a href="https://msdn.microsoft.com/C71187C5-74B6-450A-8461-BB9FDF60DB8D">NDIS_WWAN_PCO_STATUS</a>



<a href="https://msdn.microsoft.com/0AD10F14-EBDB-45F8-A435-1D0A6D6FEFFF">WWAN_PCO_TYPE</a>