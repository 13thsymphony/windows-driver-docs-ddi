---
UID: NF:ndis.NdisIfGetInterfaceIndexFromNetLuid
title: NdisIfGetInterfaceIndexFromNetLuid function
author: windows-driver-content
description: The NdisIfGetInterfaceIndexFromNetLuid function gets the network interface index that is associated with a NET_LUID value.
old-location: netvista\ndisifgetinterfaceindexfromnetluid.htm
old-project: netvista
ms.assetid: 6aaa4ae9-fd3c-4cdd-ac37-0533c45143af
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisIfGetInterfaceIndexFromNetLuid, NdisIfGetInterfaceIndexFromNetLuid function [Network Drivers Starting with Windows Vista], ndis/NdisIfGetInterfaceIndexFromNetLuid, net_if_functions_ref_d375ff1d-3f7f-4f11-8fd3-c41340276d30.xml, netvista.ndisifgetinterfaceindexfromnetluid
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
-	NdisIfGetInterfaceIndexFromNetLuid
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisIfGetInterfaceIndexFromNetLuid function
The 
  <b>NdisIfGetInterfaceIndexFromNetLuid</b> function gets the network interface index that is associated with
  a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value.

## Syntax

````
NDIS_STATUS NdisIfGetInterfaceIndexFromNetLuid(
  _In_  NET_LUID     NetLuid,
  _Out_ PNET_IFINDEX pIfIndex
);
````

## Parameters

`NetLuid`

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value that identifies a network
     interface.

`pIfIndex`

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfGetInterfaceIndexFromNetLuid</b> succeeds, NDIS writes the network interface index that is
     associated with the specified NET_LUID to this variable.


## Return Value

<b>NdisIfGetInterfaceIndexFromNetLuid</b> returns one of the following status values:

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
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisIfGetInterfaceIndexFromNetLuid</b> failed because the specified NET_LUID was not present in the
       list of registered interfaces.

</td>
</tr>
</table>

## Remarks

NDIS drivers can call the 
    <b>NdisIfGetInterfaceIndexFromNetLuid</b> function to get the network interface index that is associated
    with a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value.

For the interfaces that the NDIS proxy provider service manages, NDIS provides the interface index and
    NET_LUID in various driver initialization structures:

<ul>
<li>
Miniport drivers can obtain the interface index and NET_LUID for a miniport adapter in the 
      <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">
      NDIS_MINIPORT_INIT_PARAMETERS</a> structure.

</li>
<li>
Filter drivers can obtain the interface index and NET_LUID for a filter module in the 
      <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
      NDIS_FILTER_ATTACH_PARAMETERS</a> structure.

</li>
<li>
Protocol drivers can obtain the interface index and NET_LUID of the highest and the lowest
      interfaces on a driver stack in the 
      <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure.

</li>
</ul>
NDIS assigns an interface index to a network interface when the interface provider calls the 
    <a href="..\ndis\nf-ndis-ndisifregisterinterface.md">NdisIfRegisterInterface</a> function.
    An interface provider calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff565890">NDIS_MAKE_NET_LUID</a> macro to create the
    NET_LUID value before it registers an interface.

The interface index value can change without a computer restart. Deregistering and re-registering an
    interface that is associated with a NET_LUID value might result in different interface index values. Do
    not confuse the interface index with the NET_LUID index that persists after a computer restarts.

NDIS provides the 
    <a href="..\ndis\nf-ndis-ndisifgetnetluidfrominterfaceindex.md">
    NdisIfGetNetLuidFromInterfaceIndex</a> function to get the NET_LUID value that is associated with a
    specified interface index.

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

<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisifregisterinterface.md">NdisIfRegisterInterface</a>



<a href="..\ndis\nf-ndis-ndisifgetnetluidfrominterfaceindex.md">
   NdisIfGetNetLuidFromInterfaceIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565890">NDIS_MAKE_NET_LUID</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfGetInterfaceIndexFromNetLuid function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>