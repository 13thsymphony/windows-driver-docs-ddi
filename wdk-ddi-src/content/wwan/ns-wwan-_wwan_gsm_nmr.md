---
UID: NS:wwan._WWAN_GSM_NMR
title: "_WWAN_GSM_NMR"
author: windows-driver-content
description: The WWAN_GSM_NMR structure represents the network measurement report (NMR) of neighboring GSM cells.
old-location: netvista\wwan_gsm_nmr.htm
old-project: netvista
ms.assetid: ADEEB57F-79FF-4AA7-84AF-FED413E47057
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_GSM_NMR, PWWAN_GSM_NMR, PWWAN_GSM_NMR structure pointer [Network Drivers Starting with Windows Vista], WWAN_GSM_NMR, WWAN_GSM_NMR structure [Network Drivers Starting with Windows Vista], _WWAN_GSM_NMR, netvista.wwan_gsm_nmr, wwan/PWWAN_GSM_NMR, wwan/WWAN_GSM_NMR"
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
-	WWAN_GSM_NMR
product: Windows
targetos: Windows
req.typenames: WWAN_GSM_NMR, *PWWAN_GSM_NMR
req.product: Windows 10 or later.
---

# _WWAN_GSM_NMR structure
The <b>WWAN_GSM_NMR</b> structure represents the network measurement report (NMR) of neighboring GSM cells.

## Syntax
````
typedef struct _WWAN_GSM_NMR {
  ULONG ElementCount;
  BYTE  GSMNmr[ANYSIZE_ARRAY];
} WWAN_GSM_NMR, *PWWAN_GSM_NMR;
````

## Members


`ElementCount`

The count of NMR entries following this member.

`GSMNmr`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_gsm_nmr_info.md">WWAN_GSM_NMR_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_gsm_serving_cell_info.md">WWAN_GSM_SERVING_CELL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>



<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>