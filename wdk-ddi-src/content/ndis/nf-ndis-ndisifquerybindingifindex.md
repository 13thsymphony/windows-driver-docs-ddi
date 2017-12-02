---
UID: NF.ndis.NdisIfQueryBindingIfIndex
title: NdisIfQueryBindingIfIndex
author: windows-driver-content
description: The NdisIfQueryBindingIfIndex function retrieves the network interface indexes and NET_LUID values for the highest and lowest layered network interfaces that are associated with a specified protocol binding.
old-location: netvista\ndisifquerybindingifindex.htm
old-project: netvista
ms.assetid: 08f31584-b3ea-4e6e-b8ce-17813ca7c06b
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.iface: 
---

# NdisIfQueryBindingIfIndex function



## -description
<p>The 
  <b>NdisIfQueryBindingIfIndex</b> function retrieves the network interface indexes and 
  <a href="netvista.net_luid">NET_LUID</a> values for the highest and lowest layered
  network interfaces that are associated with a specified protocol binding.</p>


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
<dl>

### -param NdisBindingHandle [in]

<dd>
<p>A handle that identifies the binding for which NDIS should obtain the 
     <a href="netvista.net_luid">NET_LUID</a> values and network interface indexes.
     NDIS provided this handle at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.</p>
</dd>

### -param pBoundIfIndex [out]

<dd>
<p>A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is highest in the driver
     stack.</p>
</dd>

### -param pBoundIfNetLuid [out]

<dd>
<p>A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is highest in the driver stack.</p>
</dd>

### -param pLowestIfIndex [out]

<dd>
<p>A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the network interface index of
     the network interface that is associated with the specified binding and is lowest in the driver
     stack.</p>
</dd>

### -param pLowestIfNetLuid [out]

<dd>
<p>A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfQueryBindingIfIndex</b> succeeds, NDIS writes to this variable the NET_LUID value of the network
     interface that is associated with the specified binding and is lowest in the driver stack.</p>
</dd>
</dl>

## -returns
<p><b>NdisIfQueryBindingIfIndex</b> returns one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl><p><b>NdisIfQueryBindingIfIndex</b> failed because the specified binding is not
       associated with a registered interface.</p>

<p> </p>

## -remarks
<p>NDIS protocol drivers can call the 
    <b>NdisIfQueryBindingIfIndex</b> function to retrieve the network interface indexes and 
    <a href="netvista.net_luid">NET_LUID</a> values that are associated with a
    binding.</p>

<p><b>NdisIfQueryBindingIfIndex</b> provides the NET_LUID value and the interface index for the highest
    interface and lowest interface that are associated with the binding. These values are different, for
    example, if the miniport adapter that is directly associated with the specified binding is the virtual
    miniport of a filter intermediate driver or if there is a filter module that is configured over the
    miniport adapter.</p>

<p>Protocol drivers can also obtain the interface index and NET_LUID of the highest and the lowest
    interfaces in a driver stack in the 
    <a href="..\ndis\ns-ndis--ndis-bind-parameters.md">NDIS_BIND_PARAMETERS</a> structure.</p>

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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_interfaces_function">Irql_Interfaces_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis--ndis-bind-parameters.md">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.net_luid">NET_LUID</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfQueryBindingIfIndex function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
