---
UID: NC.netioddk.NPI_PROVIDER_ATTACH_CLIENT_FN
title: NPI_PROVIDER_ATTACH_CLIENT_FN
author: windows-driver-content
description: A provider module's ProviderAttachClient callback function attaches the provider module to a client module.
old-location: netvista\providerattachclient.htm
old-project: netvista
ms.assetid: 6c8e6cf1-0528-4da2-acc1-81ec9dbc23c3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NET_DMA_PROVIDER_CHARACTERISTICS, *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
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
req.alt-api: PNPI_PROVIDER_ATTACH_CLIENT_FN
req.alt-loc: netioddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NPI_PROVIDER_ATTACH_CLIENT_FN callback



## -description
A provider module's 
  <i>ProviderAttachClient</i> callback function attaches the provider module to a client module.



## -prototype

````
NPI_PROVIDER_ATTACH_CLIENT_FN ProviderAttachClient;

NTSTATUS ProviderAttachClient(
  _In_        HANDLE                     NmrBindingHandle,
  _In_        PVOID                      ProviderContext,
  _In_        PNPI_REGISTRATION_INSTANCE ClientRegistrationInstance,
  _In_        PVOID                      ClientBindingContext,
  _In_  const VOID                       *ClientDispatch,
  _Out_       PVOID                      *ProviderBindingContext,
  _Out_ const VOID                       **ProviderDispatch
)
{ ... }

typedef NPI_PROVIDER_ATTACH_CLIENT_FN * PNPI_PROVIDER_ATTACH_CLIENT_FN;
````


## -parameters

### -param NmrBindingHandle [in]

A handle used by the NMR to represent the binding between the client module and the provider
     module.


### -param ProviderContext [in]

A pointer to the provider module's registration context. The provider module passes this pointer
     to the NMR when it calls the 
     <a href="netvista.nmrregisterprovider">NmrRegisterProvider</a> function to
     register itself with the NMR.


### -param ClientRegistrationInstance [in]

A pointer to an 
     <a href="netvista.npi_registration_instance">
     NPI_REGISTRATION_INSTANCE</a> structure. This structure contains the client module's registration
     data.


### -param ClientBindingContext [in]

A pointer to the client module's context for the binding between the client module and the
     provider module. The client module uses this context to keep track of the state of the binding. The
     contents of the client module's binding context are opaque to the provider module. The provider module
     passes this pointer to the client module whenever it calls any of the client module's 
     <a href="netvista.network_programming_interface">NPI</a> callback functions that
     require the client module's binding context.


### -param ClientDispatch [in]

A pointer to a constant structure that contains the dispatch table of 
     <a href="netvista.network_programming_interface">NPI</a> callback functions for the
     client module. The contents of the structure are 
     NPI-specific. If the 
     NPI does not define a client
     dispatch table structure, then this pointer is <b>NULL</b>.


### -param ProviderBindingContext [out]

A pointer to a variable into which the provider module will store a pointer to its context for the
     binding between the client module and the provider module. The provider module uses this context to keep
     track of the state of the binding. The contents of the provider module's binding context are opaque to
     the client module. The client module passes this pointer to the provider module whenever it calls one of
     the provider module's 
     <a href="netvista.network_programming_interface">NPI</a> functions that require the
     provider module's binding context. The provider module must make sure that this context remains valid
     and resident in memory as long as the client module is attached to the provider module.


### -param ProviderDispatch [out]

A pointer to a variable into which the provider module will store a pointer to a constant
     structure that contains the dispatch table of 
     <a href="netvista.network_programming_interface">NPI</a> functions for the provider
     module. The provider module must make sure that this structure remains valid and resident in memory as
     long as the client module is attached to the provider module. The contents of the structure are 
     NPI-specific.


## -returns
A provider module's 
     <i>ProviderAttachClient</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The provider module successfully attached to the client module.
<dl>
<dt><b>STATUS_NOINTERFACE</b></dt>
</dl>The provider module did not attach to the client module.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
The NMR calls a provider module's 
    <i>ProviderAttachClient</i> callback function whenever a client module calls the 
    <a href="netvista.nmrclientattachprovider">NmrClientAttachProvider</a> function
    with a handle that represents a binding between the client module and the provider module.

A provider module can examine the client module's registration data. This data is in the structure
    pointed to by the 
    <i>ClientRegistrationInstance</i> parameter. The provider module uses this data to determine whether it
    will attach to the client module:

If the provider module determines that it will not attach to the client module, then the 
      <i>ProviderAttachClient</i> callback function must return STATUS_NOINTERFACE.

If the provider module attaches to the client module and it dynamically allocated memory for its
    binding context, it should free that allocated memory when the NMR calls the provider module's 
    <a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
    ProviderCleanupBindingContext</a> callback function after the client module and provider module are
    detached from each other.

The NMR calls a provider module's 
    <i>ProviderAttachClient</i> callback function at IRQL = PASSIVE_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Netioddk.h (include Wsk.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.nmrregisterprovider">NmrRegisterProvider</a>
</dt>
<dt>
<a href="netvista.nmrclientattachprovider">NmrClientAttachProvider</a>
</dt>
<dt>
<a href="netvista.nmrproviderdetachclientcomplete">
   NmrProviderDetachClientComplete</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
   ProviderCleanupBindingContext</a>
</dt>
<dt>
<a href="netvista.npi_registration_instance">NPI_REGISTRATION_INSTANCE</a>
</dt>
<dt>
<a href="netvista.npi_provider_characteristics">NPI_PROVIDER_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_PROVIDER_ATTACH_CLIENT_FN callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

