---
UID: NF:ndis.NdisIfAddIfStackEntry
title: NdisIfAddIfStackEntry function
author: windows-driver-content
description: The NdisIfAddIfStackEntry function specifies the ordering of two network interfaces in the NDIS network interface stack.
old-location: netvista\ndisifaddifstackentry.htm
old-project: netvista
ms.assetid: 6927bcdf-e2b5-4a60-8f71-a977f3a1c120
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisIfAddIfStackEntry
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
req.alt-api: NdisIfAddIfStackEntry
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
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisIfAddIfStackEntry function



## -description
The 
  <b>NdisIfAddIfStackEntry</b> function specifies the ordering of two network interfaces in the NDIS network
  interface stack.



## -syntax

````
NDIS_STATUS NdisIfAddIfStackEntry(
  _In_ NET_IFINDEX HigherLayerIfIndex,
  _In_ NET_IFINDEX LowerLayerIfIndex
);
````


## -parameters

### -param HigherLayerIfIndex [in]

The network interface index for the interface that should be higher in the interface stack
     table.


### -param LowerLayerIfIndex [in]

The network interface index for the interface that should be lower in the interface stack
     table.


## -returns
<b>NdisIfAddIfStackEntry</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The operation failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl><b>NdisIfAddIfStackEntry</b> failed because the index at 
       <i>HigherLayerIfIndex</i> or 
       <i>LowerLayerIfIndex</i> is not the index of a registered interface.

 


## -remarks
NDIS drivers can call the 
    <b>NdisIfAddIfStackEntry</b> function to specify the ordering of two network interfaces in the NDIS
    interface stack. The NDIS proxy provider specifies the order for filter modules and miniport adapters.
    NDIS also specifies the relationship between the virtual miniport and the underlying miniport adapter for
    filter intermediate drivers. However, NDIS does not specify the stack order for MUX intermediate
    drivers.

NDIS maintains an interface stack table (<i>ifStackTable</i> from 
    <a href="netvista.overview_of_ndis_network_interfaces">RFC 2863</a>). NDIS provides
    the 
    <b>NdisIfAddIfStackEntry</b> and 
    <a href="..\ndis\nf-ndis-ndisifdeleteifstackentry.md">
    NdisIfDeleteIfStackEntry</a> functions to add and delete entries in this table.

Any driver that can provide the information about the stack order relationship between two interfaces
    should call 
    <b>NdisIfAddIfStackEntry</b> to populate the interface stack table. NDIS deletes the corresponding stack
    entries for an interface when the interface is deregistered.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisifdeleteifstackentry.md">NdisIfDeleteIfStackEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfAddIfStackEntry function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

