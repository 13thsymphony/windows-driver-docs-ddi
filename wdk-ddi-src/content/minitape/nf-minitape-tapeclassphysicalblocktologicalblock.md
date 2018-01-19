---
UID : NF:minitape.TapeClassPhysicalBlockToLogicalBlock
title : TapeClassPhysicalBlockToLogicalBlock function
author : windows-driver-content
description : The TapeClassPhysicalBlockToLogicalBlock routine translates a physical block address to a pseudological block address. This routine is for SCSI-1 devices.
old-location : storage\tapeclassphysicalblocktologicalblock.htm
old-project : storage
ms.assetid : fc95f5c8-2892-479d-ac25-32c07e9c7aab
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : TapeClassPhysicalBlockToLogicalBlock
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : minitape.h
req.include-header : Minitape.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : TapeClassPhysicalBlockToLogicalBlock
req.alt-loc : Tape.lib,Tape.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Tape.lib
req.dll : 
req.irql : 
req.typenames : TAPE_STATUS, *PTAPE_STATUS
---


# TapeClassPhysicalBlockToLogicalBlock function
The <b>TapeClassPhysicalBlockToLogicalBlock</b> routine translates a physical block address to a pseudological block address. This routine is for SCSI-1 devices.

## Syntax

````
ULONG TapeClassPhysicalBlockToLogicalBlock(
  _In_ UCHAR   DensityCode,
  _In_ ULONG   PhysicalBlockAddress,
  _In_ ULONG   BlockLength,
  _In_ BOOLEAN FromBOT
);
````

## Parameters

`DensityCode`

Specifies the tape media density code. This routine supports tapes with the following density codes: QIC_24, QIC_120, QIC_150, QIC_525, QIC_1000, QIC_2GB, QIC_1350, and QIC_2100.

`PhysicalBlockAddress`

Specifies the physical block address obtained by a SCSI READ POSITION command.

`BlockLength`

Specifies the logical block size, in bytes.

`FromBOT`

<b>TRUE</b> indicates that the logical block calculation should start at the beginning of the tape and account for the physical device header. <b>FALSE</b> indicates that the tape has two partitions, that the block address is on the directory partition, and therefore no physical device header needs to be factored into the calculation.


## Return Value

<b>TapeClassPhysicalBlockToLogicalBlock</b> returns the logical block address.

## Remarks

A tape miniclass driver calls <b>TapeClassPhysicalBlockToLogicalBlock</b> to translate a physical block address from a tape device to a logical block address for an application. <b>TapeClassPhysicalBlockToLogicalBlock</b> is not necessary for SCSI-2 or later drivers because devices that comply with SCSI-2 or later standards support logical block addressing.

If a tape miniclass driver calls this routine with an unsupported tape density code, <b>TapeClassPhysicalBlockToLogicalBlock </b>returns the physical block address in the return value, without performing any translation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | minitape.h (include Minitape.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\minitape\nf-minitape-tapeclasslogicalblocktophysicalblock.md">TapeClassLogicalBlockToPhysicalBlock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TapeClassPhysicalBlockToLogicalBlock routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>