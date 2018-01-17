---
UID: NS:netioddk._NPI_CLIENT_CHARACTERISTICS
title: _NPI_CLIENT_CHARACTERISTICS
author: windows-driver-content
description: The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.
old-location: netvista\npi_client_characteristics.htm
old-project: netvista
ms.assetid: 03d73a80-0860-4ec7-8eb1-5954f64b6026
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NPI_CLIENT_CHARACTERISTICS, NPI_CLIENT_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NPI_CLIENT_CHARACTERISTICS
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
req.irql: < DISPATCH_LEVEL
req.typenames: NPI_CLIENT_CHARACTERISTICS
---

# _NPI_CLIENT_CHARACTERISTICS structure



## -description
The NPI_CLIENT_CHARACTERISTICS structure defines the characteristics of a client module.



## -syntax

````
typedef struct _NPI_CLIENT_CHARACTERISTICS {
  USHORT                                 Version;
  USHORT                                 Length;
  PNPI_CLIENT_ATTACH_PROVIDER_FN         ClientAttachProvider;
  PNPI_CLIENT_DETACH_PROVIDER_FN         ClientDetachProvider;
  PNPI_CLIENT_CLEANUP_BINDING_CONTEXT_FN ClientCleanupBindingContext;
  NPI_REGISTRATION_INSTANCE              ClientRegistrationInstance;
} NPI_CLIENT_CHARACTERISTICS, *PNPI_CLIENT_CHARACTERISTICS;
````


## -struct-fields

### -field Version

The version of the NMR with which the client is registering. A client module should set this
     member to zero.


### -field Length

The size, in bytes, of the NPI_CLIENT_CHARACTERISTICS structure.


### -field ClientAttachProvider

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a> callback
     function.


### -field ClientDetachProvider

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a> callback
     function.


### -field ClientCleanupBindingContext

A pointer to the client module's 
     <a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">
     ClientCleanupBindingContext</a> callback function. If the client module does not dynamically allocate
     the memory for its binding context and no other cleanup of its binding context is required, then the
     client module does not need to implement a 
     <i>
     ClientCleanupBindingContext</i> callback function. If the client module does not implement a 
     <i>
     ClientCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.


### -field ClientRegistrationInstance

An 
     <a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the client module and the 
     <a href="netvista.network_programming_interface">NPI</a> for which it is
     registering.


## -remarks
A client module passes a pointer to an NPI_CLIENT_CHARACTERISTICS structure to the 
    <a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a> function when it
    registers itself with the NMR.

A client module must make sure that this structure remains valid and resident in memory as long as the
    client module is registered with the NMR.


## -see-also
<dl>
<dt>
<a href="..\netioddk\nf-netioddk-nmrregisterclient.md">NmrRegisterClient</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_client_attach_provider_fn.md">ClientAttachProvider</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_client_cleanup_binding_context_fn.md">ClientCleanupBindingContext</a>
</dt>
<dt>
<a href="..\netioddk\nc-netioddk-npi_client_detach_provider_fn.md">ClientDetachProvider</a>
</dt>
<dt>
<a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">NPI_REGISTRATION_INSTANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_CLIENT_CHARACTERISTICS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

