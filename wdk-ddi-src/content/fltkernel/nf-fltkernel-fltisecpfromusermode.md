---
UID: NF:fltkernel.FltIsEcpFromUserMode
title: FltIsEcpFromUserMode function
author: windows-driver-content
description: The FltIsEcpFromUserMode routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.
old-location: ifsk\fltisecpfromusermode.htm
old-project: ifsk
ms.assetid: d00cb2b1-b579-43c9-9e4d-cbdefd8a343a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_ea63cca7-3efb-4b45-b075-7efbc8138f88.xml, FltIsEcpFromUserMode, FltIsEcpFromUserMode routine [Installable File System Drivers], fltkernel/FltIsEcpFromUserMode, ifsk.fltisecpfromusermode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.dll: FltMgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	FltMgr.sys
api_name:
-	FltIsEcpFromUserMode
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltIsEcpFromUserMode function
The <b>FltIsEcpFromUserMode </b>routine is used to determine if an extra create parameter context structure (ECP) originated from user mode.

## Syntax

```
BOOLEAN FLTAPI FltIsEcpFromUserMode(
  PFLT_FILTER Filter,
  PVOID       EcpContext
);
```

## Parameters

`Filter`

Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

`EcpContext`

Pointer to the ECP to test.


## Return Value

The routine returns <b>TRUE</b> if the ECP originated in user mode and <b>FALSE</b> if the ECP originated in kernel mode.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | FltMgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541661">FltAcknowledgeEcp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>