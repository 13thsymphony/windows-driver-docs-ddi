---
UID: NS:netioddk._NPI_PROVIDER_CHARACTERISTICS
title: "_NPI_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.
old-location: netvista\npi_provider_characteristics.htm
old-project: netvista
ms.assetid: a83220e8-496c-4b83-b774-88ab1f017e8d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PNPI_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], netvista.npi_provider_characteristics, nmrref_ceebed62-8102-41e3-af13-e663c1e8babb.xml, NPI_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNPI_PROVIDER_CHARACTERISTICS, _NPI_PROVIDER_CHARACTERISTICS, NPI_PROVIDER_CHARACTERISTICS, netioddk/NPI_PROVIDER_CHARACTERISTICS, netioddk/PNPI_PROVIDER_CHARACTERISTICS
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netioddk.h
apiname:
-	NPI_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NPI_PROVIDER_CHARACTERISTICS
---

# _NPI_PROVIDER_CHARACTERISTICS structure
The NPI_PROVIDER_CHARACTERISTICS structure defines the characteristics of a provider module.

## Syntax
````
typedef struct _NPI_PROVIDER_CHARACTERISTICS {
  USHORT                                   Version;
  USHORT                                   Length;
  PNPI_PROVIDER_ATTACH_CLIENT_FN           ProviderAttachClient;
  PNPI_PROVIDER_DETACH_CLIENT_FN           ProviderDetachClient;
  PNPI_PROVIDER_CLEANUP_BINDING_CONTEXT_FN ProviderCleanupBindingContext;
  NPI_REGISTRATION_INSTANCE                ProviderRegistrationInstance;
} NPI_PROVIDER_CHARACTERISTICS, *PNPI_PROVIDER_CHARACTERISTICS;
````

## Members


`Length`

The size, in bytes, of the NPI_PROVIDER_CHARACTERISTICS structure.

`ProviderAttachClient`

A pointer to the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_attach_client_fn.md">ProviderAttachClient</a> callback
     function.

`ProviderCleanupBindingContext`

A pointer to the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
     ProviderCleanupBindingContext</a> callback function. If the provider module does not dynamically
     allocate the memory for its binding context and no other cleanup of its binding context is required,
     then the provider module does not need to implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function. If the provider module does not implement a 
     <i>
     ProviderCleanupBindingContext</i> callback function, then this member must be set to <b>NULL</b>.

`ProviderDetachClient`

A pointer to the provider module's 
     <a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a> callback
     function.

`ProviderRegistrationInstance`

An 
     <a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">
     NPI_REGISTRATION_INSTANCE</a> structure that specifies the identity of the provider module and the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which it is
     registering.

`Version`

The version of the NMR with which the provider is registering. A provider module should set this
     member to zero.

## Remarks
A provider module passes a pointer to an NPI_PROVIDER_CHARACTERISTICS structure to the 
    <a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a> function when it
    registers itself with the NMR.

A provider module must make sure that this structure remains valid and resident in memory as long as
    the provider module is registered with the NMR.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | netioddk.h (include Wsk.h) |

## See Also

<a href="..\netioddk\nc-netioddk-npi_provider_detach_client_fn.md">ProviderDetachClient</a>



<a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
   ProviderCleanupBindingContext</a>



<a href="..\netioddk\nf-netioddk-nmrregisterprovider.md">NmrRegisterProvider</a>



<a href="..\netioddk\ns-netioddk-_npi_registration_instance.md">NPI_REGISTRATION_INSTANCE</a>



<a href="..\netioddk\nc-netioddk-npi_provider_cleanup_binding_context_fn.md">
   ProviderCleanupBindingContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NPI_PROVIDER_CHARACTERISTICS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>