---
UID: NS:hbapiwmi._SendSRL_OUT
title: "_SendSRL_OUT"
author: windows-driver-content
description: The SendSRL_OUT structure is used to report the output parameter data of the SendSRL WMI method to the WMI client.
old-location: storage\sendsrl_out.htm
old-project: storage
ms.assetid: f7a08e0e-cbb1-4ec5-96c6-dade9d298d0a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSendSRL_OUT, PSendSRL_OUT, PSendSRL_OUT structure pointer [Storage Devices], SendSRL_OUT, SendSRL_OUT structure [Storage Devices], _SendSRL_OUT, hbapiwmi/PSendSRL_OUT, hbapiwmi/SendSRL_OUT, storage.sendsrl_out, structs-Fibre_4cef4091-719d-457e-aeca-d3ab10b23344.xml"
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
-	SendSRL_OUT
product:
- Windows
targetos: Windows
req.typenames: SendSRL_OUT, *PSendSRL_OUT
---

# _SendSRL_OUT structure
The SendSRL_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565522">SendSRL</a> WMI method to the WMI client.

## Syntax
```
typedef struct _SendSRL_OUT {
  ULONG HBAStatus;
  ULONG TotalRspBufferSize;
  ULONG ActualRspBufferSize;
  UCHAR RspBuffer[1];
} SendSRL_OUT, *PSendSRL_OUT;
```

## Members


`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`TotalRspBufferSize`

Contains the size in bytes of the results of the SRL command.

`ActualRspBufferSize`

Contains the size in bytes of the data that was actually retrieved.

`RspBuffer`

Contains the results of the SRL command.

## Remarks
The WMI tool suite generates a declaration of the SendSRL_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565522">SendSRL</a>