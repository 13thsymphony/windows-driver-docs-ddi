---
UID: NS:rilapitypes.RILPHONEBOOKEMAILADDRESS
title: RILPHONEBOOKEMAILADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookemailaddress_2.htm
old-project: netvista
ms.assetid: 322939c8-c7c9-405b-9f78-08ae9c642b42
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILPHONEBOOKEMAILADDRESS structure [Network Drivers Starting with Windows Vista], RILPHONEBOOKEMAILADDRESS, netvista.rilphonebookemailaddress_2, *LPRILPHONEBOOKEMAILADDRESS, rilapitypes/RILPHONEBOOKEMAILADDRESS
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
-	RILPHONEBOOKEMAILADDRESS
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKEMAILADDRESS, *LPRILPHONEBOOKEMAILADDRESS
req.product: Windows 10 or later.
---

# RILPHONEBOOKEMAILADDRESS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKEMAILADDRESS {
  DWORD                           cbSize;
  DWORD                           dwParams;
  WCHAR [MAXLENGTH_PHONEBOOKTEXT] wszAddress;
} RILPHONEBOOKEMAILADDRESS, RILPHONEBOOKEMAILADDRESS;
````

## Members


`cbSize`



`dwParams`



`wszAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |