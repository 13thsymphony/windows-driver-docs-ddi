---
UID: NS:hbapiwmi._ScsiInquiry_OUT
title: "_ScsiInquiry_OUT"
author: windows-driver-content
description: The ScsiInquiry_OUT structure is used to report the output data of the ScsiInquiry WMI method to the WMI client.
old-location: storage\scsiinquiry_out2.htm
old-project: storage
ms.assetid: ea1d6f35-1dc5-4c65-9158-7f85464c5cd7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/PScsiInquiry_OUT, *PScsiInquiry_OUT, ScsiInquiry_OUT structure [Storage Devices], _ScsiInquiry_OUT, hbapiwmi/ScsiInquiry_OUT, PScsiInquiry_OUT, ScsiInquiry_OUT, storage.scsiinquiry_out2, structs-Fibre_2c7df8b3-a571-4e88-b4db-202d2bd39ce8.xml, PScsiInquiry_OUT structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hbapiwmi.h
apiname:
-	ScsiInquiry_OUT
product: Windows
targetos: Windows
req.typenames: ScsiInquiry_OUT, *PScsiInquiry_OUT
---

# _ScsiInquiry_OUT structure
The ScsiInquiry_OUT structure is used to report the output data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> WMI method to the WMI client.

## Syntax
````
typedef struct _ScsiInquiry_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferSize;
  ULONG SenseBufferSize;
  UCHAR ScsiStatus;
  UCHAR ResponseBuffer[1];
  UCHAR SenseBuffer[1];
} ScsiInquiry_OUT, *PScsiInquiry_OUT;
````

## Members


`HBAStatus`

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation.

`ResponseBuffer`

Contains the results of the SCSI inquiry command.

`ResponseBufferSize`

Indicates the size in bytes of the buffer that will hold the results of the inquiry command.

`ScsiStatus`

Contains the status of the SCSI inquiry command.

`SenseBufferSize`

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command.

## Remarks
The WMI tool suite generates a declaration of the ScsiInquiry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiInquiry_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>