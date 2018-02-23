---
UID: NS:rilapitypes.GETDEVICEINFORESPONSE
title: GETDEVICEINFORESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\getdeviceinforesponse_2.htm
old-project: netvista
ms.assetid: 318927ab-6134-4a01-bf9c-a85619d2bbdf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.getdeviceinforesponse_2, *LPGETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE structure [Network Drivers Starting with Windows Vista], rilapitypes/GETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	GETDEVICEINFORESPONSE
product: Windows
targetos: Windows
req.typenames: GETDEVICEINFORESPONSE, *LPGETDEVICEINFORESPONSE
req.product: Windows 10 or later.
---

# GETDEVICEINFORESPONSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _GETDEVICEINFORESPONSE {
  char [MAXLENGTH_ADDRESS] Result;
} GETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE;
````

## Members


`Result`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |