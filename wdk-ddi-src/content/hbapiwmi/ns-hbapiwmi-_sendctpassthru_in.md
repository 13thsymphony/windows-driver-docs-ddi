---
UID: NS:hbapiwmi._SendCTPassThru_IN
title: "_SendCTPassThru_IN"
author: windows-driver-content
description: The SendCTPassThru_IN structure is used to deliver input parameter data to the SendCTPassThru WMI method.
old-location: storage\sendctpassthru_in.htm
old-project: storage
ms.assetid: 5a3e06f5-f7f7-4e89-b78e-d6658c34ba9e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSendCTPassThru_IN, PSendCTPassThru_IN, PSendCTPassThru_IN structure pointer [Storage Devices], SendCTPassThru_IN, SendCTPassThru_IN structure [Storage Devices], _SendCTPassThru_IN, hbapiwmi/PSendCTPassThru_IN, hbapiwmi/SendCTPassThru_IN, storage.sendctpassthru_in, structs-Fibre_f95be355-7a10-483c-83cb-058812977a91.xml"
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
-	SendCTPassThru_IN
product: Windows
targetos: Windows
req.typenames: SendCTPassThru_IN, *PSendCTPassThru_IN
---

# _SendCTPassThru_IN structure
The SendCTPassThru_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method.

## Syntax
```
typedef struct _SendCTPassThru_IN {
  UCHAR PortWWN[8];
  ULONG RequestBufferCount;
  UCHAR RequestBuffer[1];
} SendCTPassThru_IN, *PSendCTPassThru_IN;
```

## Members


`PortWWN`

Contains a worldwide name for the HBA through which the target is accessed.

`RequestBufferCount`

Indicates the size in bytes of the buffer that will hold the results of the common transport command.

`RequestBuffer`

Contains the results of the common transport command.

## Remarks
The WMI tool suite generates a declaration of the SendCTPassThru_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a>