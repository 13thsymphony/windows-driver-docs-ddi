---
UID: NC:netioddk.NPI_PROVIDER_DETACH_CLIENT_FN
title: NPI_PROVIDER_DETACH_CLIENT_FN
author: windows-driver-content
description: A provider module's ProviderDetachClient callback function detaches the provider module from a client module.
old-location: netvista\providerdetachclient.htm
old-project: netvista
ms.assetid: 0f29bf89-856c-4019-a966-3e666a7fc78d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NPI_PROVIDER_DETACH_CLIENT_FN, PNPI_PROVIDER_DETACH_CLIENT_FN, PNPI_PROVIDER_DETACH_CLIENT_FN callback function [Network Drivers Starting with Windows Vista], ProviderDetachClient, ProviderDetachClient callback function [Network Drivers Starting with Windows Vista], netioddk/ProviderDetachClient, netvista.providerdetachclient, nmrref_04fc189d-40e1-4cc5-87ea-dda2664f7e63.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	netioddk.h
api_name:
-	PNPI_PROVIDER_DETACH_CLIENT_FN
product: Windows
targetos: Windows
req.typenames: NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---


# NPI_PROVIDER_DETACH_CLIENT_FN callback function
A provider module's 
  <i>ProviderDetachClient</i> callback function detaches the provider module from a client module.

## Syntax

```
NPI_PROVIDER_DETACH_CLIENT_FN NpiProviderDetachClientFn;

NTSTATUS NpiProviderDetachClientFn(
  PVOID ProviderBindingContext
)
{...}
```

## Parameters

`ProviderBindingContext`

A pointer to the provider module's context for the binding between the provider module and the
     client module from which it is detaching. The provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function returns this pointer to the NMR when it attaches to the client module.


## Return Value

A provider module's 
     <i>ProviderDetachClient</i> callback function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The provider module successfully detached from the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The provider module could not detach from the client module immediately.

</td>
</tr>
</table>

## Remarks

The NMR calls a provider module's 
    <i>ProviderDetachClient</i> callback function whenever the binding between the provider module and a
    client module needs to be terminated. Detachment is initiated by either the client module calling the 
    <a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a> function or the
    provider module calling the 
    <a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a> function.

After its 
    <i>ProviderDetachClient</i> callback function has been called, a provider module should not make any more
    calls to any of the client module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions. If there
    are no in-progress calls to any of the client module's 
    NPI callback functions when the
    provider module's 
    <i>ProviderDetachClient</i> callback function is called, then the provider module's 
    <i>ProviderDetachClient</i> callback function returns STATUS_SUCCESS.

If there are in-progress calls to one or more of the client module's 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> callback functions when the
    provider module's 
    <i>ProviderDetachClient</i> callback function is called, the provider module's 
    <i>ProviderDetachClient</i> callback function returns STATUS_PENDING. In this situation, the provider
    module must call the 
    <a href="..\netioddk\nf-netioddk-nmrproviderdetachclientcomplete.md">
    NmrProviderDetachClientComplete</a> function after all in-progress calls to the client module's 
    NPI callback functions have
    completed. The call to the 
    <b>
    NmrProviderDetachClientComplete</b> function notifies the NMR that detachment from the client module is
    complete.

The NMR calls the client module's 
    <a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">
    ClientCleanupBindingContext</a> callback function and the provider module's 
    <a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
    ProviderCleanupBindingContext</a> callback function after both the client module and the provider
    module have completed detaching from each other.

The NMR calls a provider module's 
    <i>ProviderDetachClient</i> callback function at any IRQL &lt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems.  |
| **Target Platform** | Windows |
| **Header** | netioddk.h (include Wsk.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a>



<a href="..\netioddk\nf-netioddk-nmrderegisterclient.md">NmrDeregisterClient</a>



<a href="..\netioddk\nf-netioddk-nmrproviderdetachclientcomplete.md">
   NmrProviderDetachClientComplete</a>



<a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">ClientCleanupBindingContext</a>



<a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
   ProviderCleanupBindingContext</a>



<a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_PROVIDER_DETACH_CLIENT_FN callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>