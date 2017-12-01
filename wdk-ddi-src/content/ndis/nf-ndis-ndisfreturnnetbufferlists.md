---
UID: NF.ndis.NdisFReturnNetBufferLists
title: NdisFReturnNetBufferLists
author: windows-driver-content
description: Filter drivers call NdisFReturnNetBufferLists to release the ownership of one or more NET_BUFFER_LIST structures and their associated NET_BUFFER structures.
old-location: netvista\ndisfreturnnetbufferlists.htm
old-project: netvista
ms.assetid: 083cf25d-7436-4c4e-b29a-c9a2702b136d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisFReturnNetBufferLists
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
req.alt-api: NdisFReturnNetBufferLists
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# NdisFReturnNetBufferLists function



## -description
<p>Filter drivers call
  <b>NdisFReturnNetBufferLists</b> to release the ownership of one or more 
  <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures and their
  associated 
  <a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a> structures.</p>


## -syntax

````
VOID NdisFReturnNetBufferLists(
  _In_ NDIS_HANDLE      NdisFilterHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            ReturnFlags
);
````


## -parameters
<dl>

### -param <i>NdisFilterHandle</i> [in]

<dd>
<p>The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter-attach.md">FilterAttach</a> function.</p>
</dd>

### -param <i>NetBufferLists</i> [in]

<dd>
<p>A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <a href="..\ndis\nc-ndis-filter-receive-net-buffer-lists.md">
     FilterReceiveNetBufferLists</a> function.</p>
</dd>

### -param <i>ReturnFlags</i> [in]

<dd>
<p>NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero.This function supports the following flags: </p>
<p></p>
<dl>

### -param <a id="NDIS_RETURN_FLAGS_DISPATCH_LEVEL"></a><a id="ndis_return_flags_dispatch_level"></a>NDIS_RETURN_FLAGS_DISPATCH_LEVEL

<dd>
<p>Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="NULL">Dispatch IRQL Tracking</a>.</p>
</dd>

### -param <a id="NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE"></a><a id="ndis_return_flags_switch_single_source"></a>NDIS_RETURN_FLAGS_SWITCH_SINGLE_SOURCE

<dd>
<p>If this flag is set, all packets in a linked list of <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.</p>
<p>For more information, see <a href="NULL">Hyper-V Extensible Switch Send and Receive Flags</a>.</p>
<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_RECEIVE_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>ReceiveFlags</i> parameter of <a href="..\ndis\nf-ndis-ndisfindicatereceivenetbufferlists.md">NdisFIndicateReceiveNetBufferLists</a>  when it sends the request.</div>
<div> </div>
</dd>
</dl>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <a href="..\ndis\nc-ndis-filter-receive-net-buffer-lists.md">
    FilterReceiveNetBufferLists</a> function was not set, the filter driver must call the 
    <b>NdisFReturnNetBufferLists</b> function to return the 
    <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structures and associated
    data. After the filter driver calls 
    <b>NdisFReturnNetBufferLists</b>, NDIS returns the data to the underlying driver.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_filter_driver_function">Irql_Filter_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter-attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter-receive-net-buffer-lists.md">FilterReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFReturnNetBufferLists function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
