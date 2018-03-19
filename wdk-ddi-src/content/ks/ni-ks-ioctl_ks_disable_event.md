---
UID: NI:ks.IOCTL_KS_DISABLE_EVENT
title: IOCTL_KS_DISABLE_EVENT
author: windows-driver-content
description: An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the IoControl parameter of a call to KsSynchronousDeviceControl.
old-location: stream\ioctl_ks_disable_event.htm
old-project: stream
ms.assetid: 4e451d0c-6548-4735-833a-3972cf5e59c6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_KS_DISABLE_EVENT, IOCTL_KS_DISABLE_EVENT control code [Streaming Media Devices], ks-ioctl_8b6cd750-3003-49b2-9b91-3edc1da6cf11.xml, ks/IOCTL_KS_DISABLE_EVENT, stream.ioctl_ks_disable_event
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	IOCTL_KS_DISABLE_EVENT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_DISABLE_EVENT IOCTL
An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The application places a pointer to a structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> in the <b>InBuffer</b> parameter. This is the location of the original KSEVENTDATA structure that the application instantiated at the enabling of the event. To disable all active events, a client specifies a <b>NULL</b> pointer and length of zero in the <b>InBuffer</b> and <b>InLength</b> parameters.

### Input Buffer Length
Length of <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the Status member is set to STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>



<a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a>



<a href="..\ks\nf-ks-ksdisableevent.md">KsDisableEvent</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="..\ks\ni-ks-ioctl_ks_disable_event.md">IOCTL_KS_DISABLE_EVENT</a>



<a href="..\ks\ns-ks-ksdpc_item.md">KSDPC_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>