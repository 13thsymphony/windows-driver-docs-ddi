---
UID: NS:rilapitypes.RILSYSTEMTIME
title: RILSYSTEMTIME
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemtime.htm
old-project: netvista
ms.assetid: da01963f-a0eb-4222-b0c7-20b924f65f66
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSYSTEMTIME, RILSYSTEMTIME, RILSYSTEMTIME structure [Network Drivers Starting with Windows Vista], netvista.rilsystemtime, ntddrilapitypes/RILSYSTEMTIME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILSYSTEMTIME
product: Windows
targetos: Windows
req.typenames: RILSYSTEMTIME, *LPRILSYSTEMTIME
req.product: Windows 10 or later.
---

# RILSYSTEMTIME structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSYSTEMTIME {
  WORD  wYear;
  WORD  wMonth;
  WORD  wDayOfWeek;
  WORD  wDay;
  WORD  wHour;
  WORD  wMinute;
  WORD  wSecond;
  WORD  wMilliseconds;
} RILSYSTEMTIME, RILSYSTEMTIME;
````

## Members


`wDay`



`wDayOfWeek`



`wHour`



`wMilliseconds`



`wMinute`



`wMonth`



`wSecond`



`wYear`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |