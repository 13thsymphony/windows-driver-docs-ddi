---
UID: NF.wdfresource.WdfIoResourceListAppendDescriptor
title: WdfIoResourceListAppendDescriptor function
author: windows-driver-content
description: The WdfIoResourceListAppendDescriptor method adds a resource descriptor to the end of a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistappenddescriptor.htm
old-project: wdf
ms.assetid: da9213c1-e519-44ad-aabf-fd05bdbd2079
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfIoResourceListAppendDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfIoResourceListAppendDescriptor
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfIoResourceListAppendDescriptor function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.



## -syntax

````
NTSTATUS WdfIoResourceListAppendDescriptor(
  _In_ WDFIORESLIST            ResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor
);
````


## -parameters

### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="kernel.io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns
<b>WdfIoResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver was not allowed to add descriptors to the logical configuration that the <i>ResourceList</i> parameter specified.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The framework could not allocate space to store the descriptor.

 

A system bug check occurs if the driver supplies an invalid object handle.


## -remarks
The framework copies the contents of the <a href="kernel.io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that the <i>Descriptor</i> parameter points to into internal storage, so the driver routine that calls <b>WdfIoResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfIoResourceListAppendDescriptor</b>, the driver can reuse the <b>IO_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource requirements lists and logical configurations, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example creates an empty logical configuration and adds it to a resource requirements list. Then, the example initializes a resource descriptor and adds the descriptor to the logical configuration.


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
Header

</th>
<td width="70%">
<dl>
<dt>Wdfresource.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

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
<a href="kernel.io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="wdf.wdfioresourcelistcreate">WdfIoResourceListCreate</a>
</dt>
<dt>
<a href="wdf.wdfioresourcelistinsertdescriptor">WdfIoResourceListInsertDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListAppendDescriptor method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

