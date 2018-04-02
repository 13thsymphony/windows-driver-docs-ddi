---
UID: NS:hbapiwmi._SendLIRR_OUT
title: "_SendLIRR_OUT"
author: windows-driver-content
description: The SendLIRR_OUT structure is used to report the output parameter data of the SendLIRR WMI method to the WMI client.
old-location: storage\sendlirr_out.htm
old-project: storage
ms.assetid: 842842c2-ed79-4c8a-b9c1-d73c47998f91
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSendLIRR_OUT, PSendLIRR_OUT, PSendLIRR_OUT structure pointer [Storage Devices], SendLIRR_OUT, SendLIRR_OUT structure [Storage Devices], _SendLIRR_OUT, hbapiwmi/PSendLIRR_OUT, hbapiwmi/SendLIRR_OUT, storage.sendlirr_out, structs-Fibre_193ae454-313d-4ada-a161-39c403226edf.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	SendLIRR_OUT
product:
- Windows
targetos: Windows
req.typenames: SendLIRR_OUT, *PSendLIRR_OUT
---

# _SendLIRR_OUT structure
The SendLIRR_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a> WMI method to the WMI client.

## Syntax
```
typedef struct _SendLIRR_OUT {
  ULONG HBAStatus;
  ULONG TotalRspBufferSize;
  ULONG ActualRspBufferSize;
  UCHAR RspBuffer[1];
} *PSendLIRR_OUT, SendLIRR_OUT;
```

## Members


`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`TotalRspBufferSize`

Contains the size in bytes of the results of the LIRR command.

`ActualRspBufferSize`

Contains the size in bytes of the data that was actually retrieved.

`RspBuffer`

Contains the results of the LIRR command.

## Remarks
The WMI tool suite generates a declaration of the SendLIRR_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a>