---
UID: NF:wdfresource.WdfCmResourceListAppendDescriptor
title: WdfCmResourceListAppendDescriptor function
author: windows-driver-content
description: The WdfCmResourceListAppendDescriptor method adds a resource descriptor to the end of a specified resource list.
old-location: wdf\wdfcmresourcelistappenddescriptor.htm
old-project: wdf
ms.assetid: 1a0f8ea5-9b1f-4301-b96d-aa37b80b4ce2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCmResourceListAppendDescriptor
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
req.alt-api: WdfCmResourceListAppendDescriptor
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
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfCmResourceListAppendDescriptor function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCmResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a specified resource list.



## -syntax

````
NTSTATUS WdfCmResourceListAppendDescriptor(
  _In_ WDFCMRESLIST                    List,
  _In_ PCM_PARTIAL_RESOURCE_DESCRIPTOR Descriptor
);
````


## -parameters

### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Descriptor [in]

A pointer to a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns
<b>WdfCmResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was specified.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The driver was not allowed to add descriptors to the logical configuration that the <i>List</i> parameter specified. For example, the driver could not modify the logical configuration that its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function received.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The framework could not allocate space to store the descriptor that the <i>Descriptor</i> parameter specified.

 

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks
The framework copies the contents of the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfCmResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfCmResourceListAppendDescriptor</b> it can reuse the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource lists, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.

The following code example adds a resource descriptor to the end of the resource list that an <a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a> callback function receives. 


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a>
</dt>
<dt>
<a href="..\wdfresource\nf-wdfresource-wdfcmresourcelistinsertdescriptor.md">WdfCmResourceListInsertDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCmResourceListAppendDescriptor method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

