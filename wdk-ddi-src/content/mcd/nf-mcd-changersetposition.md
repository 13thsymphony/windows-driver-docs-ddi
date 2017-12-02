---
UID: NF.mcd.ChangerSetPosition
title: ChangerSetPosition
author: windows-driver-content
description: ChangerSetPosition handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_POSITION.
old-location: storage\changersetposition.htm
old-project: storage
ms.assetid: cab12c57-dd2b-4453-90ed-7f8954e0fe5d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ChangerSetPosition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerSetPosition
req.alt-loc: mcd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# ChangerSetPosition function



## -description
<p><b>ChangerSetPosition</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-position.md">IOCTL_CHANGER_SET_POSITION</a>. </p>


## -syntax

````
NTSTATUS ChangerSetPosition(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters
<dl>

### -param DeviceObject [in]

<dd>
<p>Pointer to the device object that represents the changer. </p>
</dd>

### -param Irp [in]

<dd>
<p>Pointer to the IRP. </p>
</dd>
</dl>

## -returns
<p>If the changer supports setting the position of the transport element, <b>ChangerSetPosition</b> returns the status returned by the system port driver, or one of the following values:
      </p>

<p>STATUS_SUCCESS</p>

<p>STATUS_INFO_LENGTH_MISMATCH</p>

<p>STATUS_INVALID_PARAMETER</p>

<p>STATUS_INSUFFICIENT_RESOURCES</p>

<p>If the changer does not support setting the position of the transport element, ChangerSetPosition returns STATUS_INVALID_DEVICE_REQUEST.</p>

## -remarks
<p>This routine is required.</p>

<p><b>ChangerSetPosition</b> sets the changer's robotic transport mechanism to the specified destination, typically to optimize moving or exchanging media by first positioning the transport.</p>

<p>The CHANGER_POSITION_TO_ELEMENT flag in <b>Features0</b> of <a href="..\ntddchgr\ns-ntddchgr--get-changer-parameters.md">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports this functionality.</p>

<p>The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerSetPosition</b>. <i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="..\ntddchgr\ns-ntddchgr--changer-set-position.md">CHANGER_SET_POSITION</a> structure as an input parameter that indicates the transport element and the destination to set. </p>

<p><b>ChangerSetPosition</b> first verifies that the transport and destination element addresses are valid and converts zero-based element addresses to device-specific addresses. It then builds an SRB with a CDB to position the element and sends it to the system port driver.</p>

<p><b>ChangerSetPosition</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_SET_POSITION) before returning to the changer class driver. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mcd.h (include Mcd.h or Ntddchgr.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddchgr\ns-ntddchgr--changer-element.md">CHANGER_ELEMENT</a>
</dt>
<dt>
<a href="..\ntddchgr\ns-ntddchgr--changer-set-position.md">CHANGER_SET_POSITION</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-position.md">, IOCTL_CHANGER_SET_POSITION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerSetPosition function%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
