---
UID: NF:storport.ScsiPortReadPortBufferUlong
title: ScsiPortReadPortBufferUlong macro
author: windows-driver-content
description: The ScsiPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportbufferulong.htm
old-project: storage
ms.assetid: 719210f5-22d6-425d-aff0-aefbebfbfca2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.scsiportreadportbufferulong, srb/ScsiPortReadPortBufferUlong, ScsiPortReadPortBufferUlong, scsiprt_5da99f27-5758-4e1b-af45-0d9069b55af7.xml, ScsiPortReadPortBufferUlong routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Miniport.h, Scsi.h, Storport.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Scsiport.lib
-	Scsiport.dll
apiname:
-	ScsiPortReadPortBufferUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# ScsiPortReadPortBufferUlong function
The <b>ScsiPortReadPortBufferUlong</b> routine transfers a given number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortReadPortBufferUlong(
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`Port`

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to the buffer.

`Count`

Specifies the number of ULONG values to read from the HBA.


## Return Value

None

## Remarks

<b>ScsiPortReadPortBufferUlong</b> ensures that the data is transferred correctly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | storport.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortReadPortBufferUlong routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>