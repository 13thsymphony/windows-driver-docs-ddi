---
UID: NS:rilapitypes.RILPHONEBOOKENTRY
title: RILPHONEBOOKENTRY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookentry.htm
old-project: netvista
ms.assetid: 2741d992-624a-4fd1-a1b5-57fb39c42f84
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILPHONEBOOKENTRY, RILPHONEBOOKENTRY, RILPHONEBOOKENTRY structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookentry, ntddrilapitypes/RILPHONEBOOKENTRY"
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
-	RILPHONEBOOKENTRY
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKENTRY, *LPRILPHONEBOOKENTRY
req.product: Windows 10 or later.
---

# RILPHONEBOOKENTRY structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKENTRY {
  DWORD       cbSize;
  DWORD       dwParams;
  DWORD       dwIndex;
  RILADDRESS  raAddress;
  WCHAR [256] wszText;
  WCHAR [256] wszSecondName;
  DWORD       dwGroupIdCount;
  DWORD [10]  rgdwGroupId;
  DWORD       dwAdditionalNumCount;
  DWORD       dwAdditionalNumSize;
  DWORD       dwAdditionalNumOffset;
  DWORD       dwEmailCount;
  DWORD       dwEmailSize;
  DWORD       dwEmailOffset;
} RILPHONEBOOKENTRY, RILPHONEBOOKENTRY;
````

## Members


`cbSize`



`dwParams`



`dwIndex`



`raAddress`



`wszText`



`wszSecondName`



`dwGroupIdCount`



`rgdwGroupId`



`dwAdditionalNumCount`



`dwAdditionalNumSize`



`dwAdditionalNumOffset`



`dwEmailCount`



`dwEmailSize`



`dwEmailOffset`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |