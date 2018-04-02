---
UID: NS:dot11wdi._WDI_MAC_ADDRESS
title: "_WDI_MAC_ADDRESS"
author: windows-driver-content
description: The WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address.
old-location: netvista\wdi_mac_address.htm
old-project: netvista
ms.assetid: e170b797-f8bb-4d3c-a3ee-5fd1a817a500
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWDI_MAC_ADDRESS, PWDI_MAC_ADDRESS, PWDI_MAC_ADDRESS structure pointer [Network Drivers Starting with Windows Vista], WDI_MAC_ADDRESS, WDI_MAC_ADDRESS structure [Network Drivers Starting with Windows Vista], _WDI_MAC_ADDRESS, dot11wdi/PWDI_MAC_ADDRESS, dot11wdi/WDI_MAC_ADDRESS, netvista.wdi_mac_address, netvista.wifi_mac_address"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dot11wdi.h
api_name:
-	WDI_MAC_ADDRESS
product: Windows
targetos: Windows
req.typenames: WDI_MAC_ADDRESS, *PWDI_MAC_ADDRESS
---

# _WDI_MAC_ADDRESS structure
The 
  WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address.

## Syntax
```
typedef struct _WDI_MAC_ADDRESS {
  UINT8 Address[6];
} WDI_MAC_ADDRESS, *PWDI_MAC_ADDRESS;
```

## Members


`Address`

A Wi-Fi MAC address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |