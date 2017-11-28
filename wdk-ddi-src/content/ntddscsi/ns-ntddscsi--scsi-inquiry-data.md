---
UID: NS.ntddscsi._SCSI_INQUIRY_DATA
title: SCSI_INQUIRY_DATA
author: windows-driver-content
description: The SCSI_INQUIRY_DATA structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_inquiry_data.htm
old-project: storage
ms.assetid: f62c35dd-791d-4c21-9836-308cc5fb102b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SCSI_INQUIRY_DATA, SCSI_INQUIRY_DATA, *PSCSI_INQUIRY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_INQUIRY_DATA
req.alt-loc: ntddscsi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# SCSI_INQUIRY_DATA structure



## -description
<p>The SCSI_INQUIRY_DATA structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560509">IOCTL_SCSI_GET_INQUIRY_DATA</a> request to retrieve the SCSI inquiry data for all devices on a given SCSI bus. </p>


## -syntax

````
typedef struct _SCSI_INQUIRY_DATA {
  UCHAR   PathId;
  UCHAR   TargetId;
  UCHAR   Lun;
  BOOLEAN DeviceClaimed;
  ULONG   InquiryDataLength;
  ULONG   NextInquiryDataOffset;
  UCHAR   InquiryData[1];
} SCSI_INQUIRY_DATA, *PSCSI_INQUIRY_DATA;
````


## -struct-fields
<dl>

### -field <b>PathId</b>

<dd>
<p>Indicates the number of the bus the device is located on.</p>
</dd>

### -field <b>TargetId</b>

<dd>
<p>Indicates the number of the device on the bus. </p>
</dd>

### -field <b>Lun</b>

<dd>
<p>Indicates the logical unit number of the logical unit on the target device. </p>
</dd>

### -field <b>DeviceClaimed</b>

<dd>
<p>When <b>TRUE</b>, indicates that the device has been claimed by a class driver. </p>
</dd>

### -field <b>InquiryDataLength</b>

<dd>
<p>Indicates the length in bytes of inquiry data. </p>
</dd>

### -field <b>NextInquiryDataOffset</b>

<dd>
<p>Contains an offset to the inquiry data for the next logical unit on the target device. </p>
</dd>

### -field <b>InquiryData</b>

<dd>
<p>Pointer to buffer containing the inquiry data for the logical unit. </p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560509">IOCTL_SCSI_GET_INQUIRY_DATA</a> request retrieves inquiry data for all devices associated with a specified adapter. An adapter can potentially have multiple buses. The <b>PathId</b> member identifies the bus. Each bus can have multiple target devices. The <b>TargetId</b> member identifies the target device, and each target device can have multiple logical units. The <b>Lun</b> member identifies the logical unit. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h (include Ntddscsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560509">IOCTL_SCSI_GET_INQUIRY_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565304">SCSI_BUS_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564949">SCSI_ADAPTER_BUS_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_INQUIRY_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
