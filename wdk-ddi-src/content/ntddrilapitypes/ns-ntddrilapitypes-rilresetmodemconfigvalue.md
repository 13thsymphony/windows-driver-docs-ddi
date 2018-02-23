---
UID: NS:ntddrilapitypes.RILRESETMODEMCONFIGVALUE
title: RILRESETMODEMCONFIGVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigvalue.htm
old-project: netvista
ms.assetid: 48068d1d-3fe7-4bd6-8c91-094e4187ca1f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILRESETMODEMCONFIGVALUE, netvista.rilresetmodemconfigvalue, *LPRILRESETMODEMCONFIGVALUE, ntddrilapitypes/RILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILRESETMODEMCONFIGVALUE
product: Windows
targetos: Windows
req.typenames: RILRESETMODEMCONFIGVALUE, *LPRILRESETMODEMCONFIGVALUE
---

# RILRESETMODEMCONFIGVALUE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRESETMODEMCONFIGVALUE {
  DWORD                          cbSize;
  DWORD                          dwType;
  NULL                           RILRESETMODEMCONFIGVALUEUNION;
  RILRESETMODEMCONFIGVALUEUNION  configValueUnion;
  BOOL                           fValue;
  DWORD                          dwValue;
  WCHAR [256]                    wszValue;
} RILRESETMODEMCONFIGVALUE, RILRESETMODEMCONFIGVALUE;
````

## Members


`cbSize`



`configValueUnion`



`dwType`



`RILRESETMODEMCONFIGVALUEUNION`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |