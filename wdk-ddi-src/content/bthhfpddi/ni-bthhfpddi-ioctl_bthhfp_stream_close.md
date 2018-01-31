---
UID : NI:bthhfpddi.IOCTL_BTHHFP_STREAM_CLOSE
title : IOCTL_BTHHFP_STREAM_CLOSE
author : windows-driver-content
description : The IOCTL_BTHHFP_STREAM_CLOSE IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.
old-location : audio\ioctl_bthhfp_stream_close.htm
old-project : audio
ms.assetid : 689296FA-E28A-4F9C-8E09-2CAC8A189808
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.ioctl_bthhfp_stream_close, IOCTL_BTHHFP_STREAM_CLOSE control code [Audio Devices], IOCTL_BTHHFP_STREAM_CLOSE, bthhfpddi/IOCTL_BTHHFP_STREAM_CLOSE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthhfpddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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
req.typenames : HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_STREAM_CLOSE IOCTL
The <b>IOCTL_BTHHFP_STREAM_CLOSE</b> 
   IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
N/A

### Input Buffer Length
N/A

### Output Buffer
N/A

### Output Buffer Length
N/A

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
N/A

## Remarks
The request completes immediately.

The audio driver starts this request when the KS pin transitions to the KSSTATE_STOP state, and should not finish the pin state transition until this request completes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | bthhfpddi.h |
| **IRQL** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_STREAM_CLOSE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>