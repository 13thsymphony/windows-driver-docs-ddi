---
UID: NS:ntddscsi._SCSI_INQUIRY_DATA
title: "_SCSI_INQUIRY_DATA"
author: windows-driver-content
description: The SCSI_INQUIRY_DATA structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_inquiry_data.htm
old-project: storage
ms.assetid: f62c35dd-791d-4c21-9836-308cc5fb102b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_INQUIRY_DATA, PSCSI_INQUIRY_DATA, PSCSI_INQUIRY_DATA structure pointer [Storage Devices], SCSI_INQUIRY_DATA, SCSI_INQUIRY_DATA structure [Storage Devices], _SCSI_INQUIRY_DATA, ntddscsi/PSCSI_INQUIRY_DATA, ntddscsi/SCSI_INQUIRY_DATA, storage.scsi_inquiry_data, structs-scsibus_caffe649-9258-4363-ac26-da2c81bebdd1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	ntddscsi.h
api_name:
-	SCSI_INQUIRY_DATA
product: Windows
targetos: Windows
req.typenames: SCSI_INQUIRY_DATA, *PSCSI_INQUIRY_DATA
---

# _SCSI_INQUIRY_DATA structure
The SCSI_INQUIRY_DATA structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a> request to retrieve the SCSI inquiry data for all devices on a given SCSI bus. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSI_INQUIRY_DATA {
  UCHAR   PathId;
  UCHAR   TargetId;
  UCHAR   Lun;
  BOOLEAN DeviceClaimed;
  ULONG   InquiryDataLength;
  ULONG   NextInquiryDataOffset;
  UCHAR   InquiryData[1];
} SCSI_INQUIRY_DATA, *PSCSI_INQUIRY_DATA;
````

## Members


`PathId`

Indicates the number of the bus the device is located on.

`TargetId`

Indicates the number of the device on the bus.

`Lun`

Indicates the logical unit number of the logical unit on the target device.

`DeviceClaimed`

When <b>TRUE</b>, indicates that the device has been claimed by a class driver.

`InquiryDataLength`

Indicates the length in bytes of inquiry data.

`NextInquiryDataOffset`

Contains an offset to the inquiry data for the next logical unit on the target device.

`InquiryData`

Pointer to buffer containing the inquiry data for the logical unit.

## Remarks
The <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a> request retrieves inquiry data for all devices associated with a specified adapter. An adapter can potentially have multiple buses. The <b>PathId</b> member identifies the bus. Each bus can have multiple target devices. The <b>TargetId</b> member identifies the target device, and each target device can have multiple logical units. The <b>Lun</b> member identifies the logical unit.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_scsi_bus_data.md">SCSI_BUS_DATA</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_adapter_bus_info.md">SCSI_ADAPTER_BUS_INFO</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_inquiry_data.md">IOCTL_SCSI_GET_INQUIRY_DATA</a>