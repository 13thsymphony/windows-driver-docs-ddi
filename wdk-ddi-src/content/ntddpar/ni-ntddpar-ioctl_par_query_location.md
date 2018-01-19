---
UID : NI:ntddpar.IOCTL_PAR_QUERY_LOCATION
title : IOCTL_PAR_QUERY_LOCATION
author : windows-driver-content
description : The IOCTL_PAR_QUERY_LOCATION request returns the &#0034;LPTn&#0034; or &#0034;LPTn.m&#0034; symbolic link name associated with a parallel device.
old-location : parports\ioctl_par_query_location.htm
old-project : parports
ms.assetid : a46b1f7f-d624-48f3-a2cf-6828908ba3c1
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _OFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddpar.h
req.include-header : Ntddpar.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_PAR_QUERY_LOCATION
req.alt-loc : ntddpar.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_QUERY_LOCATION IOCTL
The IOCTL_PAR_QUERY_LOCATION request returns the "LPT<i>n</i>" or "LPT<i>n.m</i>" symbolic link name associated with a parallel device. This request is only supported by Windows XP and later.



<dl>
<dt><a id="For_more_information__see_Device_Stacks_for_ParallelPorts_and_Devices_and_Parallel_Device_Interfaces__Internal_Names__and_Symbolic_Links."></a><a id="for_more_information__see_device_stacks_for_parallelports_and_devices_and_parallel_device_interfaces__internal_names__and_symbolic_links."></a><a id="FOR_MORE_INFORMATION__SEE_DEVICE_STACKS_FOR_PARALLELPORTS_AND_DEVICES_AND_PARALLEL_DEVICE_INTERFACES__INTERNAL_NAMES__AND_SYMBOLIC_LINKS."></a>For more information, see <a href="https://msdn.microsoft.com/80222ed9-f900-4d97-b459-2d8ca780e1d1">Device Stacks for ParallelPorts and Devices</a> and <a href="https://msdn.microsoft.com/859e20bb-e411-4572-a393-a6faf534cf15">Parallel Device Interfaces, Internal Names, and Symbolic Links</a>.</dt>
<dd></dd>
</dl>


The IOCTL_PAR_QUERY_LOCATION request returns the "LPT<i>n</i>" or "LPT<i>n.m</i>" symbolic link name associated with a parallel device. This request is only supported by Windows XP and later.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The client sets the <b>AssociatedIrp.SystemBuffer</b> member to a pointer to a character buffer for the location information.

### Input Buffer Length
The length of the character buffer.

### Output Buffer
The parallel port bus driver outputs the location information in the buffer pointed to by <b>AssociatedIrp.SystemBuffer</b> as a <b>NULL</b>-terminated character string.

### Output Buffer Length
The client sets the <b>Parameters.DeviceIoControl.OutputBufferLength </b>member to the length of the output buffer that the system-supplied bus driver for parallel ports uses to output the device location information.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
If the request succeeds, the <b>Information</b> member is set to the length, in bytes, of the symbolic link name plus the <b>NULL</b> terminator. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:



The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than size, in bytes, of the location information and the <b>NULL</b> terminator.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddpar.h (include Ntddpar.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_QUERY_LOCATION control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>