---
UID: NF:ndis.NdisMaxGroupCount
title: NdisMaxGroupCount function
author: windows-driver-content
description: The NdisMaxGroupCount function returns the maximum number of processor groups in the local computer system.
old-location: netvista\ndismaxgroupcount.htm
old-project: netvista
ms.assetid: 080707c5-cf46-4066-a241-684cdae37fee
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMaxGroupCount, NdisMaxGroupCount function [Network Drivers Starting with Windows Vista], ndis/NdisMaxGroupCount, ndis_processor_group_ref_5744be61-71b7-4abc-ad66-30b26558c0ac.xml, netvista.ndismaxgroupcount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMaxGroupCount
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMaxGroupCount function
The
  <b>NdisMaxGroupCount</b> function returns the maximum number of processor groups in the local computer
  system.

## Syntax

````
USHORT NdisMaxGroupCount(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.

## Remarks

NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.

To obtain the number of groups that are currently active, call the 
    <a href="..\ndis\nf-ndis-ndisactivegroupcount.md">NdisActiveGroupCount</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisactivegroupcount.md">NdisActiveGroupCount</a>