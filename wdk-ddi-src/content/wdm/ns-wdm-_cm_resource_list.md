---
UID: NS.WDM._CM_RESOURCE_LIST
title: _CM_RESOURCE_LIST
author: windows-driver-content
description: The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device.
old-location: kernel\cm_resource_list.htm
old-project: kernel
ms.assetid: 01f31255-a4f7-4a16-9238-a7391bb850d1
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _CM_RESOURCE_LIST, CM_RESOURCE_LIST, PCM_RESOURCE_LIST, *PCM_RESOURCE_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CM_RESOURCE_LIST
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _CM_RESOURCE_LIST structure



## -description
The <b>CM_RESOURCE_LIST</b> structure specifies all of the system hardware resources assigned to a device.



## -syntax

````
typedef struct _CM_RESOURCE_LIST {
  ULONG                       Count;
  CM_FULL_RESOURCE_DESCRIPTOR List[1];
} CM_RESOURCE_LIST, *PCM_RESOURCE_LIST;
````


## -struct-fields

### -field Count

The number of full resource descriptors that are specified by this <b>CM_RESOURCE_LIST</b> structure. The <b>List</b> member is the header for the first full resource descriptor. For WDM drivers, <b>Count</b> is always 1.


### -field List

The <a href="kernel.cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a> structure that serves as the header for the first full resource descriptor. If the <b>CM_RESOURCE_LIST</b> structure contains more than one full resource descriptor, the second full resource descriptor immediately follows the first in memory, and so on. The size of each full resource descriptor depends on the length of the <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> array that it contains. For more information, see the following Remarks section.


## -remarks
This structure describes the assignment of hardware resources to a device. An <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP uses this structure to specify the resources that the Plug and Play manager assigns to a device. Drivers for legacy devices use this structure to pass their resource requirements to the <a href="kernel.ioreportresourcefordetection">IoReportResourceForDetection</a> routine. For more information about hardware resource allocation, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547012">Hardware Resources</a>.

The <b>CM_RESOURCE_LIST</b> structure is a header for a larger data structure, of variable size, that contains one or more full resource descriptors. All of the data in this larger structure occupies a contiguous block of memory. Each full resource descriptor occupies a subblock within the larger block.

A full resource descriptor begins with a <a href="kernel.cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a> structure, which serves as a header for an array of <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structures. The length of this array determines the size of the full resource descriptor. The last member in the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure is a <a href="kernel.cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a> structure that contains, as its last member, the first element in this array. If the array contains more than one element, the remaining elements immediately follow, in memory, the end of the <b>CM_PARTIAL_RESOURCE_LIST</b> structure, which is also the end of the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure.

Driver code can use pointer arithmetic to step from one full resource descriptor to the next. For example, if a parameter named <i>list</i> is a pointer to the <b>CM_FULL_RESOURCE_DESCRIPTOR</b> structure at the start of one full resource descriptor, <i>list</i> can be updated to point to the start of the next full resource descriptor as follows:

In this example, <code>list-&gt;PartialResourceList.PartialDescriptors</code> is a pointer to the start of the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> array, and <code>list-&gt;PartialResourceList.Count</code> is the number of elements in the array. For more information about the <b>PartialDescriptors</b> and <b>Count</b> members, see <a href="kernel.cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a>.

All PnP drivers must handle <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRPs. Typically, a driver's handler for this IRP walks the lists of assigned resources that are pointed to by the <b>Parameters.StartDevice.AllocatedResources</b> and <b>Parameters.StartDevice.AllocatedResourcesTranslated</b> members of the <a href="kernel.io_stack_location">IO_STACK_LOCATION</a> structure in the IRP. The following code example contains a function—named GetAssignedResources—that is called in the handler to walk each list. This function verifies that the required resources are specified in the list, and configures the device to use the resources.

The GetAssignedResources function returns <b>TRUE</b> if it succeeds. Otherwise, it returns <b>FALSE</b> (probably from the <b>switch</b> statement, although the details are omitted to simplify the code example).


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.cm_resource_list">CM_RESOURCE_LIST</a>
</dt>
<dt>
<a href="kernel.cm_full_resource_descriptor">CM_FULL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="kernel.cm_partial_resource_list">CM_PARTIAL_RESOURCE_LIST</a>
</dt>
<dt>
<a href="kernel.cm_floppy_device_data">CM_FLOPPY_DEVICE_DATA</a>
</dt>
<dt>
<a href="kernel.cm_keyboard_device_data">CM_KEYBOARD_DEVICE_DATA</a>
</dt>
<dt>
<a href="kernel.cm_scsi_device_data">CM_SCSI_DEVICE_DATA</a>
</dt>
<dt>
<a href="kernel.cm_serial_device_data">CM_SERIAL_DEVICE_DATA</a>
</dt>
<dt>
<a href="kernel.ioconnectinterrupt">IoConnectInterrupt</a>
</dt>
<dt>
<a href="kernel.iogetdeviceproperty">IoGetDeviceProperty</a>
</dt>
<dt>
<a href="kernel.ioreportresourcefordetection">IoReportResourceForDetection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_RESOURCE_LIST structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

