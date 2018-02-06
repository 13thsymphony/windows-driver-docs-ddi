---
UID: NF:mcd.ChangerGetStatus
title: ChangerGetStatus function
author: windows-driver-content
description: ChangerGetStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_STATUS.
old-location: storage\changergetstatus.htm
old-project: storage
ms.assetid: f5719dfa-e48a-4f81-8344-31b349fadb48
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mcd/ChangerGetStatus, chgrmini_8975ca0f-d42c-40d0-a16c-a2ec5d2a2f66.xml, ChangerGetStatus, storage.changergetstatus, ChangerGetStatus function [Storage Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mcd.h
apiname:
-	ChangerGetStatus
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerGetStatus function
<b>ChangerGetStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_status.md">IOCTL_CHANGER_GET_STATUS</a>.

## Syntax

````
NTSTATUS ChangerGetStatus(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

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
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>

<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_status.md">IOCTL_CHANGER_GET_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerGetStatus function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>