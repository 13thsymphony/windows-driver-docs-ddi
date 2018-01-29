---
UID : NF:ndis.NdisAllocateGenericObject
title : NdisAllocateGenericObject function
author : windows-driver-content
description : Components that do not have an NDIS handle use the NdisAllocateGenericObject function to allocate a generic NDIS object.
old-location : netvista\ndisallocategenericobject.htm
old-project : netvista
ms.assetid : 166584fb-8a81-4a5b-93c9-3ad5348e15a7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis_object_ref_bb08930d-d264-4580-be64-a48061ab8ad4.xml, NdisAllocateGenericObject function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateGenericObject, NdisAllocateGenericObject, netvista.ndisallocategenericobject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miscellaneous_Function, NdisAllocateGenericObject
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisAllocateGenericObject function
Components that do not have an NDIS handle use the 
  <b>NdisAllocateGenericObject</b> function to allocate a generic NDIS object.

## Syntax

````
PNDIS_GENERIC_OBJECT NdisAllocateGenericObject(
   PDRIVER_OBJECT DriverObject,
   ULONG          Tag,
   USHORT         Size
);
````

## Parameters

`DriverObject`

A driver object to associate with the generic object. This parameter can be <b>NULL</b>.

`Tag`

The kernel memory tag that NDIS should use to allocate memory for the generic object.

`Size`

The amount of memory, in bytes, to reserve for the caller. This does not include the size of the 
     <a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a> structure. Use the
     additional memory space for your own purposes. To access the additional memory, use 
     sizeof(NDIS_GENERIC_OBJECT) to skip over the generic object structure.


## Return Value

<b>NdisAllocateGenericObject</b> returns a pointer to the NDIS_GENERIC_OBJECT that it allocated. If NDIS
     failed to create the object, the return value is <b>NULL</b>.

## Remarks

NDIS uses a generic object to manage resources that are allocated by a component that does not
    otherwise have an NDIS handle. Such a component uses the returned generic object pointer as an NDIS
    handle in some NDIS resource allocation APIs that require an NDIS handle.

NDIS drivers must call the 
    <a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a> function to
    free a generic object that was created with 
    <b>NdisAllocateGenericObject</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function, NdisAllocateGenericObject |

## See Also

<a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a>

<a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateGenericObject function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>