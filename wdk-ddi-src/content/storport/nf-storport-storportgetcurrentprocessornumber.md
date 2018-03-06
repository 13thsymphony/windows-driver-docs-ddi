---
UID: NF:storport.StorPortGetCurrentProcessorNumber
title: StorPortGetCurrentProcessorNumber function
author: windows-driver-content
description: The StorPortGetCurrentProcessorNumber routine retrieves the current processor number from the kernel.
old-location: storage\storportgetcurrentprocessornumber.htm
old-project: storage
ms.assetid: 10d77823-fcaa-43c3-b55e-74f2da97ecf0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortGetCurrentProcessorNumber, StorPortGetCurrentProcessorNumber routine [Storage Devices], storage.storportgetcurrentprocessornumber, storport/StorPortGetCurrentProcessorNumber, storprt_ac4d7e8b-eeb7-4b10-9c9e-cfe9acfddb24.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetCurrentProcessorNumber
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetCurrentProcessorNumber function
The <b>StorPortGetCurrentProcessorNumber</b> routine retrieves the current processor number from the kernel.

## Syntax

````
ULONG StorPortGetCurrentProcessorNumber(
  _In_  PVOID             HwDeviceExtension,
  _Out_ PPROCESSOR_NUMBER ProcNumber
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`ProcNumber`

A pointer to a processor number structure that holds the return data.


## Return Value

The <b>StorPortGetCurrentProcessorNumber</b> routine returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>ProcNumber</i> is set to <b>NULL</b>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | StorPortIrql |