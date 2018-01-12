---
UID: NI:ntddstor.IOCTL_STORAGE_PREDICT_FAILURE
title: IOCTL_STORAGE_PREDICT_FAILURE
author: windows-driver-content
description: Polls for a prediction of device failure.
old-location: storage\ioctl_storage_predict_failure.htm
old-project: storage
ms.assetid: 56e178d9-e6bb-43d4-b062-da4e699c4efc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_STORAGE_PREDICT_FAILURE
req.alt-loc: Ntddstor.h
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
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_PREDICT_FAILURE IOCTL



## -description

Polls for a prediction of device failure. This request works with the IDE disk drives that support self-monitoring analysis and reporting technology (SMART). If the drive is a SCSI drive, the class driver attempts to verify if the SCSI disk supports the equivalent IDE SMART technology by check the inquiry information on the Information Exception Control Page, X3T10/94-190 Rev 4. 

If the device supports prediction failure, the disk class driver queries the device for failure prediction status and reports the results. If the disk class driver assigns a nonzero value to the <b>PredictFailure</b> member of <a href="..\ntddstor\ns-ntddstor-_storage_predict_failure.md">STORAGE_PREDICT_FAILURE</a> in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, the disk has bad sectors and is predicting a failure. The storage stack returns 512 bytes of vendor-specific information about the failure prediction in the <b>VendorSpecific</b> member of STORAGE_PREDICT_FAILURE. 

If the <b>PredictFailure</b> member contains a value of zero, the disk is not predicting a failure.

If the device does not support failure prediction, IOCTL_STORAGE_PREDICT_FAILURE fails with a status of STATUS_INVALID_DEVICE_REQUEST, and the data in the output buffer is undefined

Other means of checking for disk failure include monitoring the event log and registering to receive a WMI event with WMI_STORAGE_PREDICT_FAILURE_EVENT_GUID. 



Polls for a prediction of device failure. This request works with the IDE disk drives that support self-monitoring analysis and reporting technology (SMART). If the drive is a SCSI drive, the class driver attempts to verify if the SCSI disk supports the equivalent IDE SMART technology by check the inquiry information on the Information Exception Control Page, X3T10/94-190 Rev 4. 

If the device supports prediction failure, the disk class driver queries the device for failure prediction status and reports the results. If the disk class driver assigns a nonzero value to the <b>PredictFailure</b> member of <a href="..\ntddstor\ns-ntddstor-_storage_predict_failure.md">STORAGE_PREDICT_FAILURE</a> in the output buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, the disk has bad sectors and is predicting a failure. The storage stack returns 512 bytes of vendor-specific information about the failure prediction in the <b>VendorSpecific</b> member of STORAGE_PREDICT_FAILURE. 

If the <b>PredictFailure</b> member contains a value of zero, the disk is not predicting a failure.

If the device does not support failure prediction, IOCTL_STORAGE_PREDICT_FAILURE fails with a status of STATUS_INVALID_DEVICE_REQUEST, and the data in the output buffer is undefined

Other means of checking for disk failure include monitoring the event log and registering to receive a WMI event with WMI_STORAGE_PREDICT_FAILURE_EVENT_GUID. 



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns a <a href="..\ntddstor\ns-ntddstor-_storage_predict_failure.md">STORAGE_PREDICT_FAILURE</a> structure containing failure prediction data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer,</b> which must be greater or equal to the <b>sizeof</b>(STORAGE_PREDICT_FAILURE). 


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ns-ntddstor-_storage_predict_failure.md">STORAGE_PREDICT_FAILURE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_PREDICT_FAILURE control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

