---
UID: NF:wdfcommonbuffer.WdfCommonBufferCreate
title: WdfCommonBufferCreate function
author: windows-driver-content
description: The WdfCommonBufferCreate method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously.
old-location: wdf\wdfcommonbuffercreate.htm
old-project: wdf
ms.assetid: 05e092fe-fa70-47b7-af8d-c6e27847a6ac
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCommonBufferCreate, WdfCommonBufferCreate method, wdfcommonbuffer/WdfCommonBufferCreate, DFCommonBufferObjectRef_2ef72eb3-fa4c-40f8-aa73-54bb5dcb9e0c.xml, kmdf.wdfcommonbuffercreate, wdf.wdfcommonbuffercreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcommonbuffer.h
req.include-header: WdfCommonBuffer.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfCommonBufferCreate
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO"
req.product: Windows 10 or later.
---


# WdfCommonBufferCreate function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfCommonBufferCreate</b> method creates a memory buffer that both the driver and a direct memory access (DMA) device can access simultaneously.

## Syntax

````
NTSTATUS WdfCommonBufferCreate(
  _In_     WDFDMAENABLER          DmaEnabler,
  _In_     size_t                 Length,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_    WDFCOMMONBUFFER        *CommonBuffer
);
````

## Parameters

`DmaEnabler`

A handle to a DMA enabler object that the driver obtained by a previous call to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

`Length`

The desired size, in bytes, of the new buffer.

`Attributes`

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the common buffer object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.

`CommonBuffer`

A pointer to a WDFCOMMONBUFFER-typed variable that receives a handle to a common buffer object.


## Return Value

<b>WdfCommonBufferCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
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
The driver supplied an invalid parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate a common buffer object, or the system could not allocate a buffer.

</td>
</tr>
</table> 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfCommonBufferCreate</b> method allocates memory and maps it so that both the driver and a device can access it simultaneously for DMA operations. After your driver calls <b>WdfCommonBufferCreate</b>, the driver must:
<ul>
<li>
Call <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a> to obtain the buffer's virtual address, which the driver can use.

</li>
<li>
Call <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a> to obtain the buffer's logical address, which the device can use.

</li>
</ul>A driver typically calls <b>WdfCommonBufferCreate</b> from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. 

Before the driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, it can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a> to set a buffer alignment requirement. If the driver does not call <b>WdfDeviceSetAlignmentRequirement</b>, buffers are aligned on word boundaries. If your driver creates multiple DMA enablers, each with a different buffer alignment requirement, the driver can call <b>WdfDeviceSetAlignmentRequirement</b> before each call to <b>WdfDmaEnablerCreate</b>.

To create a common buffer that has an alignment requirement that is different from the alignment requirement that the driver specified with <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a>, the driver can call <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig.md">WdfCommonBufferCreateWithConfig</a> instead of <b>WdfCommonBufferCreate</b>.

The operating system determines whether to enable cached memory in the common buffer that is to be allocated. That decision is based on the processor architecture and device bus.


On computers with x86-based, x64-based, and Itanium-based processors, cached memory is enabled.
On computers with ARM or ARM 64-based processors, the operating system does not automatically enable cached memory for all devices. The system relies on the ACPI_CCA method for each device to determine whether the device is cache-coherent.

The DMA enabler object that the <i>DmaEnabler</i> parameter of <b>WdfCommonBufferCreate</b> specifies becomes the parent object for the new common buffer object. The driver cannot change this parent, and the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>. The framework deletes each common buffer object when it deletes the parent DMA enabler object.

For more information about common buffers, see <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfcommonbuffer.h (include WdfCommonBuffer.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffercreatewithconfig.md">WdfCommonBufferCreateWithConfig</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetalignmentrequirement.md">WdfDeviceSetAlignmentRequirement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCommonBufferCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>