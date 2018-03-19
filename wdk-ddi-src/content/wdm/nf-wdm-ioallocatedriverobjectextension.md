---
UID: NF:wdm.IoAllocateDriverObjectExtension
title: IoAllocateDriverObjectExtension function
author: windows-driver-content
description: The IoAllocateDriverObjectExtension routine allocates a per-driver context area, called a driver object extension, and assigns a unique identifier to it.
old-location: kernel\ioallocatedriverobjectextension.htm
old-project: kernel
ms.assetid: e4e4e721-5b5c-48e8-99cb-d04c6b0eb807
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoAllocateDriverObjectExtension, IoAllocateDriverObjectExtension routine [Kernel-Mode Driver Architecture], k104_f7b420f3-bcd3-4be4-8f0d-e8d61314e880.xml, kernel.ioallocatedriverobjectextension, wdm/IoAllocateDriverObjectExtension
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAllocateDriverObjectExtension
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoAllocateDriverObjectExtension function
The <b>IoAllocateDriverObjectExtension</b> routine allocates a per-driver context area, called a <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">driver object extension</a>, and assigns a unique identifier to it.

## Syntax

````
NTSTATUS IoAllocateDriverObjectExtension(
  _In_  PDRIVER_OBJECT DriverObject,
  _In_  PVOID          ClientIdentificationAddress,
  _In_  ULONG          DriverObjectExtensionSize,
  _Out_ PVOID          *DriverObjectExtension
);
````

## Parameters

`DriverObject`

Pointer to a driver object to which the context area will be associated.

`ClientIdentificationAddress`

Specifies a unique identifier for the context area to be allocated.

`DriverObjectExtensionSize`

Specifies the length, in bytes, of the context area to be allocated.

`DriverObjectExtension`

Pointer to, on completion, the allocated context area.


## Return Value

<b>IoAllocateDriverObjectExtension</b> returns one of the following NTSTATUS codes:

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
Indicates that the routine allocated an extension of the requested size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the memory could not be allocated for the driver object extension.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
Indicates that a driver object extension with the given <i>ClientIdentificationAddress</i> already exists. 

</td>
</tr>
</table>

## Remarks

Memory allocated by the system for the driver object extension is resident storage and is accessible from any IRQL. The allocated storage is automatically freed by the I/O manager when the driver object is deleted.

Callers of this routine must provide a unique identifier for <i>ClientIdentificationAddress</i>. To retrieve a pointer to the context area, a caller passes the <i>ClientIdentificationAddress</i> to <a href="..\wdm\nf-wdm-iogetdriverobjectextension.md">IoGetDriverObjectExtension</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-iogetdriverobjectextension.md">IoGetDriverObjectExtension</a>