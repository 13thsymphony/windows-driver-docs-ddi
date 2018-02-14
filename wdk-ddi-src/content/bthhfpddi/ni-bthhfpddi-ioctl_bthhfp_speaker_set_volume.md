---
UID: NI:bthhfpddi.IOCTL_BTHHFP_SPEAKER_SET_VOLUME
title: IOCTL_BTHHFP_SPEAKER_SET_VOLUME
author: windows-driver-content
description: The IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL sets the volume level for the speaker of the Bluetooth device.
old-location: audio\ioctl_bthhfp_speaker_set_volume.htm
old-project: audio
ms.assetid: D08D9CEB-8A5C-41E6-AF05-2AE8719DD462
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.ioctl_bthhfp_speaker_set_volume, IOCTL_BTHHFP_SPEAKER_SET_VOLUME control code [Audio Devices], IOCTL_BTHHFP_SPEAKER_SET_VOLUME, bthhfpddi/IOCTL_BTHHFP_SPEAKER_SET_VOLUME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthhfpddi.h
apiname:
-	IOCTL_BTHHFP_SPEAKER_SET_VOLUME
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_SPEAKER_SET_VOLUME IOCTL
The <b>IOCTL_BTHHFP_SPEAKER_SET_VOLUME</b> IOCTL sets the volume level for the  
   speaker of the Bluetooth device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A LONG that represents the volume level in 1/65536 decibels.

### Input Buffer Length
The size of a LONG.

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
The audio driver sends this request when handling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> node in the KS topology of the speaker path. The request’s input parameter is the same as the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | bthhfpddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_SPEAKER_SET_VOLUME control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>