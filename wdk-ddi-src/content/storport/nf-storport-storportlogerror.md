---
UID: NF:storport.StorPortLogError
title: StorPortLogError function
author: windows-driver-content
description: The StorPortLogError routine notifies the port driver that an error occurred.
old-location: storage\storportlogerror.htm
old-project: storage
ms.assetid: f653e6bf-e99b-4aa2-aa54-d7482d326720
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortLogError, StorPortLogError routine [Storage Devices], storage.storportlogerror, storport/StorPortLogError, storprt_0eb9851c-bfce-49aa-a22b-3d16a72b3dde.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortDeprecated
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortLogError
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortLogError function
The <b>StorPortLogError</b> routine notifies the port driver that an error occurred.

## Syntax

````
STORPORT_API VOID StorPortLogError(
  _In_     PVOID               HwDeviceExtension,
  _In_opt_ PSCSI_REQUEST_BLOCK Srb,
  _In_     UCHAR               PathId,
  _In_     UCHAR               TargetId,
  _In_     UCHAR               Lun,
  _In_     ULONG               ErrorCode,
  _In_     ULONG               UniqueId
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`Srb`

Pointer to a SCSI request block if one is associated with the error. Otherwise, this parameter is <b>NULL</b>.

`PathId`

Identifies the SCSI bus.

`TargetId`

Identifies the target controller or device on the bus.

`Lun`

Identifies the logical unit number of the target device.

`ErrorCode`

Specifies an error code indicating one of the following values as the type of error.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SP_BAD_FW_ERROR

</td>
<td>
Indicates the driver has detected bad or old firmware. The device will not be used.

</td>
</tr>
<tr>
<td>
SP_BAD_FW_WARNING

</td>
<td>
Indicates the driver has detected a card with old or bad firmware, which can result in reduced performance or functionality.

</td>
</tr>
<tr>
<td>
SP_BUS_PARITY_ERROR

</td>
<td>
Indicates a SCSI bus parity error was detected.

</td>
</tr>
<tr>
<td>
SP_BUS_TIME_OUT

</td>
<td>
Indicates a SCSI bus connection to a logical unit timed out.

</td>
</tr>
<tr>
<td>
SP_INTERNAL_ADAPTER_ERROR

</td>
<td>
Indicates an internal HBA error was detected.

</td>
</tr>
<tr>
<td>
SP_INVALID_RESELECTION

</td>
<td>
Indicates a logical unit reselected unexpectedly or with an invalid queue tag.

</td>
</tr>
<tr>
<td>
SP_IRQ_NOT_RESPONDING

</td>
<td>
Indicates the HBA is not interrupting when expected.

</td>
</tr>
<tr>
<td>
SP_PROTOCOL_ERROR

</td>
<td>
Indicates the miniport driver detected a SCSI bus protocol error.

</td>
</tr>
<tr>
<td>
SP_REQUEST_TIMEOUT

</td>
<td>
Indicates an operation to the controller has timed out.

</td>
</tr>
<tr>
<td>
SP_UNEXPECTED_DISCONNECT

</td>
<td>
Indicates that a target disconnected unexpectedly.

</td>
</tr>
</table>

`UniqueId`

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same <i>ErrorCode</i> value. For some miniport drivers, this identifies the line of code where the error was detected. For others, it is additional information returned by the HBA.


## Return Value

None

## Remarks

The port driver will log an error to the system event log.

Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> or <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |
| **DDI compliance rules** | StorPortDeprecated |

## See Also

<a href="..\storport\nf-storport-storportlogsystemevent.md">StorPortLogSystemEvent</a>



<a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>



<a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>