---
UID: NF:ntifs.FsRtlInsertExtraCreateParameter
title: FsRtlInsertExtraCreateParameter function
author: windows-driver-content
description: The FsRtlInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list.
old-location: ifsk\fsrtlinsertextracreateparameter.htm
old-project: ifsk
ms.assetid: 77ac37eb-9750-4c56-8e1c-41b8a1f50a61
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlInsertExtraCreateParameter, FsRtlInsertExtraCreateParameter routine [Installable File System Drivers], fsrtlref_25aa9ff1-4921-4f96-98dc-04230d450e98.xml, ifsk.fsrtlinsertextracreateparameter, ntifs/FsRtlInsertExtraCreateParameter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FltInsertExtraCreateParameter routine is available starting with Windows Vista.
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
-	FsRtlInsertExtraCreateParameter
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlInsertExtraCreateParameter function
The <b>FsRtlInsertExtraCreateParameter</b> routine inserts an extra create parameter (ECP) context structure into an ECP list.

## Syntax

```
NTKERNELAPI NTSTATUS FsRtlInsertExtraCreateParameter(
  PECP_LIST EcpList,
  PVOID     EcpContext
);
```

## Parameters

`EcpList`

Pointer to the ECP list structure to which the ECP context structure, pointed to by the <i>EcpContext</i> parameter, should be added.

`EcpContext`

Pointer to the ECP context structure to be added to the ECP list, pointed to by the <i>EcpList</i> parameter.


## Return Value

<b>FsRtlInsertExtraCreateParameter</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure was successfully inserted into the given ECP list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given ECP context structure already exists in the given ECP list.  In the context of ECP list insertion, two ECP context structures are considered to be identical if they contain equal GUID values.

</td>
</tr>
</table>

## Remarks

The <b>FsRtlInsertExtraCreateParameter</b> routine assumes that the given ECP context structure to be inserted into the given ECP list was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a> routine.

Each ECP context structure inserted into the ECP list must have a unique GUID value. This unique value is set when the ECP context structure is allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FltInsertExtraCreateParameter routine is available starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541728">FltAllocateExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541734">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541741">FltAllocateExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542957">FltFreeExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543016">FltGetEcpListFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544339">FltRemoveExtraCreateParameter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544510">FltSetEcpListIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>