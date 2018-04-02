---
UID: NF:ntifs.IoCheckEaBufferValidity
title: IoCheckEaBufferValidity function
author: windows-driver-content
description: The IoCheckEaBufferValidity routine checks whether the specified extended attribute (EA) buffer is valid.
old-location: ifsk\iocheckeabuffervalidity.htm
old-project: ifsk
ms.assetid: 1f9a4fcb-0e70-4f13-bd38-e87bee909a26
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoCheckEaBufferValidity, IoCheckEaBufferValidity function [Installable File System Drivers], ifsk.iocheckeabuffervalidity, ioref_cda82410-a6a9-40df-83ac-c1376a129a7a.xml, ntifs/IoCheckEaBufferValidity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCheckEaBufferValidity
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoCheckEaBufferValidity function
The <b>IoCheckEaBufferValidity</b> routine checks whether the specified extended attribute (EA) buffer is valid.

## Syntax

```
NTKERNELAPI NTSTATUS IoCheckEaBufferValidity(
  PFILE_FULL_EA_INFORMATION EaBuffer,
  ULONG                     EaLength,
  PULONG                    ErrorOffset
);
```

## Parameters

`EaBuffer`

Pointer to the buffer containing the EAs to be checked.

`EaLength`

Length, in bytes, of <i>EaBuffer</i>.

`ErrorOffset`

Pointer to a variable that receives the offset of the offending entry in the EA buffer if an error is found. This variable is only valid if an error occurs.


## Return Value

<b>IoCheckEaBufferValidity</b> returns STATUS_SUCCESS if the EA buffer is valid; otherwise it returns STATUS_EA_LIST_INCONSISTENT.

## Remarks

<b>IoCheckEaBufferValidity</b> checks each FILE_FULL_EA_INFORMATION entry in the specified EA buffer to ensure that the following conditions are met:

<ul>
<li>
The entire entry must fall within the buffer.

</li>
<li>
The value of <b>EaName</b> must be a null-terminated character array.

</li>
<li>
The value of <b>EaNameLength</b> must match the length in bytes of the <b>EaName</b> array (not including the zero-terminator).

</li>
<li>
For all entries except the last, the value of <b>NextEntryOffset</b> must be greater than zero and must fall on a ULONG boundary.

</li>
</ul>
In addition, <b>IoCheckEaBufferValidity</b> checks the EA buffer to ensure that the following conditions are met:

<ul>
<li>
The length passed in <i>EaLength</i> matches the actual length of the buffer.

</li>
<li>
The actual buffer length is nonnegative.

</li>
</ul>
To be valid, the EA buffer must meet all of these conditions.

<div class="alert"><b>Warning</b>  
      <b>IoCheckEaBufferValidity</b> does not perform any synchronization to ensure that the contents of <i>EaBuffer</i> do not change asynchronously. If a user-mode application can access the buffer in another thread, the application could change the buffer while <b>IoCheckEaBufferValidity</b> is running. This change might cause the routine to return incorrect information.  To avoid this scenario, the driver should copy the buffer before calling <b>IoCheckEaBufferValidity</b>.  After the buffer has been validated, the caller should use only the validated copy, not the original buffer.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a>