---
UID : NI:nfpdev.IOCTL_NFP_ENABLE
title : IOCTL_NFP_ENABLE
author : windows-driver-content
description : The client sends the IOCTL_NFP_ENABLE request to re-enable previously disabled subscriptions, publications, and presence events.
old-location : nfpdrivers\ioctl_nfp_enable.htm
old-project : nfpdrivers
ms.assetid : 25D4C7BB-782D-4BDB-9E07-F152E3705705
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfpdrivers.ioctl_nfp_enable, IOCTL_NFP_ENABLE, _IOCTL_NFP_ENABLE, IOCTL_NFP_ENABLE control code [Near-Field Proximity Drivers], IOCTL_NFP_ENABLE, nfpdev/IOCTL_NFP_ENABLE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : nfpdev.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : 
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
req.typenames : "*PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO"
---

# IOCTL_NFP_ENABLE IOCTL
The client sends the <b>IOCTL_NFP_ENABLE</b> request to re-enable previously disabled subscriptions, publications, and presence events.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## Remarks
The following are required actions when using this IOCTL:<ul>
<li>
	When this IOCTL is received the driver MUST mark the file handle as “Enabled”.

</li>
<li>
	If the file handle is already marked “Enabled” the driver MUST complete the IOCTL with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
If a device is currently proximate when this IOCTL is successfully completed, then the message data (along with its type) MUST be transmitted (only once) to the proximate device.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | nfpdev.h |
| **IRQL** |  |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a>

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) overall design guide</a>

<a href="..\nfpdev\ni-nfpdev-ioctl_nfp_disable.md">IOCTL_NFP_DISABLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_NFP_ENABLE control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>