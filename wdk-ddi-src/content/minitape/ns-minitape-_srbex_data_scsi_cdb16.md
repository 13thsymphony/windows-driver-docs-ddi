---
UID: NS:minitape._SRBEX_DATA_SCSI_CDB16
title: "_SRBEX_DATA_SCSI_CDB16"
author: windows-driver-content
description: The SRBEX_DATA_SCSI_CDB16 structure contains the extended SRB data for a 16-byte SCSI command data block (CDB).
old-location: storage\srbex_data_scsi_cdb16.htm
old-project: storage
ms.assetid: 168AC5F4-652B-405C-BE41-CD416A66FB74
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSRBEX_DATA_SCSI_CDB16, PSRBEX_DATA_SCSI_CDB16, PSRBEX_DATA_SCSI_CDB16 structure pointer [Storage Devices], SRBEX_DATA_SCSI_CDB16, SRBEX_DATA_SCSI_CDB16 structure [Storage Devices], _SRBEX_DATA_SCSI_CDB16, storage.srbex_data_scsi_cdb16, storport/PSRBEX_DATA_SCSI_CDB16, storport/SRBEX_DATA_SCSI_CDB16"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	Storport.h
api_name:
-	SRBEX_DATA_SCSI_CDB16
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_SCSI_CDB16, *PSRBEX_DATA_SCSI_CDB16
---

# _SRBEX_DATA_SCSI_CDB16 structure
The <b>SRBEX_DATA_SCSI_CDB16</b> structure contains the extended SRB data for a 16-byte SCSI command data block (CDB).
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SRBEX_DATA_SCSI_CDB16 {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               ScsiStatus;
  UCHAR               SenseInfoBufferLength;
  ULONG               CdbLength;
  UCHAR               Reserved;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN SenseInfoBuffer;
  UCHAR POINTER_ALIGN Cdb[16];
} SRBEX_DATA_SCSI_CDB16, *PSRBEX_DATA_SCSI_CDB16;
````

## Members


`Type`

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeScsiCdb16</b>.

`Length`

Length of the data in this structure, in bytes, starting with the <b>ScsiStatus</b> member. Set to SRBEX_DATA_SCSI_CDB16_LENGTH.

`ScsiStatus`

The SCSI status code returned for the submitted SRB.

`SenseInfoBufferLength`

The length of the sense information returned in the buffer pointed to by <b>SenseInfoBuffer</b>.

`CdbLength`

The length of the CDB data, in bytes, of the <b>Cdb</b> array.

`Reserved`

This member is reserved. Set to 0.

`Reserved1`

This member is reserved. Set to 0.

`SenseInfoBuffer`

A pointer to a buffer containing any returned sense information.

`Cdb`

The 16-byte CDB buffer.

## Remarks
This structure is used to submit an extended SRB data for a CDB of 16 bytes or less.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | minitape.h (include Storport.h, Srb.h, Minitape.h) |

## See Also

<a href="..\storport\ns-storport-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>



<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>