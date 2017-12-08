---
UID: NF.wdfregistry.WdfRegistryQueryUnicodeString
title: WdfRegistryQueryUnicodeString function
author: windows-driver-content
description: The WdfRegistryQueryUnicodeString method retrieves the string data that is currently assigned to a specified registry string value and copies the string to a specified UNICODE_STRING structure.
old-location: wdf\wdfregistryqueryunicodestring.htm
old-project: wdf
ms.assetid: efbe5526-274b-416b-8e5c-8b18fe754b43
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfRegistryQueryUnicodeString
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
req.alt-api: WdfRegistryQueryUnicodeString
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

# WdfRegistryQueryUnicodeString function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfRegistryQueryUnicodeString</b> method retrieves the string data that is currently assigned to a specified registry string value and copies the string to a specified <a href="kernel.unicode_string">UNICODE_STRING</a> structure.


## -syntax

````
NTSTATUS WdfRegistryQueryUnicodeString(
  _In_      WDFKEY           Key,
  _In_      PCUNICODE_STRING ValueName,
  _Out_opt_ PUSHORT          ValueByteLength,
  _Inout_   PUNICODE_STRING  Value
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.

### -param ValueName [in]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a name for the registry value. 

### -param ValueByteLength [out, optional]

A pointer to a location that receives the number of bytes that are contained in the Unicode string that <i>Value</i> points to, including the terminating <b>NULL</b> byte. This pointer is optional and can be <b>NULL</b>

### -param Value [in, out]

A pointer to a UNICODE_STRING structure that receives the data string for the key that <i>Key</i> specifies. If this parameter is <b>NULL</b> and <i>ValueByteLength</i> is non-<b>NULL</b>, <b>WdfRegistryQueryUnicodeString</b> returns only the size of the string.

## -returns
<b>WdfRegistryQueryUnicodeString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="wdf.wdfregistryqueryunicodestring">WdfRegistryQueryUnicodeString</a> was not called at IRQL = PASSIVE_LEVEL. 
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
</dl>The data type of the registry value that the <i>ValueName</i> parameter specified was not REG_SZ.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer that the <i>Value</i> parameter points to was too small, and only partial data was written to the buffer.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The buffer that the <i>Value</i> parameter points to was too small, and no data was written to the buffer.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The registry value was not available.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
For more information about registry-key objects, see <a href="wdf.using_the_registry_in_kmdf_drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example, which is from the <a href="wdf.sample_kmdf_drivers">Serial</a> sample driver, retrieves the Unicode string that represents the string data that is assigned to the <b>PortName</b> value under a device's hardware key.

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
<a href="kernel.rtlinitunicodestring">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="wdf.wdfregistryclose">WdfRegistryClose</a>
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
<a href="wdf.wdfregistryqueryulong">WdfRegistryQueryULong</a>
</dt>
<dt>
<a href="wdf.wdfregistryqueryvalue">WdfRegistryQueryValue</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryQueryUnicodeString method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
