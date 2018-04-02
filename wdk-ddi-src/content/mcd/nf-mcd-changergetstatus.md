---
UID: NF:mcd.ChangerGetStatus
title: ChangerGetStatus function
author: windows-driver-content
description: ChangerGetStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_STATUS.
old-location: storage\changergetstatus.htm
old-project: storage
ms.assetid: f5719dfa-e48a-4f81-8344-31b349fadb48
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerGetStatus, ChangerGetStatus function [Storage Devices], chgrmini_8975ca0f-d42c-40d0-a16c-a2ec5d2a2f66.xml, mcd/ChangerGetStatus, storage.changergetstatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerGetStatus
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerGetStatus function
<b>ChangerGetStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559405">IOCTL_CHANGER_GET_STATUS</a>.

## Syntax

```
NTSTATUS ChangerGetStatus(
  PDEVICE_OBJECT DeviceObject,
  PIRP           Irp
);
```

## Parameters

`DeviceObject`

Pointer to the device object that represents the changer.

`Irp`

Pointer to the IRP.


## Return Value

<b>ChangerGetStatus</b> returns the STATUS_<i>XXX</i> value returned by the system port driver. If there is not enough memory to process the request or to process the STATUS_<i>XXX</i> value returned by the system port driver <b>ChangerGetStatus</b> returns STATUS_INSUFFICIENT_RESOURCES.

## Remarks

This routine is required.

<b>ChangerGetStatus</b> indicates whether the changer is able to accept requests. 

<b>ChangerGetStatus</b> builds an SRB with a CDB to get the changer's status (using the SCSI command TEST UNIT READY or non-SCSI equivalent) and sends it to the system port driver to obtain status of the changer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551424">ChangerGetElementStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559405">IOCTL_CHANGER_GET_STATUS</a>