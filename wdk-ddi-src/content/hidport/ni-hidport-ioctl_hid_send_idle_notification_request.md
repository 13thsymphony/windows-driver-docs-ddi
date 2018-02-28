---
UID: NI:hidport.IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
title: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
author: windows-driver-content
description: The IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.
old-location: hid\ioctl_hid_send_idle_notification_request.htm
old-project: hid
ms.assetid: AD653C7C-7C43-4258-98F8-3D9EDB51AE44
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST, IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code [Human Input Devices], hid.ioctl_hid_send_idle_notification_request, hidport/IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: Hidport.h
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
-	Hidport.h
api_name:
-	IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST IOCTL
The <b>IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST</b> 
   control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

### Input Buffer Length
The size of a status code.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The bus or port driver sets Irp-&gt;IoStatus.Status to STATUS_SUCCESS or the appropriate error status.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidport.h (include Hidport.h) |