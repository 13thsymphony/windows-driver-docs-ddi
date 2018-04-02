---
UID: NS:ntddndis._NDIS_PM_COUNTED_STRING
title: "_NDIS_PM_COUNTED_STRING"
author: windows-driver-content
description: The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management structures.
old-location: netvista\ndis_pm_counted_string.htm
old-project: netvista
ms.assetid: 070ee8e2-80ed-4380-89ac-bfb5db2bcf7e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING structure [Network Drivers Starting with Windows Vista], PNDIS_PM_COUNTED_STRING, PNDIS_PM_COUNTED_STRING structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_COUNTED_STRING, miniport_power_management_ref_baaff596-1c2a-4cfc-865a-bb3f55988218.xml, netvista.ndis_pm_counted_string, ntddndis/NDIS_PM_COUNTED_STRING, ntddndis/PNDIS_PM_COUNTED_STRING"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ntddndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_PM_COUNTED_STRING
product: Windows
targetos: Windows
req.typenames: NDIS_PM_COUNTED_STRING, *PNDIS_PM_COUNTED_STRING
---

# _NDIS_PM_COUNTED_STRING structure
The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in power management
  structures.

## Syntax
```
typedef struct _NDIS_PM_COUNTED_STRING {
  USHORT Length;
  WCHAR  String[NDIS_PM_MAX_STRING_SIZE + 1];
} *PNDIS_PM_COUNTED_STRING, NDIS_PM_COUNTED_STRING;
```

## Members


`Length`

The length, in bytes, of the string.

`String`

A WCHAR array that contains a NULL-terminated string that is limited to a maximum size of
     NDIS_PM_MAX_STRING_SIZE.

## Remarks
The NDIS_PM_COUNTED_STRING structure specifies a limited size string that is used in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566768">NDIS_PM_WOL_PATTERN</a> power management
    structures to define name strings.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ntddndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566760">NDIS_PM_PROTOCOL_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566768">NDIS_PM_WOL_PATTERN</a>