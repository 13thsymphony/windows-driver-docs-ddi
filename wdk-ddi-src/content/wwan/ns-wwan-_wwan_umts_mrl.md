---
UID: NS:wwan._WWAN_UMTS_MRL
title: "_WWAN_UMTS_MRL"
author: windows-driver-content
description: The WWAN_UMTS_MRL structure contains the measured results list (MRL) of neighboring UMTS cells.
old-location: netvista\wwan_umts_mrl.htm
old-project: netvista
ms.assetid: B62F63EB-747A-4672-9A79-5065A8BC04D1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_UMTS_MRL, PWWAN_UMTS_MRL, PWWAN_UMTS_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_UMTS_MRL, WWAN_UMTS_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_UMTS_MRL, netvista.wwan_umts_mrl, wwan/PWWAN_UMTS_MRL, wwan/WWAN_UMTS_MRL"
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
-	WWAN_UMTS_MRL
product:
- Windows
targetos: Windows
req.typenames: WWAN_UMTS_MRL, *PWWAN_UMTS_MRL
req.product: Windows 10 or later.
---

# _WWAN_UMTS_MRL structure
The <b>WWAN_UMTS_MRL</b> structure contains the measured results list (MRL) of neighboring UMTS cells.

## Syntax
```
typedef struct _WWAN_UMTS_MRL {
  ULONG ElementCount;
  BYTE  UMTSMrl[ANYSIZE_ARRAY];
} *PWWAN_UMTS_MRL, WWAN_UMTS_MRL;
```

## Members


`ElementCount`

The count of MRL entries following this member.

`UMTSMrl`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="https://msdn.microsoft.com/66460B28-C2B4-4F05-A133-31A753AF9489">WWAN_BASE_STATIONS_INFO</a>



<a href="https://msdn.microsoft.com/C1129291-D0E7-48F6-B317-1A0BCB6D25DC">WWAN_UMTS_MRL_INFO</a>



<a href="https://msdn.microsoft.com/62257D65-DCB9-43C3-A862-DAB31C27EF0A">WWAN_UMTS_SERVING_CELL_INFO</a>