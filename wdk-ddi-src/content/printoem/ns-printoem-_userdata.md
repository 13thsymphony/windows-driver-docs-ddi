---
UID: NS:printoem._USERDATA
title: "_USERDATA"
author: windows-driver-content
description: The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure.
old-location: print\userdata.htm
old-project: print
ms.assetid: 5d4e5454-f44f-483a-a389-c8973263fbaa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_unidrv-pscript_ui_d0e62306-f4b7-491e-83b3-b1e2ddaddfb5.xml, PUSERDATA, print.userdata, *PUSERDATA, USERDATA, _USERDATA, printoem/PUSERDATA, printoem/USERDATA, USERDATA structure [Print Devices], PUSERDATA structure pointer [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
apiname:
-	USERDATA
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# _USERDATA structure
The USERDATA structure is used by <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> and <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> to specify additional information about printer features. A USERDATA structure pointer is supplied as the <b>UserData</b> member for each <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure.

## Syntax
````
typedef struct _USERDATA {
  DWORD     dwSize;
  ULONG_PTR dwItemID;
  PSTR      pKeyWordName;
  DWORD     dwReserved[8];
} USERDATA, *PUSERDATA;
````

## Members


`dwItemID`

Printer feature identifier.

`dwReserved`

Reserved.

`dwSize`

Size, in bytes, of the USERDATA structure.

`pKeyWordName`

Pointer to a nonlocalized text string identifying a printer feature.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | printoem.h (include Printoem.h) |