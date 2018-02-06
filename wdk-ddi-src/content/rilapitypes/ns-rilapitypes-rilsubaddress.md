---
UID: NS:rilapitypes.RILSUBADDRESS
title: RILSUBADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddress_2.htm
old-project: netvista
ms.assetid: fa8f7b01-a767-4713-b1e3-7417efb7db47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsubaddress_2, RILSUBADDRESS, *LPRILSUBADDRESS, rilapitypes/RILSUBADDRESS, RILSUBADDRESS structure [Network Drivers Starting with Windows Vista]
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
-	RILSUBADDRESS
product: Windows
targetos: Windows
req.typenames: "*LPRILSUBADDRESS, RILSUBADDRESS"
req.product: Windows 10 or later.
---

# RILSUBADDRESS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSUBADDRESS {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILSUBADDRESSTYPE         dwType;
  WCHAR [MAXLENGTH_SUBADDR] wszSubAddress;
} RILSUBADDRESS, RILSUBADDRESS;
````

## Members


`cbSize`



`dwParams`



`dwType`



`wszSubAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |