---
UID: NS:61883._CMP_NOTIFY_INFO
title: "_CMP_NOTIFY_INFO"
author: windows-driver-content
description: This structure is used by the PCMP_NOTIFY_ROUTINE callback.
old-location: ieee\cmp_notify_info.htm
old-project: IEEE
ms.assetid: 7451B01F-D925-4882-9E6B-EEA79F54C55B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_NOTIFY_INFO, 61883/CMP_NOTIFY_INFO, 61883/PCMP_NOTIFY_INFO, CMP_NOTIFY_INFO, CMP_NOTIFY_INFO structure [Buses], IEEE.cmp_notify_info, PCMP_NOTIFY_INFO, PCMP_NOTIFY_INFO structure pointer [Buses], _CMP_NOTIFY_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	CMP_NOTIFY_INFO
product: Windows
targetos: Windows
req.typenames: CMP_NOTIFY_INFO, *PCMP_NOTIFY_INFO
---

# _CMP_NOTIFY_INFO structure
This structure is used by the <a href="..\61883\nc-61883-pcmp_notify_routine.md">PCMP_NOTIFY_ROUTINE</a> callback.

## Syntax
````
typedef struct _CMP_NOTIFY_INFO {
  HANDLE hPlug;
  AV_PCR Pcr;
  PVOID  Context;
} CMP_NOTIFY_INFO, *PCMP_NOTIFY_INFO;
````

## Members


`hPlug`

The handle of a plug for the notification.

`Pcr`

A plug control register.

`Context`

A context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>