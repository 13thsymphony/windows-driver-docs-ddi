---
UID : NF:ndis.NdisZeroMappedMemory
title : NdisZeroMappedMemory function
author : windows-driver-content
description : NdisZeroMappedMemory fills a block of memory that was mapped with a preceding call to NdisMMapIoSpace with zeros.
old-location : netvista\ndiszeromappedmemory.htm
old-project : netvista
ms.assetid : 210e20a5-c101-4005-97fb-e549ff97e7ce
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisZeroMappedMemory, NdisZeroMappedMemory, NdisZeroMappedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_mapped_ref_41b91ff3-a113-4a69-bb38-ec3ba89cc0d7.xml, netvista.ndiszeromappedmemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisZeroMappedMemory (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisZeroMappedMemory (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisZeroMappedMemory function
<b>NdisZeroMappedMemory</b> fills a block of memory that was mapped with a preceding call to 
  <b>NdisMMapIoSpace</b> with zeros.

## Syntax

````
VOID NdisZeroMappedMemory(
  _In_ PVOID Destination,
  _In_ ULONG Length
);
````

## Parameters

`Destination`

Specifies the base virtual address of a block of mapped memory.

`Length`

Specifies the number of bytes to be filled with zeros.


## Return Value

None

## Remarks

A miniport driver can call 
    <b>NdisZeroMappedMemory</b> to zero-initialize mapped device memory. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of the range specified when the driver called 
    <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.

<b>NdisZeroMappedMemory</b> is optimized, and a miniport driver can call this function any time that it
    needs to clear a mapped memory range.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndiszeromemory.md">NdisZeroMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisZeroMappedMemory function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>