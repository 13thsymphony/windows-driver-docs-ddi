---
UID: NI:ks.IOCTL_KS_ENABLE_EVENT
title: IOCTL_KS_ENABLE_EVENT
author: windows-driver-content
description: An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object.
old-location: stream\ioctl_ks_enable_event.htm
old-project: stream
ms.assetid: 194a99f4-900f-44d1-bbc3-64953e4dce21
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_KS_ENABLE_EVENT, IOCTL_KS_ENABLE_EVENT control code [Streaming Media Devices], ks-ioctl_7cc1eab4-2a30-4998-8f7d-122150800c9a.xml, ks/IOCTL_KS_ENABLE_EVENT, stream.ioctl_ks_enable_event
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
-	IOCTL_KS_ENABLE_EVENT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_ENABLE_EVENT IOCTL
An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. The application specifies IOCTL_KS_ENABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The application places a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a> in the <b>InBuffer</b> parameter and the size of this structure at <b>InLength</b>.

### Input Buffer Length
Length of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>.

### Output Buffer
The application places a pointer to a structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> in the <b>OutBuffer</b> parameter and the size of this structure at <b>OutLength</b>.

### Output Buffer Length
Length of <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the Status member is set to STATUS_SUCCESS.

## Remarks
To determine events supported by a KS object, specify <b>NULL</b> and 0 respectively for <b>InBuffer</b> and <b>InLength</b>.

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