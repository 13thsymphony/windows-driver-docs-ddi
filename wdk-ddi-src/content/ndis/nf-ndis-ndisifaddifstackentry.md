---
UID: NF:ndis.NdisIfAddIfStackEntry
title: NdisIfAddIfStackEntry function
author: windows-driver-content
description: The NdisIfAddIfStackEntry function specifies the ordering of two network interfaces in the NDIS network interface stack.
old-location: netvista\ndisifaddifstackentry.htm
old-project: netvista
ms.assetid: 6927bcdf-e2b5-4a60-8f71-a977f3a1c120
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisIfAddIfStackEntry, NdisIfAddIfStackEntry function [Network Drivers Starting with Windows Vista], ndis/NdisIfAddIfStackEntry, net_if_functions_ref_3e652431-fb28-4382-957a-3c532951e847.xml, netvista.ndisifaddifstackentry
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIfAddIfStackEntry
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisIfAddIfStackEntry function
The 
  <b>NdisIfAddIfStackEntry</b> function specifies the ordering of two network interfaces in the NDIS network
  interface stack.

## Syntax

```
NDIS_STATUS NdisIfAddIfStackEntry(
  NET_IFINDEX HigherLayerIfIndex,
  NET_IFINDEX LowerLayerIfIndex
);
```

## Parameters

`HigherLayerIfIndex`

The network interface index for the interface that should be higher in the interface stack
     table.

`LowerLayerIfIndex`

The network interface index for the interface that should be lower in the interface stack
     table.


## Return Value

<b>NdisIfAddIfStackEntry</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisIfAddIfStackEntry</b> failed because the index at 
       <i>HigherLayerIfIndex</i> or 
       <i>LowerLayerIfIndex</i> is not the index of a registered interface.

</td>
</tr>
</table>

## Remarks

NDIS drivers can call the 
    <b>NdisIfAddIfStackEntry</b> function to specify the ordering of two network interfaces in the NDIS
    interface stack. The NDIS proxy provider specifies the order for filter modules and miniport adapters.
    NDIS also specifies the relationship between the virtual miniport and the underlying miniport adapter for
    filter intermediate drivers. However, NDIS does not specify the stack order for MUX intermediate
    drivers.

NDIS maintains an interface stack table (<i>ifStackTable</i> from 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/overview-of-ndis-network-interfaces">RFC 2863</a>). NDIS provides
    the 
    <b>NdisIfAddIfStackEntry</b> and 
    <a href="https://msdn.microsoft.com/02b4a485-d44b-458c-89f5-1807500b6db8">
    NdisIfDeleteIfStackEntry</a> functions to add and delete entries in this table.

Any driver that can provide the information about the stack order relationship between two interfaces
    should call 
    <b>NdisIfAddIfStackEntry</b> to populate the interface stack table. NDIS deletes the corresponding stack
    entries for an interface when the interface is deregistered.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Interfaces_Function |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562698">NdisIfDeleteIfStackEntry</a>