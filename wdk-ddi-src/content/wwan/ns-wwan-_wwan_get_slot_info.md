---
UID: NS:wwan._WWAN_GET_SLOT_INFO
title: "_WWAN_GET_SLOT_INFO"
author: windows-driver-content
description: The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.
old-location: netvista\wwan_get_slot_info_status.htm
old-project: netvista
ms.assetid: 62955CA4-8631-4A85-8E78-5A91A9DA0069
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO, PWWAN_GET_SLOT_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_GET_SLOT_INFO, WWAN_GET_SLOT_INFO structure [Network Drivers Starting with Windows Vista], _WWAN_GET_SLOT_INFO, netvista.wwan_get_slot_info_status, wwan/PWWAN_GET_SLOT_INFO, wwan/WWAN_GET_SLOT_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
-	WWAN_GET_SLOT_INFO
product: Windows
targetos: Windows
req.typenames: WWAN_GET_SLOT_INFO, *PWWAN_GET_SLOT_INFO
req.product: Windows 10 or later.
---

# _WWAN_GET_SLOT_INFO structure
The WWAN_GET_SLOT_INFO structure contains the slot index to specify which slot's status a query request is for.

## Syntax
```
typedef struct _WWAN_GET_SLOT_INFO {
  ULONG SlotIndex;
} *PWWAN_GET_SLOT_INFO, WWAN_GET_SLOT_INFO;
```

## Members


`SlotIndex`

Represents the index of the SIM slot. <b>SlotIndex</b> can be mapped to either a physical or embedded SIM slot and may be expanded to soft SIM in the future.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1703 Windows 10, version 1703 |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/214AFAD3-B211-4D66-8CFC-58F8EB407B83">NDIS_WWAN_GET_SLOT_INFO</a>