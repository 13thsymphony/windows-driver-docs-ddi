---
UID: NF:ndis.NdisFreeGenericObject
title: NdisFreeGenericObject function
author: windows-driver-content
description: Call the NdisFreeGenericObject function to free a generic object that was created with the NdisAllocateGenericObject function.
old-location: netvista\ndisfreegenericobject.htm
old-project: netvista
ms.assetid: 02c0ea87-d25d-4363-85e3-e47c4c5d8a9b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisFreeGenericObject, NdisFreeGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisFreeGenericObject, ndis_object_ref_d796ffda-61f1-473d-98ea-5ad3570889e9.xml, netvista.ndisfreegenericobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateGenericObject
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
-	NdisFreeGenericObject
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeGenericObject function
Call the 
  <b>NdisFreeGenericObject</b> function to free a generic object that was created with the 
  <a href="..\ndis\nf-ndis-ndisallocategenericobject.md">
  NdisAllocateGenericObject</a> function.

## Syntax

````
VOID NdisFreeGenericObject(
  _In_ PNDIS_GENERIC_OBJECT NdisGenericObject
);
````

## Parameters

`NdisObject`

TBD


## Return Value

None

## Remarks

An NDIS handle is required to allocate some NDIS resources (for example, buffer pools). Components
    that do not otherwise have an NDIS handle use a pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a> structure as an NDIS
    handle. All resources that were allocated with this generic object pointer as the handle must be freed
    before freeing the generic object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function, NdisAllocateGenericObject |

## See Also

<a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a>



<a href="..\ndis\nf-ndis-ndisallocategenericobject.md">NdisAllocateGenericObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeGenericObject function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>