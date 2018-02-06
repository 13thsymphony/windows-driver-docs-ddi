---
UID: NC:wmilib.WMI_QUERY_DATABLOCK_CALLBACK
title: WMI_QUERY_DATABLOCK_CALLBACK
author: windows-driver-content
description: The DpWmiQueryDataBlock routine returns either a single instance or all instances of a data block. This routine is required.
old-location: kernel\dpwmiquerydatablock.htm
old-project: kernel
ms.assetid: c8996367-9ac5-4725-93ff-f13a334fbc5a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.dpwmiquerydatablock, DpWmiQueryDataBlock, DpWmiQueryDataBlock callback function [Kernel-Mode Driver Architecture], DpWmiQueryDataBlock, WMI_QUERY_DATABLOCK_CALLBACK, WMI_QUERY_DATABLOCK_CALLBACK, wmilib/DpWmiQueryDataBlock, k903_9a558594-4fe5-4e18-823a-8b487e1770d9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wmilib.h
apiname:
-	DpWmiQueryDataBlock
product: Windows
targetos: Windows
req.typenames: "*PWMI_CHANGER_PROBLEM_DEVICE_ERROR, WMI_CHANGER_PROBLEM_DEVICE_ERROR"
req.product: Windows 10 or later.
---


# WMI_QUERY_DATABLOCK_CALLBACK callback function
The <i>DpWmiQueryDataBlock</i> routine returns either a single instance or all instances of a data block. This routine is required.

## Syntax

```
WMI_QUERY_DATABLOCK_CALLBACK WmiQueryDatablockCallback;

NTSTATUS WmiQueryDatablockCallback(
  PDEVICE_OBJECT DeviceObject,
  PIRP Irp,
  ULONG GuidIndex,
  ULONG InstanceIndex,
  ULONG InstanceCount,
  PULONG InstanceLengthArray,
  ULONG BufferAvail,
  PUCHAR Buffer
)
{...}
```

## Parameters

`DeviceObject`

Pointer to the driver's WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.

`Irp`

Pointer to the IRP.

`GuidIndex`

Specifies the data block by supplying a zero-based index into the list of GUIDs that the driver provided in the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure it passed to <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>.

`InstanceIndex`

If <i>DpWmiQueryDataBlock</i> is called in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request, <i>InstanceIndex </i>specifies a zero-based index that indicates the instance of the specified data block to be queried. If <i>DpWmiQueryDataBlock</i> is called in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a> request, <i>InstanceIndex </i>is zero.

`InstanceCount`

If <i>DpWmiQueryDataBlock</i> is called in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request, <i>InstanceCount </i>is 1. If <i>DpWmiQueryDataBlock</i> is called in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a> request, <i>InstanceCount </i>is the number of instances to be returned.

`InstanceLengthArray`

Pointer to a caller-supplied, <i>InstanceCount</i>-sized array of ULONG elements. The driver fills in each array element to indicate the length of each instance that was returned.  If <i>BufferAvail</i> is zero, <i>InstanceLengthArray</i> is <b>NULL</b>.

`BufferAvail`

Specifies the maximum number of bytes that are available to receive data in the buffer at <i>Buffer</i>. If this value is zero, the caller is requesting that the driver specify the required buffer size in its call to <a href="..\wmilib\nf-wmilib-wmicompleterequest.md">WmiCompleteRequest</a>. See the Remarks section for more information.

`Buffer`

Pointer to the buffer to receive instance data. If the buffer is large enough to receive all of the data, the driver writes the instance data to the buffer with each instance aligned on an 8-byte boundary. If the buffer is too small to receive all of the data, the driver calls <a href="..\wmilib\nf-wmilib-wmicompleterequest.md">WmiCompleteRequest</a> with <i>BufferUsed</i> set to the size required.


## Return Value

<i>DpWmiQueryDataBlock</i> returns STATUS_SUCCESS or an error status such as the following:

If the driver cannot complete the request immediately, it can return STATUS_PENDING.

## Remarks

WMI calls a driver's <i>DpWmiQueryDataBlock</i> routine after the driver calls <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a> request. The driver must place the address of its <i>DpWmiQueryDataBlock</i> routine in the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure that it passes to <b>WmiSystemControl</b>.

The driver is responsible for validating all input arguments. Specifically, the driver must do the following:
<ul>
<li>
Verify that the <i>GuidIndex</i> value is between zero and GuidCount-1, based on the <b>GuidCount</b> member of the <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure.

</li>
<li>
Verify that the driver has not flagged the specified data block for removal. If the driver recently specified the WMIREG_FLAG_REMOVE_GUID flag in a <a href="..\wmilib\ns-wmilib-_wmiguidreginfo.md">WMIGUIDREGINFO</a> structure that is contained in a <b>WMILIB_CONTEXT</b> structure, it is possible for a query to arrive before the removal occurs.

</li>
<li>
Verify that the <i>InstanceIndex</i> and <i>InstanceCount</i> values, together, specify a number of data block instances that is within the range supported by the driver for the data block. If <i>InstanceIndex</i> is nonzero, <i>InstanceCount</i> must be 1. If <i>InstanceIndex</i> is 0, <i>InstanceCount</i> must not be greater than the number of instances supported.

</li>
<li>
Verify that the buffer described by <i>Buffer</i> and <i>BufferAvail</i> is large enough to hold all requested instances of the data block. Each instance must begin on an 8-byte boundary, and additional padding might exist between data items within each instance.

</li>
</ul>After writing instance data to the buffer, the driver calls <a href="..\wmilib\nf-wmilib-wmicompleterequest.md">WmiCompleteRequest</a> to complete the request. If the buffer described by <i>Buffer</i> and <i>BufferAvail</i> is zero, or is too small to receive all the requested data, the call to <b>WmiCompleteRequest</b> must specify STATUS_BUFFER_TOO_SMALL for the <i>Status</i> parameter and the required buffer size for the <i>BufferUsed</i> parameter.

This routine can be pageable.

For more information about implementing this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540741">Calling WmiSystemControl to Handle WMI IRPs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wmilib.h (include Wmilib.h) |
| **IRQL** | Called at PASSIVE_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a>

<a href="..\wmilib\nf-wmilib-wmicompleterequest.md">WmiCompleteRequest</a>

<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>

<a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMI_QUERY_DATABLOCK_CALLBACK callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>