---
UID : NF:ndis.NdisFreeIoWorkItem
title : NdisFreeIoWorkItem function
author : windows-driver-content
description : NDIS drivers call the NdisFreeIoWorkItem function to free a specified work item.
old-location : netvista\ndisfreeioworkitem.htm
old-project : netvista
ms.assetid : ddc2f96b-fa2c-43c1-960f-7f8e06a5b22d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisFreeIoWorkItem, netvista.ndisfreeioworkitem, NdisFreeIoWorkItem, ndis_work_items_ref_50b3859f-f34b-4cae-b7ef-935f1aae82cb.xml, NdisFreeIoWorkItem function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Init_NdisAllocateIoWorkItem, Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeIoWorkItem function
NDIS drivers call the
  <b>NdisFreeIoWorkItem</b> function to free a specified work item.

## Syntax

````
VOID NdisFreeIoWorkItem(
  _In_ NDIS_HANDLE NdisIoWorkItemHandle
);
````

## Parameters

`NdisIoWorkItemHandle`

A handle to a private <b>NDIS_IO_WORKITEM</b> structure that was returned by a previous call to the 
     <mshelp:link keywords="netvista.ndisallocateioworkitem" tabindex="0"><b>
     NdisAllocateIoWorkItem</b></mshelp:link> function.


## Return Value

None

## Remarks

<b>NdisFreeIoWorkItem</b> calls 
    <a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a> to free the structure that is
    specified by the
    <i>NdisIoWorkItemHandle</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Init_NdisAllocateIoWorkItem, Irql_Miscellaneous_Function |

## See Also

<a href="https://msdn.microsoft.com/4f966ff3-2092-495f-863f-50f079085fa6">NDIS I/O Work Items</a>

<a href="..\ndis\nf-ndis-ndisallocateioworkitem.md">NdisAllocateIoWorkItem</a>

<a href="..\ndis\nf-ndis-ndisqueueioworkitem.md">NdisQueueIoWorkItem</a>

<a href="..\wdm\nf-wdm-iofreeworkitem.md">IoFreeWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeIoWorkItem function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>