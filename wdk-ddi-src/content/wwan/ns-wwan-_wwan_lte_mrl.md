---
UID: NS:wwan._WWAN_LTE_MRL
title: "_WWAN_LTE_MRL"
author: windows-driver-content
description: The WWAN_LTE_MRL structure represents the measured results list (MRL) of neighboring LTE cells.
old-location: netvista\wwan_lte_mrl.htm
old-project: netvista
ms.assetid: 5959B7A7-147D-4F20-82CC-EC1DEAAE3494
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_LTE_MRL, PWWAN_LTE_MRL, PWWAN_LTE_MRL structure pointer [Network Drivers Starting with Windows Vista], WWAN_LTE_MRL, WWAN_LTE_MRL structure [Network Drivers Starting with Windows Vista], _WWAN_LTE_MRL, netvista.wwan_lte_mrl, wwan/PWWAN_LTE_MRL, wwan/WWAN_LTE_MRL"
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
-	WWAN_LTE_MRL
product: Windows
targetos: Windows
req.typenames: WWAN_LTE_MRL, *PWWAN_LTE_MRL
req.product: Windows 10 or later.
---

# _WWAN_LTE_MRL structure
The <b>WWAN_LTE_MRL</b> structure represents the measured results list (MRL) of neighboring LTE cells.

## Syntax
````
typedef struct _WWAN_LTE_MRL {
  ULONG ElementCount;
  BYTE  LTEMrl[ANYSIZE_ARRAY];
} WWAN_LTE_MRL, *PWWAN_LTE_MRL;
````

## Members


`ElementCount`

The count of MRL entries following this member.

`LTEMrl`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_lte_mrl_info.md">WWAN_LTE_MRL_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_lte_serving_cell_info.md">WWAN_LTE_SERVING_CELL_INFO</a>



<a href="..\wwan\ns-wwan-_wwan_base_stations_info.md">WWAN_BASE_STATIONS_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>