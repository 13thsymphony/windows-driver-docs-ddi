---
UID : NF:storport.StorPortGetHighestNodeNumber
title : StorPortGetHighestNodeNumber function
author : windows-driver-content
description : The StorPortGetHighestNodeNumber routine returns the largest possible node number on the system.
old-location : storage\storportgethighestnodenumber.htm
old-project : storage
ms.assetid : 3e0b85f9-b6e4-4d53-b8dc-7f51e0f74be3
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortGetHighestNodeNumber
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
req.alt-api : StorPortGetHighestNodeNumber
req.alt-loc : storport.h
req.ddi-compliance : StorPortIrql
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
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
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The operation was successful.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>HighestNode</i> is set to <b>NULL</b>.


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