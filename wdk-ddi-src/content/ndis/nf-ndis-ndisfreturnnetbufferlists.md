---
UID : NF:ndis.NdisFReturnNetBufferLists
title : NdisFReturnNetBufferLists function
author : windows-driver-content
description : Filter drivers call NdisFReturnNetBufferLists to release the ownership of one or more NET_BUFFER_LIST structures and their associated NET_BUFFER structures.
old-location : netvista\ndisfreturnnetbufferlists.htm
old-project : netvista
ms.assetid : 083cf25d-7436-4c4e-b29a-c9a2702b136d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisFReturnNetBufferLists, ndis/NdisFReturnNetBufferLists, filter_ndis_functions_ref_3473c0c3-077c-4df7-b9d4-8392cf1ed918.xml, netvista.ndisfreturnnetbufferlists, NdisFReturnNetBufferLists function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Filter_Driver_Function
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
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFReturnNetBufferLists function
Filter drivers call
  <b>NdisFReturnNetBufferLists</b> to release the ownership of one or more 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures and their
  associated 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures.

## Syntax

````
VOID NdisFReturnNetBufferLists(
  _In_ NDIS_HANDLE      NdisFilterHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            ReturnFlags
);
````

## Parameters

`NdisFilterHandle`

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

`NetBufferLists`

A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <mshelp:link keywords="netvista.filterreceivenetbufferlists" tabindex="0"><i>
     FilterReceiveNetBufferLists</i></mshelp:link> function.

`ReturnFlags`

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero.This function supports the following flags:


## Return Value

None

## Remarks

If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <mshelp:link keywords="netvista.filterreceivenetbufferlists" tabindex="0"><i>
    FilterReceiveNetBufferLists</i></mshelp:link> function was not set, the filter driver must call the 
    <b>NdisFReturnNetBufferLists</b> function to return the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures and associated
    data. After the filter driver calls 
    <b>NdisFReturnNetBufferLists</b>, NDIS returns the data to the underlying driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Filter_Driver_Function |

## See Also

<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFReturnNetBufferLists function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>