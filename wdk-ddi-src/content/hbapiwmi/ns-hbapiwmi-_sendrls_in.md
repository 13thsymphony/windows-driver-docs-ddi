---
UID: NS:hbapiwmi._SendRLS_IN
title: "_SendRLS_IN"
author: windows-driver-content
description: The SendRLS_IN structure is used to deliver input parameter data to the SendRLS WMI method.
old-location: storage\sendrls_in.htm
old-project: storage
ms.assetid: ba78482f-243a-4f60-907e-8d5c4a702ef2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSendRLS_IN, PSendRLS_IN, PSendRLS_IN structure pointer [Storage Devices], SendRLS_IN, SendRLS_IN structure [Storage Devices], _SendRLS_IN, hbapiwmi/PSendRLS_IN, hbapiwmi/SendRLS_IN, storage.sendrls_in, structs-Fibre_c78b38af-b1e5-4f98-a57c-9c4c81b4a5f3.xml"
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
-	SendRLS_IN
product:
- Windows
targetos: Windows
req.typenames: SendRLS_IN, *PSendRLS_IN
---

# _SendRLS_IN structure
The SendRLS_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a> WMI method.

## Syntax
```
typedef struct _SendRLS_IN {
  UCHAR PortWWN[8];
  UCHAR DestWWN[8];
} *PSendRLS_IN, SendRLS_IN;
```

## Members


`PortWWN`

Contains a worldwide name for the local port through which the read link error status block (RLS) command is sent.

`DestWWN`

Contains a worldwide name for the destination port.

## Remarks
The WMI tool suite generates a declaration of the SendRLS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a>