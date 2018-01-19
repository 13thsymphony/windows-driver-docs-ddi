---
UID : NF:srb.ScsiPortReadPortBufferUchar
title : ScsiPortReadPortBufferUchar function
author : windows-driver-content
description : The ScsiPortReadPortBufferUchar routine transfers a given number of unsigned byte values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location : storage\scsiportreadportbufferuchar.htm
old-project : storage
ms.assetid : 9444670d-5b9f-4d77-b867-ac5608c24e02
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ScsiPortReadPortBufferUchar
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
req.alt-api : ScsiPortReadPortBufferUchar
req.alt-loc : Scsiport.lib,Scsiport.dll
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
req.typenames : "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product : Windows 10 or later.
---


# ScsiPortReadPortBufferUchar function
The <b>ScsiPortReadPortBufferUchar</b> routine transfers a given number of unsigned byte values from the HBA to a buffer.

## Syntax

````
VOID ScsiPortReadPortBufferUchar(
  _In_ PUCHAR Port,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`Port`

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to the buffer.

`Count`

Specifies the number of bytes to be read from the HBA.


## Return Value

None

## Remarks

<b>ScsiPortReadPortBufferUchar</b> ensures that the data is transferred correctly.

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

<dl>
<dt>
<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortReadPortBufferUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>