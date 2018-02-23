---
UID: NF:wdfresource.WdfIoResourceListInsertDescriptor
title: WdfIoResourceListInsertDescriptor function
author: windows-driver-content
description: The WdfIoResourceListInsertDescriptor method inserts a resource descriptor into a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistinsertdescriptor.htm
old-project: wdf
ms.assetid: 604182ea-3712-4670-bab8-edc3cb2fcd06
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfIoResourceListInsertDescriptor method, kmdf.wdfioresourcelistinsertdescriptor, wdf.wdfioresourcelistinsertdescriptor, wdfresource/WdfIoResourceListInsertDescriptor, WdfIoResourceListInsertDescriptor, DFResourceObjectRef_6f8fc17d-c5db-47fa-854a-5536dfc11705.xml
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoResourceListInsertDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WdfIoResourceListInsertDescriptor function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListInsertDescriptor</b> method inserts a resource descriptor into a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.

## Syntax

````
NTSTATUS WdfIoResourceListInsertDescriptor(
  _In_ WDFIORESLIST            ResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor,
  _In_ ULONG                   Index
);
````

## Parameters

`ResourceList`

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.

`Descriptor`

A pointer to an <a href="..\miniport\ns-miniport-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.

`Index`

A zero-based value that is used as an index into the set of resource descriptors that are already in the logical configuration that <i>ResourceList</i> specifies. To add a resource descriptor to the end of the logical configuration, specify WDF_INSERT_AT_END or the return value from <a href="..\wdfresource\nf-wdfresource-wdfioresourcelistgetcount.md">WdfIoResourceListGetCount</a>.


## Return Value

<b>WdfIoResourceListInsertDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver was not allowed to add descriptors to the logical configuration.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ARRAY_BOUNDS_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The value that the <i>Index</i> parameter specifies was too large.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfIoResourceListInsertDescriptor</b> method inserts the resource descriptor that the <i>Descriptor</i> parameter points to into the logical configuration that the <i>ResourceList</i> parameter specifies, in front of the resource descriptor that the <i>Index</i> value identifies. 

To add a resource descriptor to the end of a logical configuration, specify WDF_INSERT_AT_END or the return value from <a href="..\wdfresource\nf-wdfresource-wdfioresourcelistgetcount.md">WdfIoResourceListGetCount</a> for the <i>Index</i> value. Alternatively, use the <a href="..\wdfresource\nf-wdfresource-wdfioresourcelistappenddescriptor.md">WdfIoResourceListAppendDescriptor</a> method.

The framework copies the contents of the <a href="..\miniport\ns-miniport-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfIoResourceListInsertDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfIoResourceListInsertDescriptor</b>, the driver can reuse the <b>IO_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a resource descriptor and adds the descriptor to the end of a logical configuration.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_RESOURCE_DESCRIPTOR descriptor;

RtlZeroMemory(&amp;descriptor, sizeof(descriptor));

descriptor.Option = 0;
descriptor.Type = CmResourceTypePort;
descriptor.ShareDisposition = CmResourceShareDeviceExclusive;
descriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
descriptor.u.Port.Length = 1;
descriptor.u.Port.Alignment = 0x01;
descriptor.u.Port.MinimumAddress.QuadPart = 0;
descriptor.u.Port.MaximumAddress.QuadPart = 0xFFFF;

status = WdfIoResourceListInsertDescriptor(
                                           logConfig,
                                           &amp;descriptor,
                                           WDF_INSERT_AT_END
                                           );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfresource.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistappenddescriptor.md">WdfIoResourceListAppendDescriptor</a>



<a href="..\miniport\ns-miniport-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListInsertDescriptor method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>