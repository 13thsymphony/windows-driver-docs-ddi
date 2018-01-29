---
UID : NF:ndis.NdisCoSendNetBufferLists
title : NdisCoSendNetBufferLists function
author : windows-driver-content
description : The NdisCoSendNetBufferLists function sends network data that is contained in a specified list of NET_BUFFER_LIST structures.
old-location : netvista\ndiscosendnetbufferlists.htm
old-project : netvista
ms.assetid : 8284fdd4-26de-4622-b164-f33aee1d8742
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisCoSendNetBufferLists, NdisCoSendNetBufferLists, condis_sendrcv_ref_6d1dfac7-b538-402c-ae8b-04f74bd188e9.xml, NdisCoSendNetBufferLists function [Network Drivers Starting with Windows Vista], netvista.ndiscosendnetbufferlists
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 drivers in Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Connection_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisCoSendNetBufferLists function
The 
  <b>NdisCoSendNetBufferLists</b> function sends network data that is contained in a specified list of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures.

## Syntax

````
VOID NdisCoSendNetBufferLists(
  _In_ NDIS_HANDLE      NdisVcHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendFlags
);
````

## Parameters

`NdisVcHandle`

A handle to a virtual connection (VC) that identifies the target of the send request.

`NetBufferLists`

A pointer to a linked list of 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures. Each
     NET_BUFFER_LIST structure describes a list of 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures.

`SendFlags`

Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <b>NdisCoSendNetBufferLists</b> supports the following flags:


## Return Value

None

## Remarks

After a CoNDIS protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, NDIS submits the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that the 
    <i>NetBufferLists</i> parameter specifies to an underlying driver's 
    <mshelp:link keywords="netvista.miniportcosendnetbufferlists" tabindex="0"><i>
    MiniportCoSendNetBufferLists</i></mshelp:link> function.

The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:
<ul>
<li>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a>


</li>
<li>

<mshelp:link keywords="netvista.ndisallocatenetbufferandnetbufferlist" tabindex="0"><b>
       NdisAllocateNetBufferAndNetBufferList</b></mshelp:link>


</li>
<li>

<mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
       NdisAllocateCloneNetBufferList</b></mshelp:link>


</li>
</ul>The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. Alternatively, the protocol
    driver can allocate the structures immediately prior to calling 
    <b>NdisCoSendNetBufferLists</b> and then can free them when the send operation is complete. When NDIS
    returns a NET_BUFFER_LIST structure to the 
    <mshelp:link keywords="netvista.protocolcosendnetbufferlistscomplete" tabindex="0"><i>
    ProtocolCoSendNetBufferListsComplete</i></mshelp:link> function, the protocol driver can prepare the NET_BUFFER_LIST
    structure and any associated resources for reuse. If you reuse the NET_BUFFER_LIST structures, you can
    get better performance than returning the structures to a pool and then reallocating them for another
    send operation.

A protocol driver must set the 
    <b>SourceHandle</b> member of each 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure to the same value
    that it passes at the 
    <i>NdisVcHandle</i> parameter. The source handle provides the information that NDIS requires to return the
    NET_BUFFER_LIST structure to the protocol driver after the underlying miniport driver calls the 
    <mshelp:link keywords="netvista.ndismcosendnetbufferlistscomplete" tabindex="0"><b>
    NdisMCoSendNetBufferListsComplete</b></mshelp:link> function.

Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, the driver can set information that accompanies the send request with
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.

Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent.

As soon as a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, it no longer owns the NET_BUFFER_LIST structures and all of the
    associated resources. NDIS calls the 
    <i>ProtocolCoSendNetBufferListsComplete</i> function to return the structures and data to the protocol
    driver. NDIS can collect the structures and data from multiple send requests into a single linked list of
    NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.

Until NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i>, the current status of a protocol driver-initiated send is
    not available to the protocol driver. A protocol driver temporarily releases ownership of all of the
    resources that it allocated for a send request when it calls 
    <b>NdisCoSendNetBufferLists</b>. A protocol driver should never attempt to examine the NET_BUFFER_LIST
    structures or any associated data after the driver calls 
    <b>NdisCoSendNetBufferLists</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Connection_Function |

## See Also

<mshelp:link keywords="netvista.ndismcosendnetbufferlistscomplete" tabindex="0"><b>
   NdisMCoSendNetBufferListsComplete</b></mshelp:link>

<mshelp:link keywords="netvista.ndisallocatenetbufferandnetbufferlist" tabindex="0"><b>
   NdisAllocateNetBufferAndNetBufferList</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<mshelp:link keywords="netvista.protocolcosendnetbufferlistscomplete" tabindex="0"><i>
   ProtocolCoSendNetBufferListsComplete</i></mshelp:link>

<mshelp:link keywords="netvista.ndisallocateclonenetbufferlist" tabindex="0"><b>
   NdisAllocateCloneNetBufferList</b></mshelp:link>

<mshelp:link keywords="netvista.miniportcosendnetbufferlists" tabindex="0"><i>
   MiniportCoSendNetBufferLists</i></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoSendNetBufferLists function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>