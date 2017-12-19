---
UID: NF.wdfregistry.WdfRegistryAssignMemory
title: WdfRegistryAssignMemory function
author: windows-driver-content
description: The WdfRegistryAssignMemory method assigns data that is contained in a specified memory buffer to a specified value name in the registry.
old-location: wdf\wdfregistryassignmemory.htm
old-project: wdf
ms.assetid: 692a9cdf-3cb7-41c1-96a8-28daed13aa60
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfRegistryAssignMemory
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
req.alt-api: WdfRegistryAssignMemory
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

# WdfRegistryAssignMemory function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignMemory</b> method assigns data that is contained in a specified memory buffer to a specified value name in the registry. 



## -syntax

````
NTSTATUS WdfRegistryAssignMemory(
  _In_     WDFKEY            Key,
  _In_     PCUNICODE_STRING  ValueName,
  _In_     ULONG             ValueType,
  _In_     WDFMEMORY         Memory,
  _In_opt_ PWDFMEMORY_OFFSET MemoryOffsets
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a value name. 


### -param ValueType [in]

A value that identifies the data type. For a list of data type values, see the <b>Type</b> member of <a href="kernel.key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>.


### -param Memory [in]

A handle to a framework memory object. This object represents a buffer that contains data that will be assigned to the value name that <i>ValueName</i> points to.


### -param MemoryOffsets [in, optional]

A pointer to a driver-supplied <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that identifies a subsection of the buffer that <i>Memory</i> specifies. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfRegistryAssignMemory</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="wdf.wdfregistryassignmemory">WdfRegistryAssignMemory</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver did not open the registry key with KEY_SET_VALUE access.
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>The contents of the <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that the <i>MemoryOffsets</i> parameter specified were invalid.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignMemory</b> updates the value's data.

For more information about registry-key objects, see <a href="wdf.using_the_registry_in_kmdf_drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example creates a framework memory object, loads the object's buffer with fake data, and assigns the buffer's contents to a registry value.


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
<a href="kernel.key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a>
</dt>
<dt>
<a href="wdf.wdfmemorycreate">WdfMemoryCreate</a>
</dt>
<dt>
<a href="wdf.wdfregistryassignvalue">WdfRegistryAssignValue</a>
</dt>
<dt>
<a href="wdf.wdfregistryassignmultistring">WdfRegistryAssignMultiString</a>
</dt>
<dt>
<a href="wdf.wdfregistryassignstring">WdfRegistryAssignString</a>
</dt>
<dt>
<a href="wdf.wdfregistryassignunicodestring">WdfRegistryAssignUnicodeString</a>
</dt>
<dt>
<a href="wdf.wdfregistryassignulong">WdfRegistryAssignULong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryAssignMemory method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

