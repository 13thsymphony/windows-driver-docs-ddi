---
UID: NS:rilapitypes.RILRESETMODEMCONFIGITEM
title: RILRESETMODEMCONFIGITEM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemconfigitem.htm
old-project: netvista
ms.assetid: 4e823f87-662c-491f-b368-f853f381e4b8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM, RILRESETMODEMCONFIGITEM structure [Network Drivers Starting with Windows Vista], netvista.rilresetmodemconfigitem, ntddrilapitypes/RILRESETMODEMCONFIGITEM"
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
-	RILRESETMODEMCONFIGITEM
product:
- Windows
targetos: Windows
req.typenames: RILRESETMODEMCONFIGITEM, *LPRILRESETMODEMCONFIGITEM
req.product: Windows 10 or later.
---

# RILRESETMODEMCONFIGITEM structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILRESETMODEMCONFIGITEM {
  DWORD                    dwModemConfigItem;
  RILRESETMODEMCONFIGVALUE rrmcValue;
}  *LPRILRESETMODEMCONFIGITEM;
```

## Members


`dwModemConfigItem`



`rrmcValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |