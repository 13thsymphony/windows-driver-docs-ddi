---
UID: NF:storport.StorPortUpdateAdapterMaxIO
title: StorPortUpdateAdapterMaxIO function
author: windows-driver-content
description: This function can be called by a miniport to update the maximum IO's supported by an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine callback and has effect only during adapter initialization.
old-location: storage\storportupdateadaptermaxio.htm
old-project: storage
ms.assetid: BB18925D-ACFA-426D-ADD3-33C1D8A99396
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortUpdateAdapterMaxIO, StorPortUpdateAdapterMaxIO function [Storage Devices], storage.storportupdateadaptermaxio, storport/StorPortUpdateAdapterMaxIO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	StorPortUpdateAdapterMaxIO
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortUpdateAdapterMaxIO function
This function can be called by a miniport to update the maximum IO's supported by
    an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine
    callback and has effect only during adapter initialization.

## Syntax

````
ULONG StorPortUpdateAdapterMaxIO(
   PVOID HwDeviceExtension,
   ULONG MaxIoCount
);
````

## Parameters

`HwDeviceExtension`

A pointer to miniport's device extension.

`MaxIoCount`

Maximum IO's supported by the adapter.


## Return Value

This function returns of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>STOR_STATUS_SUCCESS</td>
<td>The telemetry event was successfully logged.</td>
</tr>
<tr>
<td>STOR_STATUS_NOT_IMPLEMENTED</td>
<td>The function is called on the OS that does not support it.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_PARAMETER</td>
<td>There is an invalid parameter.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_DEVICE_REQUEST</td>
<td>The function was called outside of <b>HwInitialize</b>/<b>HwPassiveInitRoutine</b>. </td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10, version 1709.  |
| **Target Platform** | Windows |
| **Header** | storport.h |

## See Also

<a href="..\strmini\ns-strmini-_hw_initialization_data.md">HwInitialize</a>