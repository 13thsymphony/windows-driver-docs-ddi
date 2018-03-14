---
UID: NF:storport.StorPortGetHighestNodeNumber
title: StorPortGetHighestNodeNumber function
author: windows-driver-content
description: The StorPortGetHighestNodeNumber routine returns the largest possible node number on the system.
old-location: storage\storportgethighestnodenumber.htm
old-project: storage
ms.assetid: 3e0b85f9-b6e4-4d53-b8dc-7f51e0f74be3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortGetHighestNodeNumber, StorPortGetHighestNodeNumber routine [Storage Devices], storage.storportgethighestnodenumber, storport/StorPortGetHighestNodeNumber, storprt_e9e942e1-6de3-4170-87ec-00660ce9925a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.lib: 
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
-	StorPortGetHighestNodeNumber
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetHighestNodeNumber function
The <b>StorPortGetHighestNodeNumber</b> routine returns the largest possible node number on the system.

## Syntax

````
ULONG StorPortGetHighestNodeNumber(
  _In_  PVOID  HwDeviceExtension,
  _Out_ PULONG HighestNode
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`HighestNode`

A pointer to a variable that holds the highest-numbered node.


## Return Value

The <b>StorPortGetHighestNodeNumber</b>routine returns one of the following status codes:

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
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>HighestNode</i> is set to <b>NULL</b>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | StorPortIrql |