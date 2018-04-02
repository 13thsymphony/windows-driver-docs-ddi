---
UID: NC:ndis.NDIS_PROCESS_SG_LIST
title: NDIS_PROCESS_SG_LIST
author: windows-driver-content
description: The NetProcessSGList function (NDIS_PROCESS_SG_LIST_HANDLER entry point) processes a scatter/gather list.
old-location: netvista\netprocesssglist.htm
old-project: netvista
ms.assetid: 5b99e0ec-7c82-46d6-b32a-246b368cf4f1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_PROCESS_SG_LIST, NetProcessSGList, NetProcessSGList callback function [Network Drivers Starting with Windows Vista], ndis/NetProcessSGList, ndis_shared_memory_ref_0c3e2851-6897-4997-a974-2a108e1e5ee9.xml, netvista.netprocesssglist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NetProcessSGList
product:
- Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NDIS_PROCESS_SG_LIST callback function
The 
  <i>NetProcessSGList</i> function (NDIS_PROCESS_SG_LIST_HANDLER entry point) processes a scatter/gather
  list.

## Syntax

```
NDIS_PROCESS_SG_LIST NdisProcessSgList;

void NdisProcessSgList(
  PDEVICE_OBJECT DeviceObject,
  PVOID Reserved,
  PSCATTER_GATHER_LIST ScatterGatherListBuffer,
  PVOID Context
)
{...}
```

## Parameters

`DeviceObject`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure.

`Reserved`

Reserved for NDIS.

`ScatterGatherListBuffer`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure.

`Context`

A pointer to a block of driver-allocated context information that contains information about the
     scatter gather list. The driver provided this context information in the 
     <b>Context</b> member of the 
     <a href="https://msdn.microsoft.com/5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36">
     NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure.


## Return Value

None

## Remarks

NDIS calls the 
    <i>NetProcessSGList</i> function that is specified at the 
    <b>ProcessSGListHandler</b> member of the 
    <a href="https://msdn.microsoft.com/5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure within the context of the 
    <a href="https://msdn.microsoft.com/439d68ec-9d27-484b-b6a3-9bae732d142e">
    NdisBuildScatterGatherList</a> function.

The driver specified the entry point (NDIS_PROCESS_SG_LIST_HANDLER) for 
    <i>NetProcessSGList</i> in the NDIS_SCATTER_GATHER_LIST_PARAMETERS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561620">NdisBuildScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a>