---
UID: NF:netioddk.NmrClientDetachProviderComplete
title: NmrClientDetachProviderComplete function
author: windows-driver-content
description: The NmrClientDetachProviderComplete function notifies the NMR that a client module has completed detaching from a provider module.
old-location: netvista\nmrclientdetachprovidercomplete.htm
old-project: netvista
ms.assetid: e54864de-9558-44b1-9c5a-0f2ecc6516b1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NmrClientDetachProviderComplete, NmrClientDetachProviderComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrClientDetachProviderComplete, netvista.nmrclientdetachprovidercomplete, nmrref_7fb0e7ef-62a3-4dc4-a0e2-b38005056317.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	netio.lib
-	netio.dll
api_name:
-	NmrClientDetachProviderComplete
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---


# NmrClientDetachProviderComplete function
The 
  <b>NmrClientDetachProviderComplete</b> function notifies the NMR that a client module has completed
  detaching from a provider module.

## Syntax

````
VOID NmrClientDetachProviderComplete(
  _In_ HANDLE NmrBindingHandle
);
````

## Parameters

`NmrBindingHandle`

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the client module when it calls the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a> callback
     function.


## Return Value

None

## Remarks

A client module calls the 
    <b>NmrClientDetachProviderComplete</b> function when it asynchronously completes detaching from a provider
    module after returning STATUS_PENDING from its 
    <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
    function.

A client module should not call the 
    <b>NmrClientDetachProviderComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
    function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems.  |
| **Target Platform** | Desktop |
| **Header** | netioddk.h (include Wsk.h) |
| **Library** | Netio.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a>



<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrClientDetachProviderComplete function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>