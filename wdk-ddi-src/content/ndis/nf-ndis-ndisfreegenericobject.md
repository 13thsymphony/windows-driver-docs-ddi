---
UID: NF:ndis.NdisFreeGenericObject
title: NdisFreeGenericObject function
author: windows-driver-content
description: Call the NdisFreeGenericObject function to free a generic object that was created with the NdisAllocateGenericObject function.
old-location: netvista\ndisfreegenericobject.htm
old-project: netvista
ms.assetid: 02c0ea87-d25d-4363-85e3-e47c4c5d8a9b
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisFreeGenericObject
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
req.alt-api: NdisFreeGenericObject
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

# NdisFreeGenericObject function



## -description
Call the 
  <b>NdisFreeGenericObject</b> function to free a generic object that was created with the 
  <a href="..\ndis\nf-ndis-ndisallocategenericobject.md">
  NdisAllocateGenericObject</a> function.



## -syntax

````
VOID NdisFreeGenericObject(
  _In_ PNDIS_GENERIC_OBJECT NdisGenericObject
);
````


## -parameters

### -param NdisGenericObject [in]

A pointer to the 
     <a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a> structure to be
     freed.


## -returns
None


## -remarks
An NDIS handle is required to allocate some NDIS resources (for example, buffer pools). Components
    that do not otherwise have an NDIS handle use a pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_generic_object.md">NDIS_GENERIC_OBJECT</a> structure as an NDIS
    handle. All resources that were allocated with this generic object pointer as the handle must be freed
    before freeing the generic object.


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
<a href="..\ndis\nf-ndis-ndisallocategenericobject.md">NdisAllocateGenericObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeGenericObject function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

