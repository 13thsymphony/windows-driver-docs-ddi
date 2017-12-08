---
UID: NF.ndis.NdisIfQueryBindingIfIndex
title: NdisIfQueryBindingIfIndex function
author: windows-driver-content
description: The NdisIfQueryBindingIfIndex function retrieves the network interface indexes and NET_LUID values for the highest and lowest layered network interfaces that are associated with a specified protocol binding.
old-location: netvista\ndisifquerybindingifindex.htm
old-project: netvista
ms.assetid: 08f31584-b3ea-4e6e-b8ce-17813ca7c06b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisIfQueryBindingIfIndex
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
req.alt-api: NdisIfQueryBindingIfIndex
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

# NdisIfQueryBindingIfIndex function



## -description
The 
  <b>NdisIfQueryBindingIfIndex</b> function retrieves the network interface indexes and 
  <a href="netvista.net_luid">NET_LUID</a> values for the highest and lowest layered
  network interfaces that are associated with a specified protocol binding.


## -syntax

````
NDIS_STATUS NdisIfQueryBindingIfIndex(
  _In_  NDIS_HANDLE  NdisBindingHandle,
  _Out_ PNET_IFINDEX pBoundIfIndex,
  _Out_ PNET_LUID    pBoundIfNetLuid,
  _Out_ PNET_IFINDEX pLowestIfIndex,
  _Out_ PNET_LUID    pLowestIfNetLuid
);
````


## -parameters

### -param NdisBindingHandle [in]

A handle that identifies the binding for which NDIS should obtain the 
     <a href="netvista.net_luid">NET_LUID</a> values and network interface indexes.
     NDIS provided this handle at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param pBoundIfIndex [out]

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is highest in the driver
     stack.

### -param pBoundIfNetLuid [out]

A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is highest in the driver stack.

### -param pLowestIfIndex [out]

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is lowest in the driver
     stack.

### -param pLowestIfNetLuid [out]

A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is lowest in the driver stack.

## -returns
<b>NdisIfQueryBindingIfIndex</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl><b>NdisIfQueryBindingIfIndex</b> failed because the specified binding is not
       associated with a registered interface.

 

## -remarks
NDIS protocol drivers can call the 
    <b>NdisIfQueryBindingIfIndex</b> function to retrieve the network interface indexes and 
    <a href="netvista.net_luid">NET_LUID</a> values that are associated with a
    binding.

<b>NdisIfQueryBindingIfIndex</b> provides the NET_LUID value and the interface index for the highest
    interface and lowest interface that are associated with the binding. These values are different, for
    example, if the miniport adapter that is directly associated with the specified binding is the virtual
    miniport of a filter intermediate driver or if there is a filter module that is configured over the
    miniport adapter.

Protocol drivers can also obtain the interface index and NET_LUID of the highest and the lowest
    interfaces in a driver stack in the 
    <a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure.

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
<a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.net_luid">NET_LUID</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfQueryBindingIfIndex function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
