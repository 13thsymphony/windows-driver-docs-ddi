---
UID: NF.wdfresource.WdfCmResourceListGetDescriptor
title: WdfCmResourceListGetDescriptor
author: windows-driver-content
description: The WdfCmResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a specified resource list.
old-location: wdf\wdfcmresourcelistgetdescriptor.htm
old-project: wdf
ms.assetid: 5aa96fed-83ca-417e-876d-a734be6f27dd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfCmResourceListGetDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfCmResourceListGetDescriptor
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
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfCmResourceListGetDescriptor function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfCmResourceListGetDescriptor</b> method returns a pointer to a resource descriptor that is contained in a specified resource list.</p>


## -syntax

````
PCM_PARTIAL_RESOURCE_DESCRIPTOR WdfCmResourceListGetDescriptor(
  _In_ WDFCMRESLIST List,
  _In_ ULONG        Index
);
````


## -parameters
<dl>

### -param List [in]

<dd>
<p>A handle to a framework resource-list object that represents a list of hardware resources for a device.</p>
</dd>

### -param Index [in]

<dd>
<p>A zero-based value that is used as an index into the logical configuration that <i>List</i> specifies.</p>
</dd>
</dl>

## -returns
<p><b>WdfCmResourceListGetDescriptor</b> returns a pointer to the <a href="..\wdm\ns-wdm--cm-partial-resource-descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the hardware resource that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.</p>

<p>A system bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>Your driver cannot modify the resource descriptor that <b>WdfCmResourceListGetDescriptor</b> retrieves. </p>

<p>For more information about resource lists, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.</p>

<p>For a code example that uses <b>WdfCmResourceListGetDescriptor</b>, see <a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistgetcount.md">WdfCmResourceListGetCount</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfresource.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--cm-partial-resource-descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCmResourceListGetDescriptor method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
