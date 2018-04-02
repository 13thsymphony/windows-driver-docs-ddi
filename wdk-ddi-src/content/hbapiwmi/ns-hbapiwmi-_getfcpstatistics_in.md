---
UID: NS:hbapiwmi._GetFCPStatistics_IN
title: "_GetFCPStatistics_IN"
author: windows-driver-content
description: The GetFCPStatistics_IN structure is used to deliver input parameter data to the GetFCPStatistics WMI method.
old-location: storage\getfcpstatistics_in.htm
old-project: storage
ms.assetid: f6cb4532-fc66-45e7-a779-0981465d69fc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PGetFCPStatistics_IN, GetFCPStatistics_IN, GetFCPStatistics_IN structure [Storage Devices], PGetFCPStatistics_IN, PGetFCPStatistics_IN structure pointer [Storage Devices], _GetFCPStatistics_IN, hbapiwmi/GetFCPStatistics_IN, hbapiwmi/PGetFCPStatistics_IN, storage.getfcpstatistics_in, structs-Fibre_409be852-67ff-45c4-bce1-291076c1a70b.xml"
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
-	GetFCPStatistics_IN
product: Windows
targetos: Windows
req.typenames: GetFCPStatistics_IN, *PGetFCPStatistics_IN
---

# _GetFCPStatistics_IN structure
The GetFCPStatistics_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554939">GetFCPStatistics</a> WMI method.

## Syntax
```
typedef struct _GetFCPStatistics_IN {
  HBAScsiID ScsiId;
} GetFCPStatistics_IN, *PGetFCPStatistics_IN;
```

## Members


`ScsiId`

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556042">HBAScsiID</a> that uniquely identifies a logical unit and the bus and HBA that the logical unit is connected to.

## Remarks
The WMI tool suite generates a declaration of the GetFCPStatistics_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554939">GetFCPStatistics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556042">HBAScsiID</a>