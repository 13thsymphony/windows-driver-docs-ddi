---
UID: NS:ndis._LOCK_STATE
title: "_LOCK_STATE"
author: windows-driver-content
description: The LOCK_STATE structure tracks the state of a read/write lock.
old-location: netvista\lock_state.htm
old-project: netvista
ms.assetid: d23c7824-b2ab-4316-8d4c-474619a22223
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PLOCK_STATE, LOCK_STATE, LOCK_STATE structure [Network Drivers Starting with Windows Vista], PLOCK_STATE, PLOCK_STATE structure pointer [Network Drivers Starting with Windows Vista], _LOCK_STATE, ndis/LOCK_STATE, ndis/PLOCK_STATE, ndis_processor_group_ref_d04d3375-211e-4ef8-a30b-d2c6b98f9cc1.xml, netvista.lock_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use LOCK_STATE_EX instead.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	LOCK_STATE
product:
- Windows
targetos: Windows
req.typenames: LOCK_STATE, *PLOCK_STATE
---

# _LOCK_STATE structure
The <b>LOCK_STATE</b> structure tracks the state of a read/write lock. This structure is opaque to NDIS
   drivers.

## Syntax
```
typedef struct _LOCK_STATE {
  USHORT LockState;
  KIRQL  OldIrql;
} LOCK_STATE, *PLOCK_STATE;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use LOCK_STATE_EX instead. Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use LOCK_STATE_EX instead. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557070">LOCK_STATE_EX</a>