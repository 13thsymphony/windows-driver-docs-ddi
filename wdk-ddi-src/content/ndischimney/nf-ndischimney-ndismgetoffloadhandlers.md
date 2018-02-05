---
UID : NF:ndischimney.NdisMGetOffloadHandlers
title : NdisMGetOffloadHandlers function
author : windows-driver-content
description : This function obtains the entry points of the NDIS functions for a particular chimney type.
old-location : netvista\ndismgetoffloadhandlers.htm
old-project : netvista
ms.assetid : a78acf5d-07ec-487c-97bd-daca8d08863c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisMGetOffloadHandlers, ndischimney/NdisMGetOffloadHandlers, NdisMGetOffloadHandlers function [Network Drivers Starting with Windows Vista], tcp_chim_ndis_func_6cfee4fb-432c-4f03-b28d-947dbc95ae48.xml, netvista.ndismgetoffloadhandlers
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Universal
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# NdisMGetOffloadHandlers function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

This function obtains the entry points of the NDIS functions for a particular chimney type.

## Syntax

````
NDIS_STATUS NdisMGetOffloadHandlers(
  _In_  NDIS_HANDLE                  NdisMiniportHandle,
  _In_  NDIS_CHIMNEY_OFFLOAD_TYPE    ChimneyType,
  _Out_ PNDIS_OFFLOAD_EVENT_HANDLERS *OffloadHandlers
);
````

## Parameters

`NdisMiniportHandle`

The handle to a context area that is offload target-allocated in which the offload target
     maintains state information about this instance of the adapter. The offload target provided this handle
     to NDIS when calling 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

`ChimneyType`

A chimney type that is one of the following NDIS_CHIMNEY_OFFLOAD_TYPE values:
     



All other NDIS_CHIMNEY_OFFLOAD_TYPE values are currently reserved.


#### NdisTcpChimneyOffload

The TCP chimney offload type.

`OffloadHandlers`

A pointer to a variable supplied by the offload target. The size of this variable is 
     sizeof(PNDIS_OFFLOAD_EVENT_HANDLERS). If the call to the 
     <b>NdisMGetOffloadHandlers</b> function succeeds, the function returns, in this variable, a pointer to an
     NDIS_OFFLOAD_EVENT_HANDLERS structure. This structure serves as a header for the chimney-specific
     structure that contains the entry points. The NDIS_OFFLOAD_EVENT_HANDLERS structure is formatted as
     follows:
     
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NDIS_OFFLOAD_EVENT_HANDLERS {
  NDIS_OBJECT_HEADER  Header;
} NDIS_OFFLOAD_EVENT_HANDLERS, *PNDIS_OFFLOAD_EVENT_HANDLERS;</pre>
</td>
</tr>
</table></span></div>This structure contains the following member:




#### Header

Specifies an NDIS object header, which is formatted as an 
       <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


## Return Value

<b>NdisMGetOffloadHandlers</b> can return either of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call succeeded. The returned NDIS entry points are valid for the specified chimney
       type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
NDIS does not support the chimney type specified by the offload target. In this case, NDIS does
       not return a valid 
       <i>OffloadHandlers</i> pointer.

</td>
</tr>
</table>

## Remarks

The offload target calls this function from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function to
    get the entry points of the NDIS functions for a particular chimney type. The offload target calls 
    <b>NdisMGetOffloadHandlers</b> once for each chimney type that it supports. In each call, the offload
    target specifies a different chimney type.

If the call to the 
    <b>NdisMGetOffloadHandlers</b> function succeeds, NDIS supplies a valid 
    <i>OffloadHandlers</i> pointer, which points to an NDIS_OFFLOAD_EVENT_HANDLERS structure. This structure
    contains an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The offload
    target examines the 
    <b>Type</b>, 
    <b>Revision</b>, and 
    <b>Size</b> members of the NDIS_OBJECT_HEADER structure. These members specify the structure that contains
    the chimney-specific entry points, the revision number of this structure, and the size of this structure
    in bytes. The 
    <b>Type</b> value is the same value that the offload target supplied for the 
    <i>ChimneyType</i> parameter.

If the offload target supports the specified 
    <b>Revision</b> number, it casts the 
    <i>OffloadHandlers</i> pointer to a pointer to the appropriate chimney-specific structure type. The
    following table indicates the chimney-specific structure for each chimney type.
<table>
<tr>
<th><i>ChimneyType</i></th>
<th>Chimney-specific handlers structure</th>
</tr>
<tr>
<td>
<b>NdisTcpChimneyOffload</b>

</td>
<td>

<a href="..\ndischimney\ns-ndischimney-_ndis_tcp_offload_event_handlers.md">
        NDIS_TCP_OFFLOAD_EVENT_HANDLERS</a>


</td>
</tr>
</table> 

For example, for the 
    <b>NdisTcpChimneyOffload</b> chimney type, the offload target casts the 
    <i>OffloadHandlers</i> pointer to *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS.

The chimney-specific handlers structure contains the same NDIS_OBJECT_HEADER structure as the
    NDIS_OFFLOAD_EVENT_HANDLERS structure.

The offload target copies the entry points from the chimney-specific structure into its own internal
    data structure and then returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndischimney\ns-ndischimney-_ndis_tcp_offload_event_handlers.md">
   NDIS_TCP_OFFLOAD_EVENT_HANDLERS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMGetOffloadHandlers function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>