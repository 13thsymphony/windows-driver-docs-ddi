---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
title: IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL removes the Handfree Profile (HFP) Service Level Connection that existed between the audio driver and the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_request_disconnect.htm
old-project: audio
ms.assetid: BC28F8FC-5C0A-4999-89C1-FE25FD68B9FF
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.ioctl_bthhfp_device_request_disconnect, IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT control code [Audio Devices], IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT, bthhfpddi/IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
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
-	IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT IOCTL
The <b>IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT</b> 
   IOCTL removes the Handfree Profile (HFP) Service Level Connection that existed between the audio driver and  the Bluetooth device.

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
This request initiates the process to disconnect the Service Level Connection and ends without waiting for the disconnection to complete. Connection status can be determined using <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>.

The audio driver sends this request from its handler for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706181">KSPROPERTY_ONESHOT_DISCONNECT</a> KS property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | bthhfpddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_connection_status_update.md">IOCTL_BTHHFP_DEVICE_GET_CONNECTION_STATUS_UPDATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh706181">KSPROPERTY_ONESHOT_DISCONNECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_REQUEST_DISCONNECT control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>