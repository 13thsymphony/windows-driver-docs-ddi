---
UID: NS:srb._SRBEX_DATA_POWER
title: "_SRBEX_DATA_POWER"
author: windows-driver-content
description: The SRBEX_DATA_POWER structure contains the request data for an extended power SRB.
old-location: storage\srbex_data_power.htm
old-project: storage
ms.assetid: 61F5C316-5214-45A6-B4BA-DEE6A224E811
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/SRBEX_DATA_POWER, PSRBEX_DATA_POWER structure pointer [Storage Devices], _SRBEX_DATA_POWER, SRBEX_DATA_POWER, storport/PSRBEX_DATA_POWER, *PSRBEX_DATA_POWER, storage.srbex_data_power, PSRBEX_DATA_POWER, SRBEX_DATA_POWER structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Storport.h, Srb.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	SRBEX_DATA_POWER
product: Windows
targetos: Windows
req.typenames: "*PSRBEX_DATA_POWER, SRBEX_DATA_POWER"
req.product: Windows 10 or later.
---

# _SRBEX_DATA_POWER structure
The <b>SRBEX_DATA_POWER</b> structure contains the request data for an extended power SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SRBEX_DATA_POWER {
  SRBEXDATATYPE           Type;
  ULONG                   Length;
  ULONG                   SrbPowerFlags;
  UCHAR                   Reserved[3];
  STOR_DEVICE_POWER_STATE DevicePowerState;
  STOR_POWER_ACTION       PowerAction;
} SRBEX_DATA_POWER, *PSRBEX_DATA_POWER;
````

## Members


`DevicePowerState`

An enumerator value of type <a href="..\storport\ne-storport-_stor_device_power_state.md">STOR_DEVICE_POWER_STATE</a> that specifies the requested power state of the device.

`Length`

Length of the data in this structure starting with the <b>SrbPowerFlags</b> member. Set to SRBEX_DATA_POWER_LENGTH.

`PowerAction`

An enumerator value of type <a href="..\storport\ne-storport-pstor_power_action.md">STOR_POWER_ACTION</a> that specifies the type of system shutdown that is about to occur. This value is meaningful only if the device is moving into the D1, D2, or D3 power state as indicated by the <b>DevicePowerState</b> member.

`Reserved`

This member is reserved. Set to 0.

`SrbPowerFlags`

Indicates that the power request is for the adapter if SRB_POWER_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>SrbPowerFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a> structure.

`Type`

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypePower</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | srb.h (include Storport.h, Srb.h) |

## See Also

<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



<a href="..\storport\ne-storport-pstor_power_action.md">STOR_POWER_ACTION</a>



<a href="..\storport\ne-storport-_stor_device_power_state.md">STOR_DEVICE_POWER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA_POWER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>