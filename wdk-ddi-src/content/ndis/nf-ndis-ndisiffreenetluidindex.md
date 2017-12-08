---
UID: NF.ndis.NdisIfFreeNetLuidIndex
title: NdisIfFreeNetLuidIndex function
author: windows-driver-content
description: The NdisIfFreeNetLuidIndex function frees a network interface NET_LUID index that was previously allocated by a call to the NdisIfAllocateNetLuidIndex function.
old-location: netvista\ndisiffreenetluidindex.htm
old-project: netvista
ms.assetid: eba881f8-e946-44a8-9624-37f63471fb65
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisIfFreeNetLuidIndex
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
req.alt-api: NdisIfFreeNetLuidIndex
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

# NdisIfFreeNetLuidIndex function



## -description
The 
  <b>NdisIfFreeNetLuidIndex</b> function frees a network interface 
  <a href="netvista.net_luid">NET_LUID</a> index that was previously allocated by a
  call to the 
  <a href="netvista.ndisifallocatenetluidindex">
  NdisIfAllocateNetLuidIndex</a> function.


## -syntax

````
NDIS_STATUS NdisIfFreeNetLuidIndex(
  _In_ NET_IFTYPE IfType,
  _In_ UINT32     NetLuidIndex
);
````


## -parameters

### -param IfType [in]

The interface type that the index was allocated for. The caller must provide the same value that
     it used when it allocated the NET_LUID index with 
     <a href="netvista.ndisifallocatenetluidindex">NdisIfAllocateNetLuidIndex</a>.
     For a list of interface types, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565767">NDIS Interface Types</a>.

### -param NetLuidIndex [in]

The NET_LUID index value that NDIS should free. This index was allocated in a previous call to 
     <b>NdisIfAllocateNetLuidIndex</b>.

## -returns
<b>NdisIfFreeNetLuidIndex</b> returns one of the following values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>DIS_STATUS_INVALID_PARAMETER</b></dt>
</dl><b>NdisIfFreeNetLuidIndex</b> failed because the 
       <i>NetLuidIndex</i> parameter specified an index that was not allocated for the type that the 
       <i>IfType</i> parameter specified.

 

If the call to 
     <b>NdisIfFreeNetLuidIndex</b> fails, the
     interface provider should remove any information that it saved in persistent storage that is related to
     the index. Removing the information will ensure that the provider does not keep trying to free an index
     that is already freed after the computer restarts.

## -remarks
NDIS interface providers call the 
    <b>NdisIfFreeNetLuidIndex</b> function to free a 
    <a href="netvista.net_luid">NET_LUID</a> index. The interface provider should free
    the NET_LUID index only if the interface will not be used anymore on the local computer.

<b>NdisIfFreeNetLuidIndex</b> returns a previously allocated NET_LUID index to NDIS for possible
    reallocation to another interface. The caller must pass in the same interface type at 
    <i>IfType</i> that it used when it called the 
    <a href="netvista.ndisifallocatenetluidindex">
    NdisIfAllocateNetLuidIndex</a> function to allocate the NET_LUID index.

The provider should not use the freed NET_LUID index or the associated NET_LUID value in any other
    NDIS function calls after it calls 
    <b>NdisIfFreeNetLuidIndex</b>.

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
<a href="netvista.ndisifallocatenetluidindex">NdisIfAllocateNetLuidIndex</a>
</dt>
<dt>
<a href="netvista.net_luid">NET_LUID</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfFreeNetLuidIndex function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
