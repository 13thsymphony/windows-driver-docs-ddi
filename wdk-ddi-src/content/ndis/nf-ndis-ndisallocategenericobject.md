---
UID: NF:ndis.NdisAllocateGenericObject
title: NdisAllocateGenericObject function
author: windows-driver-content
description: Components that do not have an NDIS handle use the NdisAllocateGenericObject function to allocate a generic NDIS object.
old-location: netvista\ndisallocategenericobject.htm
old-project: netvista
ms.assetid: 166584fb-8a81-4a5b-93c9-3ad5348e15a7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisAllocateGenericObject
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
req.alt-api: NdisAllocateGenericObject
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateGenericObject
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateGenericObject function



## -description
Components that do not have an NDIS handle use the 
  <b>NdisAllocateGenericObject</b> function to allocate a generic NDIS object.



## -syntax

````
PNDIS_GENERIC_OBJECT NdisAllocateGenericObject(
   PDRIVER_OBJECT DriverObject,
   ULONG          Tag,
   USHORT         Size
);
````


## -parameters

### -param DriverObject [optional]

A driver object to associate with the generic object. This parameter can be <b>NULL</b>.


### -param Tag 

The kernel memory tag that NDIS should use to allocate memory for the generic object.


### -param Size 

The amount of memory, in bytes, to reserve for the caller. This does not include the size of the 
     <a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a> structure. Use the
     additional memory space for your own purposes. To access the additional memory, use 
     sizeof(NDIS_GENERIC_OBJECT) to skip over the generic object structure.


## -returns
<b>NdisAllocateGenericObject</b> returns a pointer to the NDIS_GENERIC_OBJECT that it allocated. If NDIS
     failed to create the object, the return value is <b>NULL</b>.


## -remarks
NDIS uses a generic object to manage resources that are allocated by a component that does not
    otherwise have an NDIS handle. Such a component uses the returned generic object pointer as an NDIS
    handle in some NDIS resource allocation APIs that require an NDIS handle.

NDIS drivers must call the 
    <a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a> function to
    free a generic object that was created with 
    <b>NdisAllocateGenericObject</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>, <a href="..\ndis\nf-ndis-ndisallocategenericobject.md">NdisAllocateGenericObject</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreegenericobject.md">NdisFreeGenericObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateGenericObject function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

