---
UID: NF.wdfregistry.WdfRegistryQueryULong
title: WdfRegistryQueryULong function
author: windows-driver-content
description: The WdfRegistryQueryULong method retrieves the unsigned long word (REG_DWORD) data that is currently assigned to a specified registry value and copies the data to a specified location.
old-location: wdf\wdfregistryqueryulong.htm
old-project: wdf
ms.assetid: 54583406-9c60-4622-a78d-085c35ce7593
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfRegistryQueryULong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRegistryQueryULong
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfRegistryQueryULong function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryQueryULong</b> method retrieves the unsigned long word (REG_DWORD) data that is currently assigned to a specified registry value and copies the data to a specified location.



## -syntax

````
NTSTATUS WdfRegistryQueryULong(
  _In_  WDFKEY           Key,
  _In_  PCUNICODE_STRING ValueName,
  _Out_ PULONG           Value
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a name for the registry value. 


### -param Value [out]

A pointer to a location that receives the data that is assigned to the registry value that <i>ValueName</i> specifies.


## -returns
<b>WdfRegistryQueryULong</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="wdf.wdfregistryqueryulong">WdfRegistryQueryULong</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory to complete the operation.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver did not open the registry key with KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS access.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_DWORD.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The registry value was not available.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about registry-key objects, see <a href="wdf.using_the_registry_in_wdf_drivers">Using the Registry in WDF Drivers</a>.

The following code example retrieves the data that is currently assigned to the <b>NumberOfThings</b> value.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfregistry.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="wdf.wdfregistryquerymemory">WdfRegistryQueryMemory</a>
</dt>
<dt>
<a href="wdf.wdfregistryquerymultistring">WdfRegistryQueryMultiString</a>
</dt>
<dt>
<a href="wdf.wdfregistryquerystring">WdfRegistryQueryString</a>
</dt>
<dt>
<a href="wdf.wdfregistryqueryunicodestring">WdfRegistryQueryUnicodeString</a>
</dt>
<dt>
<a href="wdf.wdfregistryqueryvalue">WdfRegistryQueryValue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryULong method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

