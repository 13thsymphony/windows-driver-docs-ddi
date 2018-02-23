---
UID: NF:ndis.NdisGroupMaxProcessorCount
title: NdisGroupMaxProcessorCount function
author: windows-driver-content
description: The NdisGroupMaxProcessorCount function determines the maximum number of processors in a specified processor group.
old-location: netvista\ndisgroupmaxprocessorcount.htm
old-project: netvista
ms.assetid: 545a5014-aa07-49ee-92b7-2ae95f4ce785
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisGroupMaxProcessorCount, NdisGroupMaxProcessorCount function [Network Drivers Starting with Windows Vista], NdisGroupMaxProcessorCount, netvista.ndisgroupmaxprocessorcount, ndis_processor_group_ref_6bee6183-d82f-4512-a05d-134a95e898ae.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGroupMaxProcessorCount
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGroupMaxProcessorCount function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>