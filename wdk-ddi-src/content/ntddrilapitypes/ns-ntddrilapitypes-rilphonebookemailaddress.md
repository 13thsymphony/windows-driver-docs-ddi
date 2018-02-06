---
UID: NS:ntddrilapitypes.RILPHONEBOOKEMAILADDRESS
title: RILPHONEBOOKEMAILADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookemailaddress.htm
old-project: netvista
ms.assetid: 89dc64a4-dce9-4ed2-a657-d216d502cded
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILPHONEBOOKEMAILADDRESS structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookemailaddress, RILPHONEBOOKEMAILADDRESS, *LPRILPHONEBOOKEMAILADDRESS, ntddrilapitypes/RILPHONEBOOKEMAILADDRESS
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
-	RILPHONEBOOKEMAILADDRESS
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKEMAILADDRESS, *LPRILPHONEBOOKEMAILADDRESS
---

# RILPHONEBOOKEMAILADDRESS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKEMAILADDRESS {
  DWORD       cbSize;
  DWORD       dwParams;
  WCHAR [256] wszAddress;
} RILPHONEBOOKEMAILADDRESS, RILPHONEBOOKEMAILADDRESS;
````

## Members


`cbSize`



`dwParams`



`wszAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |