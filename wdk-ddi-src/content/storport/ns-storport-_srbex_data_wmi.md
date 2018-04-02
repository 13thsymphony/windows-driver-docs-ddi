---
UID: NS:storport._SRBEX_DATA_WMI
title: "_SRBEX_DATA_WMI"
author: windows-driver-content
description: The SRBEX_DATA_WMI structure contains the request data for an extended WMI SRB.
old-location: storage\srbex_data_wmi.htm
old-project: storage
ms.assetid: 3FFBF258-50C3-4D2D-AFC8-184D2FF85EE4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSRBEX_DATA_WMI, PSRBEX_DATA_WMI, PSRBEX_DATA_WMI structure pointer [Storage Devices], SRBEX_DATA_WMI, SRBEX_DATA_WMI structure [Storage Devices], _SRBEX_DATA_WMI, storage.srbex_data_wmi, storport/PSRBEX_DATA_WMI, storport/SRBEX_DATA_WMI"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available  starting with Windows 8.
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
-	SRBEX_DATA_WMI
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA_WMI, *PSRBEX_DATA_WMI
req.product: Windows 10 or later.
---

# _SRBEX_DATA_WMI structure
The <b>SRBEX_DATA_WMI</b> structure contains the request data for an extended WMI SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
```
typedef struct _SRBEX_DATA_WMI {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               WMISubFunction;
  UCHAR               WMIFlags;
  UCHAR               Reserved[2];
  ULONG               Reserved1;
  PVOID POINTER_ALIGN DataPath;
} SRBEX_DATA_WMI, *PSRBEX_DATA_WMI;
```

## Members


`Type`

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypeWmi</b>.

`Length`

Length of the data in this structure starting with the <b>WMISubFunction</b> member. Set to SRBEX_DATA_WMI_LENGTH.

`WMISubFunction`

Indicates the WMI action to be performed. The subfunction value corresponds to the WMI minor IRP number that identifies the WMI operation.

`WMIFlags`

Indicates that the WMI request is for the adapter if SRB_WMI_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>WMIFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a> structure.

`Reserved`

This member is reserved. Contains zeros.

`Reserved1`

This member is reserved. Set to 0.

`DataPath`

Specifies the WMI data path for this request.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available  starting with Windows 8. Available  starting with Windows 8. |
| **Header** | storport.h (include Storport.h, Srb.h, Minitape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>