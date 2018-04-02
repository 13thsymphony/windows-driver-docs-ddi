---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_PROTOCOL
title: IOCTL_SMARTCARD_SET_PROTOCOL
author: windows-driver-content
description: Sets the procotol the driver communicates to the smart card with after the card is detected.
old-location: nfpdrivers\ioctl_smartcard_set_protocol.htm
old-project: nfpdrivers
ms.assetid: 9A54D427-128F-41C1-B6BD-EE09B0402C32
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SMARTCARD_SET_PROTOCOL, IOCTL_SMARTCARD_SET_PROTOCOL control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_set_protocol, winsmcrd/IOCTL_SMARTCARD_SET_PROTOCOL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winsmcrd.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsmcrd.h
api_name:
-	IOCTL_SMARTCARD_SET_PROTOCOL
product:
- Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_SET_PROTOCOL IOCTL
Sets the procotol the driver communicates to the smart card with after the card is detected.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
(DWORD) mask of protocols below:<ul>
<li>SCARD_PROTOCOL_T1</li>
<li>SCARD_PROTOCOL_DEFAULT</li>
<li>SCARD_PROTOCOL_OPTIMAL</li>
</ul>

### Input Buffer Length
<text></text>

### Output Buffer
(DWORD) contains the selected protocol (for example, SCARD_PROTOCOL_T1).

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsmcrd.h |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>