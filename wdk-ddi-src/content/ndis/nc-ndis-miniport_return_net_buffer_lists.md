---
UID: NC.ndis.MINIPORT_RETURN_NET_BUFFER_LISTS
title: MINIPORT_RETURN_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls the MiniportReturnNetBufferLists function to return ownership of NET_BUFFER_LIST structures, associated NET_BUFFER structures, and any attached MDLs to a miniport driver.
old-location: netvista\miniportreturnnetbufferlists.htm
old-project: netvista
ms.assetid: 0f33ae87-164e-40dc-a915-28211a0d74b7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportReturnNetBufferLists
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# MINIPORT_RETURN_NET_BUFFER_LISTS callback



## -description
NDIS calls the 
   <i>MiniportReturnNetBufferLists</i> function to return ownership of 
   <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures, associated 
   <a href="netvista.net_buffer">NET_BUFFER</a> structures, and any attached MDLs to a
   miniport driver.


## -prototype

````
MINIPORT_RETURN_NET_BUFFER_LISTS MiniportReturnNetBufferLists;

VOID MiniportReturnNetBufferLists(
  _In_ NDIS_HANDLE      MiniportAdapterContext,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            ReturnFlags
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information about an adapter.

### -param NetBufferLists [in]

A pointer to a linked list of 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that NDIS is
     returning to the miniport driver. The linked list can contain NET_BUFFER_LIST structures from multiple
     previous calls to the 
     <a href="netvista.ndismindicatereceivenetbufferlists">
     NdisMIndicateReceiveNetBufferLists</a> function.

### -param ReturnFlags [in]

NDIS flags that can be combined with an OR operation. This function supports the NDIS_RETURN_FLAGS_DISPATCH_LEVEL flag which, if set, indicates that the
     current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.

## -returns
None

## -remarks
<i>MiniportReturnNetBufferLists</i> is a required function for miniport drivers that indicate received
    network data with the 
    <a href="netvista.ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function. When an overlying driver calls the 
    <a href="netvista.ndisreturnnetbufferlists">
    NdisReturnNetBufferLists</a> function, NDIS calls the 
    <i>MiniportReturnNetBufferLists</i> function of the miniport driver that indicated the specified 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures.

<i>MiniportReturnNetBufferLists</i> can prepare a returned NET_BUFFER_LIST structure for use in a
    subsequent receive indication. Although 
    <i>MiniportReturnNetBufferLists</i> can return the NET_BUFFER_LIST structures to a pool (for example, it
    could call the 
    <a href="netvista.ndisfreenetbufferlist">NdisFreeNetBufferList</a> function), it
    can be more efficient to reuse the structures without returning them to the pool.

NDIS calls 
    <i>MiniportReturnNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.

To define a <i>MiniportReturnNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportReturnNetBufferLists</i> function that is named "MyReturnNetBufferLists", use the <b>MINIPORT_RETURN_NET_BUFFER_LISTS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_RETURN_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_RETURN_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndisfreenetbufferlist">NdisFreeNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndisreturnnetbufferlists">NdisReturnNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_RETURN_NET_BUFFER_LISTS callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
