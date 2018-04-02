---
UID: NE:wditypes._WDI_ENCAPSULATION_TYPE
title: "_WDI_ENCAPSULATION_TYPE"
author: windows-driver-content
description: The WDI_ENCAPSULATION_TYPE enumeration defines the Wi-Fi encapsulation types.
old-location: netvista\wdi_encapsulation_type.htm
old-project: netvista
ms.assetid: 6EDCC69B-F156-416B-9824-5E26F9834D14
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: WDI_ENCAPSULATION_802_1H, WDI_ENCAPSULATION_RFC_1042, WDI_ENCAPSULATION_TYPE, WDI_ENCAPSULATION_TYPE enumeration [Device and Driver Installation], _WDI_ENCAPSULATION_TYPE, netvista.wdi_encapsulation_type, netvista.wifi_encapsulation_type, wditypes/WDI_ENCAPSULATION_802_1H, wditypes/WDI_ENCAPSULATION_RFC_1042, wditypes/WDI_ENCAPSULATION_TYPE
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
-	WDI_ENCAPSULATION_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_ENCAPSULATION_TYPE
req.product: Windows 10 or later.
---

# _WDI_ENCAPSULATION_TYPE Enumeration
The WDI_ENCAPSULATION_TYPE enumeration defines the Wi-Fi encapsulation types.

## Syntax
```
typedef enum _WDI_ENCAPSULATION_TYPE {
  WDI_ENCAPSULATION_RFC_1042  ,
  WDI_ENCAPSULATION_802_1H
} WDI_ENCAPSULATION_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>WDI_ENCAPSULATION_RFC_1042</td>
                    <td>The encapsulation that is defined in IETF RFC 1042.</td>
                </tr>
            
                <tr>
                    <td>WDI_ENCAPSULATION_802_1H</td>
                    <td>The encapsulation that is defined in the IEEE 802.1h-1997 standard.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |