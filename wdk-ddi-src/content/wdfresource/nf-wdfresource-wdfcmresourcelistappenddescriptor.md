---
UID: NF:wdfresource.WdfCmResourceListAppendDescriptor
title: WdfCmResourceListAppendDescriptor function
author: windows-driver-content
description: The WdfCmResourceListAppendDescriptor method adds a resource descriptor to the end of a specified resource list.
old-location: wdf\wdfcmresourcelistappenddescriptor.htm
old-project: wdf
ms.assetid: 1a0f8ea5-9b1f-4301-b96d-aa37b80b4ce2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_13d42471-baa5-4985-a5fa-70336f2be352.xml, WdfCmResourceListAppendDescriptor, WdfCmResourceListAppendDescriptor method, kmdf.wdfcmresourcelistappenddescriptor, wdf.wdfcmresourcelistappenddescriptor, wdfresource/WdfCmResourceListAppendDescriptor
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfCmResourceListAppendDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---


# WdfCmResourceListAppendDescriptor function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCmResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a specified resource list.

## Syntax

````
NTSTATUS WdfCmResourceListAppendDescriptor(
  _In_ WDFCMRESLIST                    List,
  _In_ PCM_PARTIAL_RESOURCE_DESCRIPTOR Descriptor
);
````

## Parameters

`List`

A handle to a framework resource-list object that represents a list of hardware resources for a device.

`Descriptor`

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## Return Value

<b>WdfCmResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The driver was not allowed to add descriptors to the logical configuration that the <i>List</i> parameter specified. For example, the driver could not modify the logical configuration that its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function received.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor that the <i>Descriptor</i> parameter specified.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.

## Remarks

The framework copies the contents of the <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfCmResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfCmResourceListAppendDescriptor</b> it can reuse the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example adds a resource descriptor to the end of the resource list that an <a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a> callback function receives. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
PdoEvtDeviceResourcesQuery(
    IN WDFDEVICE  Device,
    IN WDFCMRESLIST  Resources
    )
{
    CM_PARTIAL_RESOURCE_DESCRIPTOR newDescriptor;
...
    newDescriptor.Type = CmResourceTypePort;
    newDescriptor.ShareDisposition = CmResourceShareDeviceExclusive;
    newDescriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
    newDescriptor.u.Port.Length = 1;
    newDescriptor.u.Port.Start = 0;

    status = WdfCmResourceListAppendDescriptor(
                                               Resources,
                                               &amp;newDescriptor
                                               );
...

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

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>



<a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>



<a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistinsertdescriptor.md">WdfCmResourceListInsertDescriptor</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>