---
UID: NS:storport._SRBEX_DATA_BIDIRECTIONAL
title: "_SRBEX_DATA_BIDIRECTIONAL"
author: windows-driver-content
description: The SRBEX_DATA_BIDIRECTIONAL structure contains the extended SRB data for bi-directional transfer commands.
old-location: storage\srbex_data_bidirectional.htm
old-project: storage
ms.assetid: B61247DC-8AC3-4A96-985B-A4CAC232555E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSRBEX_DATA_BIDIRECTIONAL, PSRBEX_DATA_BIDIRECTIONAL, PSRBEX_DATA_BIDIRECTIONAL structure pointer [Storage Devices], SRBEX_DATA_BIDIRECTIONAL, SRBEX_DATA_BIDIRECTIONAL structure [Storage Devices], _SRBEX_DATA_BIDIRECTIONAL, storage.srbex_data_bidirectional, storport/PSRBEX_DATA_BIDIRECTIONAL, storport/SRBEX_DATA_BIDIRECTIONAL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
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
-	SRBEX_DATA_BIDIRECTIONAL
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_BIDIRECTIONAL, *PSRBEX_DATA_BIDIRECTIONAL
req.product: Windows 10 or later.
---

# _SRBEX_DATA_BIDIRECTIONAL structure
The <b>SRBEX_DATA_BIDIRECTIONAL</b> structure contains the extended SRB data for bi-directional transfer commands.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SRBEX_DATA_BIDIRECTIONAL {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  ULONG               DataInTransferLength;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN DataInBuffer;
} SRBEX_DATA_BIDIRECTIONAL, *PSRBEX_DATA_BIDIRECTIONAL;
````

## Members


`Type`

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeBidirectional</b>.

`Length`

Length of the data in this structure, in bytes, starting with the <b>DataInTransferLength</b> member. Set to SRBEX_DATA_BIDIRECTIONAL_LENGTH.

`DataInTransferLength`

Length of the data present  in the <b>DataInBuffer</b> member.

`Reserved1`

This member is reserved. Set to 0.

`DataInBuffer`

A pointer to the buffer that contains the data sent from the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | storport.h (include Storport.h, Srb.h, Minitape.h) |

## See Also

<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>