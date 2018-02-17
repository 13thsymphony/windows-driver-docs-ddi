---
UID: NF:ndis.NdisFCancelSendNetBufferLists
title: NdisFCancelSendNetBufferLists function
author: windows-driver-content
description: Filter drivers call the NdisFCancelSendNetBufferLists function to cancel the transmission of network data.
old-location: netvista\ndisfcancelsendnetbufferlists.htm
old-project: netvista
ms.assetid: 358b1aa9-4bfd-4bed-94f7-1b021c732a02
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisFCancelSendNetBufferLists function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_272bc8c3-bf88-42d8-b415-429100169d47.xml, netvista.ndisfcancelsendnetbufferlists, ndis/NdisFCancelSendNetBufferLists, NdisFCancelSendNetBufferLists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFCancelSendNetBufferLists
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFCancelSendNetBufferLists function
Filter drivers call the 
  <b>NdisFCancelSendNetBufferLists</b> function to cancel the transmission of network data.

## Syntax

````
VOID NdisFCancelSendNetBufferLists(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ PVOID       CancelId
);
````

## Parameters

`NdisFilterHandle`

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`CancelId`

The cancellation identifier. This identifier specifies the network data for the transmission that
     is being canceled.


## Return Value

None

## Remarks

A filter driver can cancel the send requests that it originates or pass on the cancellation requests
    from overlying drivers. To cancel a send request from an overlying driver, NDIS calls the filter drivers 
    <a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
    FilterCancelSendNetBufferLists</a> function.

A filter driver can call the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro to mark NET_BUFFER_LIST structures that it originates and
    passes down to lower-level drivers for transmission. The NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro marks
    the specified packet with a cancellation identifier.

<b>NdisFCancelSendNetBufferLists</b> cancels the transmission of all data that is marked with the
    specified cancellation identifier.

NDIS returns canceled send data that the filter driver originated to the 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
    FilterSendNetBufferListsComplete</a> function. The completion status of canceled requests is
    NDIS_STATUS_SEND_ABORTED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Filter_Driver_Function |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567299">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>



<a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
   FilterCancelSendNetBufferLists</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelSendNetBufferLists function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>