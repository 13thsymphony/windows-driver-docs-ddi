---
UID: NF:ndis.NdisQueryAdapterInstanceName
title: NdisQueryAdapterInstanceName function
author: windows-driver-content
description: The NdisQueryAdapterInstanceName function retrieves the friendly name of a physical NIC or a virtual adapter that the calling protocol driver is bound to.
old-location: netvista\ndisqueryadapterinstancename.htm
old-project: netvista
ms.assetid: bd6fade6-9b9b-4b38-8e53-c70c40c1165f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisQueryAdapterInstanceName, NdisQueryAdapterInstanceName function [Network Drivers Starting with Windows Vista], ndis/NdisQueryAdapterInstanceName, netvista.ndisqueryadapterinstancename, protocol_ndis_functions_ref_e9e2070d-3b82-43a6-8964-92296de4c896.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisQueryAdapterInstanceName
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisQueryAdapterInstanceName function
The 
  <b>NdisQueryAdapterInstanceName</b> function retrieves the friendly name of a physical NIC or a virtual
  adapter that the calling protocol driver is bound to.

## Syntax

````
NDIS_STATUS NdisQueryAdapterInstanceName(
  _Out_ PNDIS_STRING AdapterInstanceName,
  _In_  NDIS_HANDLE  NdisBindingHandle
);
````

## Parameters

`pAdapterInstanceName`

TBD

`NdisBindingHandle`

A handle that identifies the binding to the target physical NIC or virtual adapter of the
     next-lower driver to which the caller is bound. Typically, 
     <i>NdisBindingHandle</i> was returned by the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


## Return Value

<b>NdisQueryAdapterInstanceName</b> returns NDIS_STATUS_SUCCESS if memory for the string at 
     <i>AdapterInstanceName</i> was successfully allocated; otherwise, it returns
     NDIS_STATUS_RESOURCES.

## Remarks

A protocol driver uses 
    <b>NdisQueryAdapterInstanceName</b> to retrieve the friendly name of a physical NIC or a virtual adapter
    to which the protocol driver is bound. The protocol driver specifies the handle to such a NIC or virtual
    adapter in 
    <i>NdisBindingHandle</i> . The protocol driver calls the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function to retrieve
    this handle.

<b>NdisQueryAdapterInstanceName</b> allocates memory for the string that specifies the friendly name.
    After the caller finishes using this memory, the caller must call the 
    <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function to release the
    memory.

Friendly names are intended to help the user quickly and accurately identify a physical NIC or virtual
    adapter--for example, "PCI Ethernet Adapter" and "Virtual Private Networking Adapter" are considered
    friendly names.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryAdapterInstanceName   (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueryAdapterInstanceName function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>