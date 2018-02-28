---
UID: NF:ndis.NdisIfDeregisterProvider
title: NdisIfDeregisterProvider function
author: windows-driver-content
description: The NdisIfDeregisterProvider function deregisters an interface provider that was previously registered by a call to the NdisIfRegisterProvider function.
old-location: netvista\ndisifderegisterprovider.htm
old-project: netvista
ms.assetid: 90e921e3-b384-495b-8cb6-74596d060ec0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisIfDeregisterProvider, NdisIfDeregisterProvider function [Network Drivers Starting with Windows Vista], ndis/NdisIfDeregisterProvider, net_if_functions_ref_7e9c9d72-3b55-4001-9848-c79608608c82.xml, netvista.ndisifderegisterprovider
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
-	NdisIfDeregisterProvider
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisIfDeregisterProvider function
The 
  <b>NdisIfDeregisterProvider</b> function deregisters an interface provider that was previously registered by
  a call to the 
  <a href="..\ndis\nf-ndis-ndisifregisterprovider.md">
  NdisIfRegisterProvider</a> function.

## Syntax

````
VOID NdisIfDeregisterProvider(
  _In_ NDIS_HANDLE NdisProviderHandle
);
````

## Parameters

`NdisProviderHandle`

A handle that identifies the network interface provider. The caller obtained this handle from a
     previous call to the 
     <a href="..\ndis\nf-ndis-ndisifregisterprovider.md">
     NdisIfRegisterProvider</a> function.


## Return Value

None

## Remarks

NDIS drivers call the 
    <b>NdisIfDeregisterProvider</b> function to deregister as a network interface provider. NDIS drivers
    should deregister as interface providers when they are unloaded.

The interface provider must ensure that it does not have any interfaces registered when it calls 
    <b>NdisIfDeregisterProvider</b>. To deregister interfaces, the provider must call the 
    <a href="..\ndis\nf-ndis-ndisifderegisterinterface.md">
    NdisIfDeregisterInterface</a> function once for each registered interface.

The provider must not use the provider handle that it passed at the 
    <i>NdisProviderHandle</i> parameter after it calls 
    <b>NdisIfDeregisterProvider</b>.

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

<a href="..\ndis\nf-ndis-ndisifderegisterinterface.md">NdisIfDeregisterInterface</a>



<a href="..\ndis\nf-ndis-ndisifregisterprovider.md">NdisIfRegisterProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIfDeregisterProvider function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>