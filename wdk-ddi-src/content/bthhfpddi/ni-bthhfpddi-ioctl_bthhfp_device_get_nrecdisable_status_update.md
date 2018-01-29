---
UID : NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
title : IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
author : windows-driver-content
description : The IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL Gets noise reduction / echo cancellation (NREC) Disable status updates from the remote Bluetooth device.
old-location : audio\ioctl_bthhfp_device_get_nrecdisable_status_update.htm
old-project : audio
ms.assetid : 2AA3098D-B3CA-4515-AC53-C78E2060D798
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.ioctl_bthhfp_device_get_nrecdisable_status_update, IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE control code [Audio Devices], IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthhfpddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PHFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION"
---

# IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE IOCTL
The <b>IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE</b> 
   IOCTL Gets noise reduction / echo cancellation (NREC) Disable status updates from the remote Bluetooth device.

This IOCTL is available in Windows 8.1 and later operating systems.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A BOOL that is set to TRUE to request an immediate update. Otherwise, set this to FALSE.

### Input Buffer Length
The size of a BOOL.

### Output Buffer
A BOOL that indicates the new NREC Disable status. See <b>Remarks</b> for additional information.

### Output Buffer Length
The size of a BOOL.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If a request is already pending, then the new request fails with an error code of STATUS_INVALID_DEVICE_REQUEST.

## Remarks
When the NREC Disable status is TRUE, it shows that the remote Bluetooth device has disabled  any system-based NREC processing, implying that the remote device has enabled its own NREC signal processing. In this scenario, the audio driver should disable any of its own NREC processing, regardless of whether the processing is being done within the driver code itself, in its digital signal processing (DSP) module, or its audio processing object (APO). 

Additionally, in this scenario where NREC is enabled in the remote Bluetooth device, the driver’s APO should return "NREC" in its list of effects, to let applications know that NREC processing is enabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | bthhfpddi.h |
| **IRQL** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_NRECDISABLE_STATUS_UPDATE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>