---
UID: NF:ndis.NdisGetDataBuffer
title: NdisGetDataBuffer function
author: windows-driver-content
description: Call the NdisGetDataBuffer function to gain access to a contiguous block of data from a NET_BUFFER structure.
old-location: netvista\ndisgetdatabuffer.htm
old-project: netvista
ms.assetid: 784d4c32-a517-4219-8e22-a998e0e66d69
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisGetDataBuffer, NdisGetDataBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisGetDataBuffer, ndis_netbuf_functions_ref_b4ffded6-13c9-417d-bb03-a6421f718deb.xml, netvista.ndisgetdatabuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetDataBuffer
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetDataBuffer function
Call the 
  <b>NdisGetDataBuffer</b> function to gain access to a contiguous block of data from a 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.

## Syntax

````
PVOID NdisGetDataBuffer(
  _In_     PNET_BUFFER NetBuffer,
  _In_     ULONG       BytesNeeded,
  _In_opt_ PVOID       Storage,
  _In_     UINT        AlignMultiple,
  _In_     UINT        AlignOffset
);
````

## Parameters

`NetBuffer`

A pointer to a NET_BUFFER structure.

`BytesNeeded`

The number of contiguous bytes of data requested.

`Storage`

A pointer to a buffer, or <b>NULL</b> if no buffer is provided by the caller. The buffer must be greater
     than or equal in size to the number of bytes specified in 
     <i>BytesNeeded</i> . If this value is non-<b>NULL</b>, and the data requested is not contiguous, NDIS copies the
     requested data to the area indicated by 
     <i>Storage</i> .

`AlignMultiple`

The alignment multiple expressed in power of two. For example, 2, 4, 8, 16, and so forth. If 
     <i>AlignMultiple</i> is 1, then there is no alignment requirement.

`AlignOffset`

The offset, in bytes, from the alignment multiple.


## Return Value

<b>NdisGetDataBuffer</b> returns a pointer to the start of the contiguous data or it returns <b>NULL</b>.

If the 
      <b>DataLength</b> member of the 
      <a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a> structure in the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that the <i>NetBuffer</i>
      parameter points to is less than the value in the 
      <i>BytesNeeded</i> parameter, the return value is <b>NULL</b>.

If the requested data in the buffer is contiguous, the return value is a pointer to a location that
      NDIS provides. If the data is not contiguous, NDIS uses the 
      <i>Storage</i> parameter as follows:

<ul>
<li>If the 
       <i>Storage</i> parameter is non-<b>NULL</b>, NDIS copies the data to the buffer at 
       <i>Storage</i>. The return value is the pointer passed to the 
       <i>Storage</i> parameter.</li>
<li>If the 
       <i>Storage</i> parameter is <b>NULL</b>, the return value is <b>NULL</b>.</li>
</ul>
The return value can also be <b>NULL</b> due to a low resource condition where a data buffer cannot be mapped. This may occur even if the data is contiguous or the <i>Storage</i> parameter is non-<b>NULL</b>.

## Remarks

Call this function to get a pointer to a network data header contained in the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure. You can easily parse the
    header stored in the contiguous data block that this function returns.

The requested alignment requirement is expressed as a power-of-two multiple plus an offset. For
    example, if 
    <i>AlignMultiple</i> is 4 and 
    <i>AlignOffset</i> is 3 then the data address should be a multiple of 4 plus 3. If necessary, NDIS will
    allocate memory to satisfy the alignment requirement.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_data.md">NET_BUFFER_DATA</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetDataBuffer function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>