---
UID : NF:storport.StorPortGetActiveGroupCount
title : StorPortGetActiveGroupCount function
author : windows-driver-content
description : The StorPortGetActiveGroupCount routine returns the number of processor groups that are present in the system.
old-location : storage\storportgetactivegroupcount.htm
old-project : storage
ms.assetid : 640dd836-a5f9-4a88-b2a3-038a66a50868
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storport/StorPortGetActiveGroupCount, storage.storportgetactivegroupcount, StorPortGetActiveGroupCount routine [Storage Devices], StorPortGetActiveGroupCount, storprt_d26e001f-a43e-4d7e-9278-9ba48a74574a.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : StorPortIrql
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortGetActiveGroupCount function
The <b>StorPortGetActiveGroupCount</b> routine returns the number of processor groups that are present in the system.

## Syntax

````
ULONG StorPortGetActiveGroupCount(
  _In_  PVOID   HwDeviceExtension,
  _Out_ PUSHORT NumberGroups
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`NumberGroups`

A pointer to a variable that holds the number of groups.


## Return Value

The <b>StorPortGetActiveGroupCount</b> routine returns one of the following status codes:
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
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | StorPortIrql |