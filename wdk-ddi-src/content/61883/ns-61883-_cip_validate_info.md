---
UID: NS:61883._CIP_VALIDATE_INFO
title: "_CIP_VALIDATE_INFO"
author: windows-driver-content
description: The CIP_VALIDATE_INFO structure contains information about the frame.
old-location: ieee\cip_validate_info.htm
old-project: IEEE
ms.assetid: 98993973-91a4-456a-9343-c744408055ed
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCIP_VALIDATE_INFO, 61883/CIP_VALIDATE_INFO, 61883/PCIP_VALIDATE_INFO, 61883_structures_9f8bc3f2-ad43-4e0b-a4f9-8d441397f11d.xml, CIP_VALIDATE_INFO, CIP_VALIDATE_INFO structure [Buses], IEEE.cip_validate_info, PCIP_VALIDATE_INFO, PCIP_VALIDATE_INFO structure pointer [Buses], _CIP_VALIDATE_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
api_name:
-	CIP_VALIDATE_INFO
product: Windows
targetos: Windows
req.typenames: CIP_VALIDATE_INFO, *PCIP_VALIDATE_INFO
---

# _CIP_VALIDATE_INFO structure
The CIP_VALIDATE_INFO structure contains information about the frame.

## Syntax
```
typedef struct _CIP_VALIDATE_INFO {
  HANDLE     hConnect;
  PVOID      Context;
  CYCLE_TIME TimeStamp;
  PUCHAR     Packet;
} *PCIP_VALIDATE_INFO, CIP_VALIDATE_INFO;
```

## Members


`hConnect`

A handle to the connection.

`Context`

Points to the context provided by the caller at <b>ValidateContext</b> in the input CIP_FRAME structure.

`TimeStamp`

The timestamp of the current source packet.

`Packet`

The packet offset for the current source packet.

## Remarks
The IEC-61883 protocol driver allocates and initializes this structure from the input CIP_FRAME structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h (include 61883.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a>