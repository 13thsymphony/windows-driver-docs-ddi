---
UID: NE:wditypes._WDI_DS_INFO
title: "_WDI_DS_INFO"
author: windows-driver-content
description: The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.
old-location: netvista\wdi_ds_info.htm
old-project: netvista
ms.assetid: 4375FF5C-8772-43AB-844B-4AD5E044AF55
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WDI_DS_CHANGED, WDI_DS_INFO, WDI_DS_INFO enumeration [Device and Driver Installation], WDI_DS_UNCHANGED, WDI_DS_UNKNOWN, _WDI_DS_INFO, netvista.wdi_ds_info, netvista.wifi_ds_info, wditypes/WDI_DS_CHANGED, wditypes/WDI_DS_INFO, wditypes/WDI_DS_UNCHANGED, wditypes/WDI_DS_UNKNOWN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	WDI_DS_INFO
product: Windows
targetos: Windows
req.typenames: WDI_DS_INFO
req.product: Windows 10 or later.
---

# _WDI_DS_INFO Enumeration
The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.

## Syntax
````
typedef enum _WDI_DS_INFO { 
  WDI_DS_CHANGED    = 1,
  WDI_DS_UNCHANGED  = 2,
  WDI_DS_UNKNOWN    = 3
} WDI_DS_INFO;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_DS_CHANGED</td>
                    <td>New DS.</td>
                </tr>
            
                <tr>
                    <td>WDI_DS_UNCHANGED</td>
                    <td>Same DS as previously associated.</td>
                </tr>
            
                <tr>
                    <td>WDI_DS_UNKNOWN</td>
                    <td>Unable to determine if the DS has changed.</td>
                </tr>
            
                <tr>
                    <td>WDI_DS_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |