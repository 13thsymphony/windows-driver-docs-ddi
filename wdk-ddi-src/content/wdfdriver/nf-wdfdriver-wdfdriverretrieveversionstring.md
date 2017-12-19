---
UID: NF.wdfdriver.WdfDriverRetrieveVersionString
title: WdfDriverRetrieveVersionString function
author: windows-driver-content
description: The WdfDriverRetrieveVersionString method retrieves a Unicode string that identifies the version of the Kernel-Mode Driver Framework that the driver is running with.
old-location: wdf\wdfdriverretrieveversionstring.htm
old-project: wdf
ms.assetid: cbea7a3c-faae-4779-9a27-6c2b60f2b35c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDriverRetrieveVersionString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDriverRetrieveVersionString
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

# WdfDriverRetrieveVersionString function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDriverRetrieveVersionString</b> method retrieves a Unicode string that identifies the version of the Kernel-Mode Driver Framework that the driver is running with.



## -syntax

````
NTSTATUS WdfDriverRetrieveVersionString(
  _In_ WDFDRIVER Driver,
  _In_ WDFSTRING String
);
````


## -parameters

### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="wdf.wdfdrivercreate">WdfDriverCreate</a> or <a href="wdf.wdfgetdriver">WdfGetDriver</a>.


### -param String [in]

A handle to a framework string object that the driver obtained from a previous call to <a href="wdf.wdfstringcreate">WdfStringCreate</a>. The framework assigns the version string to the string object.


## -returns
<b>WdfDriverRetrieveVersionString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The framework could not allocate a buffer for the Unicode string.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the <i>Driver</i> handle is invalid.


## -remarks
Your driver can call <b>WdfDriverRetrieveVersionString</b> if you want to display a string that identifies the framework library's version. The string's format might change from one version to another, so the driver must not attempt to interpret the string's format or content.

For more information about library versions, see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.

The following code example creates a string object, assigns the version string to the object, and displays the string if a debugger is running.


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
<dt>Wdfdriver.h (include Wdf.h)</dt>
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
<a href="wdf.wdfdrivercreate">WdfDriverCreate</a>
</dt>
<dt>
<a href="wdf.wdfdriverisversionavailable">WdfDriverIsVersionAvailable</a>
</dt>
<dt>
<a href="wdf.wdfgetdriver">WdfGetDriver</a>
</dt>
<dt>
<a href="wdf.wdfobjectdelete">WdfObjectDelete</a>
</dt>
<dt>
<a href="wdf.wdfstringcreate">WdfStringCreate</a>
</dt>
<dt>
<a href="wdf.wdfstringgetunicodestring">WdfStringGetUnicodeString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverRetrieveVersionString method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

