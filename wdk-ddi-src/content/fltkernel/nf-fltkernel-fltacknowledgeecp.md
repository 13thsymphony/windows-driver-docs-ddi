---
UID: NF:fltkernel.FltAcknowledgeEcp
title: FltAcknowledgeEcp function
author: windows-driver-content
description: The FltAcknowledgeEcp routine is used to mark an extra create parameter context structure (ECP) as acknowledged.
old-location: ifsk\fltacknowledgeecp.htm
old-project: ifsk
ms.assetid: 89fd8a33-9b2e-401a-9b48-49b4b19d3cb2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltAcknowledgeEcp, FltAcknowledgeEcp routine [Installable File System Drivers], FltApiRef_a_to_d_17c8b1d4-47d1-4871-be9d-57986967a083.xml, fltkernel/FltAcknowledgeEcp, ifsk.fltacknowledgeecp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAcknowledgeEcp
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltAcknowledgeEcp function
The <b>FltAcknowledgeEcp</b> routine is used to mark an extra create parameter context structure (ECP) as acknowledged.

## Syntax

```
VOID FLTAPI FltAcknowledgeEcp(
  PFLT_FILTER Filter,
  PVOID       EcpContext
);
```

## Parameters

`Filter`

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`EcpContext`

Pointer to the ECP to mark as acknowledged.


## Return Value

None

## Remarks

This routine is available in Windows Vista and later. 

The ECP pointed to by the <i>EcpContext</i> parameter is marked as "acknowledged" by this routine.  This acknowledgment could indicate a number of things, including whether the ECP has been looked at, used, processed, and so on.  Note that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a> routine can be used to determine if a particular ECP has been marked as acknowledged.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543321">FltIsEcpAcknowledged</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543325">FltIsEcpFromUserMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>