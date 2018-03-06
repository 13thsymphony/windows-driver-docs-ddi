---
UID: NS:wditypes._WDI_TYPE_PMK_NAME
title: "_WDI_TYPE_PMK_NAME"
author: windows-driver-content
description: The WDI_TYPE_PMK_NAME structure defines the PMKR0Name or PMKR1Name (802.11r).
old-location: netvista\wdi_type_pmk_name.htm
old-project: netvista
ms.assetid: 71020A3E-0839-4D73-B1B7-8A979BD0F5E0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME structure pointer [Network Drivers Starting with Windows Vista], WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME structure [Network Drivers Starting with Windows Vista], _WDI_TYPE_PMK_NAME, netvista.wdi_type_pmk_name, wditypes/PWDI_TYPE_PMK_NAME, wditypes/WDI_TYPE_PMK_NAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
api_name:
-	WDI_TYPE_PMK_NAME
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# _WDI_TYPE_PMK_NAME structure
The WDI_TYPE_PMK_NAME structure defines the PMKR0Name or PMKR1Name (802.11r).

## Syntax
````
typedef struct _WDI_TYPE_PMK_NAME {
  UINT8 Name[16];
} WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME;
````

## Members


`Name`

the PMKR0Name or PMKR1Name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |