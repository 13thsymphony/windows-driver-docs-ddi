---
UID : NC:netioddk.NPI_CLIENT_ATTACH_PROVIDER_FN
title : NPI_CLIENT_ATTACH_PROVIDER_FN
author : windows-driver-content
description : A client module's ClientAttachProvider callback function attaches the client module to a provider module.
old-location : netvista\clientattachprovider.htm
old-project : netvista
ms.assetid : 8f8abdb1-d018-4404-a80a-74017c324a0f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.clientattachprovider, ClientAttachProvider callback function [Network Drivers Starting with Windows Vista], ClientAttachProvider, NPI_CLIENT_ATTACH_PROVIDER_FN, NPI_CLIENT_ATTACH_PROVIDER_FN, netioddk/ClientAttachProvider, PNPI_CLIENT_ATTACH_PROVIDER_FN callback function [Network Drivers Starting with Windows Vista], PNPI_CLIENT_ATTACH_PROVIDER_FN, nmrref_36b8ce1f-6570-40a1-b6f9-5d6782aac61d.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : netioddk.h
req.include-header : Wsk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS
---


# NPI_CLIENT_ATTACH_PROVIDER_FN callback function
A client module's 
  <i>ClientAttachProvider</i> callback function attaches the client module to a provider module.

## Syntax

```
NPI_CLIENT_ATTACH_PROVIDER_FN NpiClientAttachProviderFn;

NTSTATUS NpiClientAttachProviderFn(
  HANDLE NmrBindingHandle,
  PVOID ClientContext,
  PNPI_REGISTRATION_INSTANCE ProviderRegistrationInstance
)
{...}
```

## Parameters

`NmrBindingHandle`

A handle used by the NMR to represent the binding between the client module and the provider
     module.

`ClientContext`

A pointer to the client module's registration context. The client module passes this pointer to
     the NMR when it calls the 
     <a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a> function to register
     itself with the NMR.

`ProviderRegistrationInstance`

A pointer to an 
     <mshelp:link keywords="netvista.npi_registration_instance" tabindex="0"><b>
     NPI_REGISTRATION_INSTANCE</b></mshelp:link> structure. This structure contains the provider module's registration
     data.


## Return Value

A client module's 
     <i>ClientAttachProvider</i> callback function returns one of the following NTSTATUS codes:
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
The client module and the provider module successfully attached to each other.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
Either the client module did not attach to the provider module or the provider module did not
       attach to the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

After a client module has registered with the NMR, the NMR calls the client module's 
    <i>ClientAttachProvider</i> callback function, once for each provider module that is registered as a
    provider of the same 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the client module
    has registered as a client.

The NMR also calls a client module's 
    <i>ClientAttachProvider</i> callback function whenever a new network module registers as a provider of the
    same 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the client module
    has registered as a client.

A client module can examine the provider module's registration data. This data is in the structure
    pointed to by the 
    <i>ProviderRegistrationInstance</i> parameter. The client module uses this data to determine whether it
    will attach to the provider module:
<ul>
<li>
If the client module determines that it will attach to the provider module, then the 
      <i>ClientAttachProvider</i> callback function calls the 
      <a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a> function
      to continue the attachment process. In this situation the 
      <i>ClientAttachProvider</i> callback function must return the status code that is returned by the call
      to the 
      <b>
      NmrClientAttachProvider</b> function.

</li>
<li>
If the client module determines that it will not attach to the provider module, then the 
      <i>ClientAttachProvider</i> callback function must return STATUS_NOINTERFACE.

</li>
</ul>If the client module successfully attaches to the provider module, it must save the handle provided in
    the 
    <i>NmrBindingHandle</i> parameter. The client module passes this handle as a parameter to the 
    <mshelp:link keywords="netvista.nmrclientdetachprovidercomplete" tabindex="0"><b>
    NmrClientDetachProviderComplete</b></mshelp:link> function when it detaches from the provider module.

The NMR calls a client module's 
    <i>ClientAttachProvider</i> callback function at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | netioddk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\netioddk\ns-netioddk-_npi_client_characteristics.md">NPI_CLIENT_CHARACTERISTICS</a>

<a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a>

<mshelp:link keywords="netvista.nmrclientdetachprovidercomplete" tabindex="0"><b>
   NmrClientDetachProviderComplete</b></mshelp:link>

<a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">NPI_REGISTRATION_INSTANCE</a>

<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>

<a href="..\netioddk\nf-netioddk-nmrclientattachprovider.md">NmrClientAttachProvider</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_CLIENT_ATTACH_PROVIDER_FN callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>