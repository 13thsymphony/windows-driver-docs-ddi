---
UID: NE:dot11wdi._WDI_INTERCONNECT_TYPE
title: "_WDI_INTERCONNECT_TYPE"
author: windows-driver-content
description: The WDI_INTERCONNECT_TYPE enumeration defines the interconnect types.
old-location: netvista\wdi_interconnect_type.htm
old-project: netvista
ms.assetid: 58cb1ead-94a1-4587-bb2a-7b8e23f42eeb
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: WDI_INTERCONNECT_MEMORY_MAPPED, WDI_INTERCONNECT_MESSAGE_BASED, WDI_INTERCONNECT_TYPE, WDI_INTERCONNECT_TYPE enumeration [Network Drivers Starting with Windows Vista], WDI_INTERCONNECT_UNKNOWN, _WDI_INTERCONNECT_TYPE, dot11wdi/WDI_INTERCONNECT_MEMORY_MAPPED, dot11wdi/WDI_INTERCONNECT_MESSAGE_BASED, dot11wdi/WDI_INTERCONNECT_TYPE, dot11wdi/WDI_INTERCONNECT_UNKNOWN, netvista.wdi_interconnect_type, netvista.wifi_interconnect_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
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
-	dot11wdi.h
api_name:
-	WDI_INTERCONNECT_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_INTERCONNECT_TYPE
---

# _WDI_INTERCONNECT_TYPE Enumeration
The WDI_INTERCONNECT_TYPE enumeration defines the interconnect types.

## Syntax
```
typedef enum _WDI_INTERCONNECT_TYPE {
  WDI_INTERCONNECT_MEMORY_MAPPED  ,
  WDI_INTERCONNECT_MESSAGE_BASED  ,
  WDI_INTERCONNECT_UNKNOWN
} WDI_INTERCONNECT_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>WDI_INTERCONNECT_MEMORY_MAPPED</td>
                    <td>Target can access system memory (for example, PCI-based interconnect).</td>
                </tr>
            
                <tr>
                    <td>WDI_INTERCONNECT_MESSAGE_BASED</td>
                    <td>Message based interconnect (for example, USB or SDIO).</td>
                </tr>
            
                <tr>
                    <td>WDI_INTERCONNECT_UNKNOWN</td>
                    <td>Unspecified interconnect type.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |