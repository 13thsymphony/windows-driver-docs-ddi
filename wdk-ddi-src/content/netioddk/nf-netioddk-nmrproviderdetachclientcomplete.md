---
UID: NF:netioddk.NmrProviderDetachClientComplete
title: NmrProviderDetachClientComplete function
author: windows-driver-content
description: The NmrProviderDetachClientComplete function notifies the NMR that a provider module has completed detaching from a client module.
old-location: netvista\nmrproviderdetachclientcomplete.htm
old-project: netvista
ms.assetid: a52b3cfc-d6bd-4569-8b09-36dce65d017f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NmrProviderDetachClientComplete, NmrProviderDetachClientComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrProviderDetachClientComplete, netvista.nmrproviderdetachclientcomplete, nmrref_c86f4d4f-b54f-4e31-b683-f692ff7ed1ba.xml
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
-	NmrProviderDetachClientComplete
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---


# NmrProviderDetachClientComplete function
The 
  <b>NmrProviderDetachClientComplete</b> function notifies the NMR that a provider module has completed
  detaching from a client module.

## Syntax

````
VOID NmrProviderDetachClientComplete(
  _In_ HANDLE NmrBindingHandle
);
````

## Parameters

`NmrBindingHandle`

A handle used by the NMR to represent the binding between the client module and the provider
     module. The NMR passes this handle to the provider module when it calls the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function.


## Return Value

None

## Remarks

A provider module calls the 
    <b>NmrProviderDetachClientComplete</b> function when it asynchronously completes detaching from a client
    module after returning STATUS_PENDING from its 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
    function.

A provider module should not call the 
    <b>NmrProviderDetachClientComplete</b> function if it returns STATUS_SUCCESS from its 
    <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
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

<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>



<a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrProviderDetachClientComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>