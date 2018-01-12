---
UID: NC:wdfregistry.PFN_WDFREGISTRYASSIGNUNICODESTRING
title: PFN_WDFREGISTRYASSIGNUNICODESTRING function
author: windows-driver-content
description: The WdfRegistryAssignUnicodeString method assigns a specified Unicode string to a specified value name in the registry.
old-location: wdf\wdfregistryassignunicodestring.htm
old-project: wdf
ms.assetid: 3a614b58-8230-4137-aae9-5c50e94bea5e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFREGISTRYASSIGNUNICODESTRING
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
req.alt-api: WdfRegistryAssignUnicodeString
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
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREGISTRYASSIGNUNICODESTRING function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryAssignUnicodeString</b> method assigns a specified Unicode string to a specified value name in the registry.



## -syntax

````
NTSTATUS WdfRegistryAssignUnicodeString(
  _In_ WDFKEY           Key,
  _In_ PCUNICODE_STRING ValueName,
  _In_ PCUNICODE_STRING Value
);
````


## -parameters

### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


### -param ValueName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains a value name. 


### -param Value [in]

A pointer to a UNICODE_STRING structure that contains the string to be assigned to the value name that <i>ValueName</i> specifies.


## -returns
<b>WdfRegistryAssignUnicodeString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignunicodestring.md">WdfRegistryAssignUnicodeString</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver did not open the registry key with KEY_SET_VALUE access.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There was insufficient memory to complete the operation.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If the string that the <i>Value</i> parameter specifies is not NULL-terminated, the framework adds a NULL character when copying the string to the registry.

If the value name that the <i>ValueName</i> parameter specifies already exists, <b>WdfRegistryAssignUnicodeString</b> updates the value's data.

The framework sets the value's data type to REG_SZ.

For more information about registry-key objects, see <a href="wdf.using_the_registry_in_kmdf_drivers">Using the Registry in Framework-Based Drivers</a>.

The following code example assigns a Unicode string "String1" to the <b>ValueName</b> value, under a specified registry key.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignvalue.md">WdfRegistryAssignValue</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmemory.md">WdfRegistryAssignMemory</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignmultistring.md">WdfRegistryAssignMultiString</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignstring.md">WdfRegistryAssignString</a>
</dt>
<dt>
<a href="..\wdfregistry\nf-wdfregistry-wdfregistryassignulong.md">WdfRegistryAssignULong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryAssignUnicodeString method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

