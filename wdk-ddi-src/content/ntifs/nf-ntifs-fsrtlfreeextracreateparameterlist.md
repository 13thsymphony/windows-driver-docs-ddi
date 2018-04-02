---
UID: NF:ntifs.FsRtlFreeExtraCreateParameterList
title: FsRtlFreeExtraCreateParameterList function
author: windows-driver-content
description: The FsRtlFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure.
old-location: ifsk\fsrtlfreeextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 0d2f1204-0874-4ede-9931-be6f2dbc3c47
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlFreeExtraCreateParameterList, FsRtlFreeExtraCreateParameterList routine [Installable File System Drivers], fsrtlref_909d50be-4f8d-47dc-ad00-03d3f9eb4533.xml, ifsk.fsrtlfreeextracreateparameterlist, ntifs/FsRtlFreeExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlFreeExtraCreateParameterList routine is available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlFreeExtraCreateParameterList
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlFreeExtraCreateParameterList function
The <b>FsRtlFreeExtraCreateParameterList</b> routine frees an extra create parameter (ECP) list structure.

## Syntax

```
NTKERNELAPI VOID FsRtlFreeExtraCreateParameterList(
  PECP_LIST EcpList
);
```

## Parameters

`EcpList`

Pointer to the ECP list structure to be freed.


## Return Value

None

## Remarks

<b>FsRtlFreeExtraCreateParameterList</b> frees an ECP list structure including any list elements, if they exist.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FsRtlFreeExtraCreateParameterList routine is available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543305">FltInsertExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>