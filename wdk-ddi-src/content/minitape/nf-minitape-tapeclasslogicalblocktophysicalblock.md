---
UID: NF:minitape.TapeClassLogicalBlockToPhysicalBlock
title: TapeClassLogicalBlockToPhysicalBlock function
author: windows-driver-content
description: The TapeClassLogicalBlockToPhysicalBlock routine translates a pseudological block address to a physical block address. This routine is for SCSI-1 devices.
old-location: storage\tapeclasslogicalblocktophysicalblock.htm
old-project: storage
ms.assetid: 4ad11a15-ba72-4921-a00a-6d3bfb443b51
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: TapeClassLogicalBlockToPhysicalBlock, TapeClassLogicalBlockToPhysicalBlock routine [Storage Devices], minitape/TapeClassLogicalBlockToPhysicalBlock, storage.tapeclasslogicalblocktophysicalblock, tapeclas_6d45358d-68a6-4f00-991e-714a489fd78d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: minitape.h
req.include-header: Minitape.h
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
req.lib: Tape.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Tape.lib
-	Tape.dll
api_name:
-	TapeClassLogicalBlockToPhysicalBlock
product: Windows
targetos: Windows
req.typenames: TAPE_STATUS, *PTAPE_STATUS
---


# TapeClassLogicalBlockToPhysicalBlock function
The <b>TapeClassLogicalBlockToPhysicalBlock</b> routine translates a pseudological block address to a physical block address. This routine is for SCSI-1 devices.

## Syntax

````
TAPE_PHYS_POSITION TapeClassLogicalBlockToPhysicalBlock(
  _In_ UCHAR   DensityCode,
  _In_ ULONG   LogicalBlockAddress,
  _In_ ULONG   BlockLength,
  _In_ BOOLEAN FromBOT
);
````

## Parameters

`DensityCode`

Specifies the tape media density code. This routine supports tapes with the following density codes: QIC_24, QIC_120, QIC_150, QIC_525, QIC_1000, QIC_2GB, QIC_1350, and QIC_2100.

`LogicalBlockAddress`

Specifies a pseudological block address.

`BlockLength`

Specifies the logical block size, in bytes.

`FromBOT`

<b>TRUE</b> indicates that the physical block calculation should start at the beginning of the tape and account for the physical device header. <b>FALSE</b> indicates that the tape has two partitions, that the block address is on the directory partition, and therefore no physical device header needs to be factored into the calculation.


## Return Value

<b>TapeClassLogicalBlockToPhysicalBlock</b> returns a structure containing the physical block address:
      

typedef struct _TAPE_PHYS_POSITION {

ULONG SeekBlockAddress;

ULONG SpaceBlockCount;

} TAPE_PHYS_POSITION, PTAPE_PHYS_POSITION;

## Remarks

A tape miniclass driver calls <b>TapeClassLogicalBlockToPhysicalBlock</b> to translate a logical block address from an application to a physical block address for a tape device. <b>TapeClassLogicalBlockToPhysicalBlock</b> is not necessary for SCSI-2 or later drivers because devices that comply with SCSI-2 or later standards support logical block addressing.

To position a tape to the physical block address returned by this routine, a tape miniclass driver issues two SCSI commands: a LOCATE command to position the tape to the <b>SeekBlockAddress</b>, and then a SPACE command to advance the tape <b>SpaceBlockCount</b>. The <b>SpaceBlockCount</b> value is necessary if the pseudological blocks on the tape are smaller than the physical blocks; in that case, the logical block boundary might not align with a physical block boundary.

If a tape miniclass driver calls this routine with an unsupported tape density code, <b>TapeClassLogicalBlockToPhysicalBlock</b> does not perform any translation. It returns the logical block address in <b>SeekBlockAddress</b> and returns zero in <b>SpaceBlockCount</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | minitape.h (include Minitape.h) |
| **Library** | Tape.lib |

## See Also

<a href="..\minitape\nf-minitape-tapeclassphysicalblocktologicalblock.md">TapeClassPhysicalBlockToLogicalBlock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TapeClassLogicalBlockToPhysicalBlock routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>