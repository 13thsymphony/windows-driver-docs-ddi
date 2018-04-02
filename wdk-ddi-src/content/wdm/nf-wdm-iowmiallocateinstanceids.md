---
UID: NF:wdm.IoWMIAllocateInstanceIds
title: IoWMIAllocateInstanceIds function
author: windows-driver-content
description: The IoWMIAllocateInstanceIds routine allocates one or more instance IDs that are unique to the GUID.
old-location: kernel\iowmiallocateinstanceids.htm
old-project: kernel
ms.assetid: c382689e-907c-473c-9ab1-da963d7f3ba3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoWMIAllocateInstanceIds, IoWMIAllocateInstanceIds routine [Kernel-Mode Driver Architecture], k104_52b2c9a6-e9c2-4c9f-b6f1-43ec8c72056a.xml, kernel.iowmiallocateinstanceids, wdm/IoWMIAllocateInstanceIds
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWMIAllocateInstanceIds
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoWMIAllocateInstanceIds function
The <b>IoWMIAllocateInstanceIds</b> routine allocates one or more instance IDs that are unique to the GUID.

## Syntax

```
NTKERNELAPI NTSTATUS IoWMIAllocateInstanceIds(
  LPCGUID Guid,
  ULONG   InstanceCount,
  ULONG   *FirstInstanceId
);
```

## Parameters

`Guid`

Pointer to the GUID for which to generate instance identifiers.

`InstanceCount`

Specifies how many instance identifiers should be provided.

`FirstInstanceId`

Pointer to the first instance identifier that the driver should use.


## Return Value

<b>IoWMIAllocateInstanceIds</b> returns a status code from the following list:

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
Indicates that WMI successfully provided unique instance identifiers for the GUID specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the WMI services are not available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that insufficient resources were available to provide the caller with instance IDs.

</td>
</tr>
</table>

## Remarks

If greater than one instance was requested in <i>InstanceCount</i> and the routine completed successfully, <i>FirstInstanceId</i> points to the first instance that the caller should use. For each instance requested beyond one, the caller should increment the value returned in *<i>FirstInstanceId</i>. For example, if the caller requested six instances and one was returned as the value of <i>FirstInstanceId</i>, the caller should use the values 1-6 as his unique instance identifiers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550505">IoWmiSuggestInstanceName</a>