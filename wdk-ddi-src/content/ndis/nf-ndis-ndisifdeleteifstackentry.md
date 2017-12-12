---
UID: NF.ndis.NdisIfDeleteIfStackEntry
title: NdisIfDeleteIfStackEntry function
author: windows-driver-content
description: The NdisIfDeleteIfStackEntry function deletes information about the ordering of two network interfaces in the NDIS interface stack.
old-location: netvista\ndisifdeleteifstackentry.htm
old-project: netvista
ms.assetid: 02b4a485-d44b-458c-89f5-1807500b6db8
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisIfDeleteIfStackEntry
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
req.alt-api: NdisIfDeleteIfStackEntry
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Interfaces_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisIfDeleteIfStackEntry function



## -description
The 
  <b>NdisIfDeleteIfStackEntry</b> function deletes information about the ordering of two network interfaces in
  the NDIS interface stack.



## -syntax

````
VOID NdisIfDeleteIfStackEntry(
  _In_ NET_IFINDEX HigherLayerIfIndex,
  _In_ NET_IFINDEX LowerLayerIfIndex
);
````


## -parameters

### -param HigherLayerIfIndex [in]

The network interface index for the interface that was higher in the stack table.


### -param LowerLayerIfIndex [in]

The network interface index for the interface that was lower in the stack table.


## -returns
None


## -remarks
NDIS drivers call 
    <b>NdisIfDeleteIfStackEntry</b> to delete a stack entry that was previously added by calling the 
    <a href="netvista.ndisifaddifstackentry">NdisIfAddIfStackEntry</a> function. NDIS
    deletes the stack entry from its interface stack table if it finds a matching entry.

NDIS maintains an interface stack table (<i>ifStackTable</i> from 
    <a href="netvista.overview_of_ndis_network_interfaces">RFC 2863</a>). NDIS provides
    the 
    <b>NdisIfAddIfStackEntry</b> and 
    <b>NdisIfDeleteIfStackEntry</b> functions to add and delete entries in this table.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_interfaces_function">Irql_Interfaces_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisifaddifstackentry">NdisIfAddIfStackEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfDeleteIfStackEntry function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

