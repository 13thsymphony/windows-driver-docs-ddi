---
UID : NF:srb.ScsiPortReadRegisterBufferUshort
title : ScsiPortReadRegisterBufferUshort function
author : windows-driver-content
description : The ScsiPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location : storage\scsiportreadregisterbufferushort.htm
old-project : storage
ms.assetid : 6db90186-a663-4710-8209-abd5ef2b361a
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : srb/ScsiPortReadRegisterBufferUshort, ScsiPortReadRegisterBufferUshort, scsiprt_f6e36a20-066b-4b3e-bf94-9182e84dc2eb.xml, ScsiPortReadRegisterBufferUshort routine [Storage Devices], storage.scsiportreadregisterbufferushort
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
req.typenames : "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product : Windows 10 or later.
---


# ScsiPortReadRegisterBufferUshort function
The <b>ScsiPortReadRegisterBufferUshort</b> routine transfers a specified number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortReadRegisterBufferUshort(
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to the buffer.

`Count`

Specifies the number of USHORT values to be read from the HBA.


## Return Value

None

## Remarks

<b>ScsiPortReadRegisterBufferUshort</b> ensures that the data has been transferred correctly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortReadRegisterBufferUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>