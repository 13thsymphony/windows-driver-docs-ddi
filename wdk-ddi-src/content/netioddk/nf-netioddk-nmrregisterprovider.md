---
UID: NF:netioddk.NmrRegisterProvider
title: NmrRegisterProvider function
author: windows-driver-content
description: The NmrRegisterProvider function registers a provider module with the NMR.
old-location: netvista\nmrregisterprovider.htm
old-project: netvista
ms.assetid: aac9382c-5177-4216-bf3d-7970b18662eb
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NmrRegisterProvider
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
req.alt-api: NmrRegisterProvider
req.alt-loc: Netio.lib,Netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNET_DMA_PROVIDER_CHARACTERISTICS, NET_DMA_PROVIDER_CHARACTERISTICS
---

# NmrRegisterProvider function



## -description
The 
  <b>NmrRegisterProvider</b> function registers a provider module with the NMR.



## -syntax

````
NTSTATUS NmrRegisterProvider(
  _In_  PNPI_PROVIDER_CHARACTERISTICS ProviderCharacteristics,
  _In_  PVOID                         ProviderContext,
  _Out_ PHANDLE                       NmrProviderHandle
);
````


## -parameters

### -param ProviderCharacteristics [in]

A pointer to an 
     <a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">
     NPI_PROVIDER_CHARACTERISTICS</a> structure that describes the characteristics of the provider module.
     The provider module must make sure that this structure remains valid and resident in memory as long as
     the provider module is registered with the NMR.


### -param ProviderContext [in]

A pointer to a caller-supplied context for the registration. The provider module uses this context
     to keep track of the state of the provider registration. The contents of the provider module's
     registration context are opaque to the NMR. The NMR passes this pointer to the provider module whenever
     it calls the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function. The provider module must make sure that this context remains valid and resident in memory as
     long as the provider module is registered with the NMR.


### -param NmrProviderHandle [out]

A pointer to a variable that receives a handle used by the NMR to represent the registration of
     the provider module. The provider module must save this handle and pass it as a parameter to the 
     <a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a> function when
     it deregisters from the NMR.


## -returns
The 
     <b>NmrRegisterProvider</b> function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The NMR successfully registered the provider module.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The NMR did not have sufficient system resources to register the provider module.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A provider module calls the 
    <b>NmrRegisterProvider</b> function to register as a provider of an 
    <a href="netvista.network_programming_interface">NPI</a> so that it can attach to
    client modules that register as clients of the same 
    NPI.

A provider module typically calls the 
    <b>NmrRegisterProvider</b> function from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> function after it has completed
    all other initialization tasks. The call to the 
    <b>NmrRegisterProvider</b> function indicates to the NMR that the provider module is ready to attach to
    any client modules that have registered or will register as clients of the same 
    <a href="netvista.network_programming_interface">NPI</a> for which the provider module
    has registered as a provider.


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
Library

</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
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
<a href="..\netioddk\nf-netioddk-nmrderegisterprovider.md">NmrDeregisterProvider</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\netioddk\ns-netioddk-_npi_provider_characteristics.md">NPI_PROVIDER_CHARACTERISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NmrRegisterProvider function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

