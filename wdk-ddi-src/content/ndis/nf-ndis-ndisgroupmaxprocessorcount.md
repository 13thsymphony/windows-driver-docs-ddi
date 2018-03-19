---
UID: NF:ndis.NdisGroupMaxProcessorCount
title: NdisGroupMaxProcessorCount function
author: windows-driver-content
description: The NdisGroupMaxProcessorCount function determines the maximum number of processors in a specified processor group.
old-location: netvista\ndisgroupmaxprocessorcount.htm
old-project: netvista
ms.assetid: 545a5014-aa07-49ee-92b7-2ae95f4ce785
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisGroupMaxProcessorCount, NdisGroupMaxProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisGroupMaxProcessorCount, ndis_processor_group_ref_6bee6183-d82f-4512-a05d-134a95e898ae.xml, netvista.ndisgroupmaxprocessorcount
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
-	NdisGroupMaxProcessorCount
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGroupMaxProcessorCount function
The 
  <b>NdisGroupMaxProcessorCount</b> function determines the maximum number of processors in a specified
  processor group.

## Syntax

````
ULONG NdisGroupMaxProcessorCount(
   USHORT Group
);
````

## Parameters

`Group`

A USHORT value that identifies a processor group in the local computer system.


## Return Value

<b>NdisGroupMaxProcessorCount</b> returns a ULONG value for the maximum number of processors that are
      included in the group that is specified in the 
      <i>Group</i> parameter. The number of processors is a zero-based value.

If the 
      <i>Group</i> parameter is ALL_PROCESSOR_GROUPS, 
      <b>NdisGroupMaxProcessorCount</b> returns the maximum number of processors in the local computer.

## Remarks

An NDIS driver might call the 
    <b>NdisGroupMaxProcessorCount</b> function during initialization before it allocates resources.

<div class="alert"><b>Note</b>  NDIS 6.20 and later drivers should not use the 
    <a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a> function
    because it only returns the processor count for processor group 0.</div>
<div> </div>
The processor count can change at runtime on SKUs that support hot-add functionality for CPUs. To
    obtain an active processor count, call the 
    <a href="..\ndis\nf-ndis-ndisgroupactiveprocessorcount.md">
    NdisGroupActiveProcessorCount</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a>



<a href="..\ndis\nf-ndis-ndisgroupactiveprocessorcount.md">
   NdisGroupActiveProcessorCount</a>