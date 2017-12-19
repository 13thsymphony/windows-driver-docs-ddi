---
UID: NF.wdfstring.WdfStringCreate
title: WdfStringCreate function
author: windows-driver-content
description: The WdfStringCreate method creates a framework string object and optionally assigns a specified Unicode string to the object.
old-location: wdf\wdfstringcreate.htm
old-project: wdf
ms.assetid: 491b99c6-5531-4d24-83a4-c404b58d111c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfStringCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfstring.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfStringCreate
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

# WdfStringCreate function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfStringCreate</b> method creates a framework string object and optionally assigns a specified Unicode string to the object.



## -syntax

````
NTSTATUS WdfStringCreate(
  _In_opt_ PCUNICODE_STRING       UnicodeString,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES StringAttributes,
  _Out_    WDFSTRING              *String
);
````


## -parameters

### -param UnicodeString [in, optional]

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that contains a Unicode string constant. The framework copies the string to the new framework string object. This pointer is optional and can be <b>NULL</b>.


### -param StringAttributes [in, optional]

A pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new string object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param String [out]

A pointer to a location that receives a handle to the new string object.


## -returns
<b>WdfStringCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
<a href="wdf.wdfstringcreate">WdfStringCreate</a> was not called at IRQL = PASSIVE_LEVEL. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A string object could not be allocated.

 

For a list of other return values that the <b>WdfStringCreate</b> method might return, see <a href="wdf.framework_object_creation_errors">Framework Object Creation Errors</a>.



This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The default parent for framework string objects is the driver's framework driver object. However, unless the string is associated with the driver, your driver should set the <b>ParentObject</b> member of the <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure to an object that represents the string's scope. Typically, strings are device-specific and their parent object should be a framework device object.

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework string object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework string objects, see <a href="wdf.using_string_objects">Using String Objects</a>.

The following code example initializes a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure and then creates a framework string object.


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
<dt>Wdfstring.h (include Wdf.h)</dt>
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
<a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="wdf.wdfstringgetunicodestring">WdfStringGetUnicodeString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfStringCreate method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

