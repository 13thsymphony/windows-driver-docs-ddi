---
UID : NF:srb.ScsiPortWriteRegisterBufferUlong
title : ScsiPortWriteRegisterBufferUlong function
author : windows-driver-content
description : The ScsiPortWriteRegisterBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location : storage\scsiportwriteregisterbufferulong.htm
old-project : storage
ms.assetid : d77b188e-45b2-47c3-bee5-557886925d3f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : srb/ScsiPortWriteRegisterBufferUlong, ScsiPortWriteRegisterBufferUlong, ScsiPortWriteRegisterBufferUlong routine [Storage Devices], scsiprt_f6ce8fd2-0d06-4bda-9673-983af38f08e9.xml, storage.scsiportwriteregisterbufferulong
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : srb.h
req.include-header : Miniport.h, Scsi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Scsiport.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product : Windows 10 or later.
---


# ScsiPortWriteRegisterBufferUlong function
The <b>ScsiPortWriteRegisterBufferUlong</b> routine transfers a given number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortWriteRegisterBufferUlong(
  _In_ PULONG Register,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to a buffer containing the data to be written.

`Count`

Specifies the number of ULONG values to be transferred to the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWriteRegisterBufferUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>