---
UID: NS:dot11wdi._WDI_P2P_SERVICE_NAME_HASH
title: "_WDI_P2P_SERVICE_NAME_HASH"
author: windows-driver-content
description: The WDI_P2P_SERVICE_NAME_HASH structure defines a hash of a WFDS Service Name.
old-location: netvista\wdi_p2p_service_name_hash.htm
old-project: netvista
ms.assetid: B03C779A-ED25-48D7-BB5E-EB95ED1B2D00
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: dot11wdi/PWDI_P2P_SERVICE_NAME_HASH, dot11wdi/WDI_P2P_SERVICE_NAME_HASH, *PWDI_P2P_SERVICE_NAME_HASH, WDI_P2P_SERVICE_NAME_HASH structure [Network Drivers Starting with Windows Vista], WDI_P2P_SERVICE_NAME_HASH, PWDI_P2P_SERVICE_NAME_HASH, netvista.wdi_p2p_service_name_hash, PWDI_P2P_SERVICE_NAME_HASH structure pointer [Network Drivers Starting with Windows Vista], _WDI_P2P_SERVICE_NAME_HASH
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_P2P_SERVICE_NAME_HASH
product: Windows
targetos: Windows
req.typenames: "*PWDI_P2P_SERVICE_NAME_HASH, WDI_P2P_SERVICE_NAME_HASH"
---

# _WDI_P2P_SERVICE_NAME_HASH structure
The 
  WDI_P2P_SERVICE_NAME_HASH structure defines a hash of a WFDS Service Name.

## Syntax
````
typedef struct _WDI_P2P_SERVICE_NAME_HASH {
  UINT8 Hash[6];
} WDI_P2P_SERVICE_NAME_HASH, *PWDI_P2P_SERVICE_NAME_HASH;
````

## Members


`Hash`

Hash of a WFDS Service Name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |