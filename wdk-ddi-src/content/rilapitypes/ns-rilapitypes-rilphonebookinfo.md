---
UID: NS:rilapitypes.RILPHONEBOOKINFO
title: RILPHONEBOOKINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookinfo.htm
old-project: netvista
ms.assetid: 626bfc9b-6d84-4b8c-89eb-c635d0cb61f0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILPHONEBOOKINFO, RILPHONEBOOKINFO, RILPHONEBOOKINFO structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookinfo, ntddrilapitypes/RILPHONEBOOKINFO"
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
-	RILPHONEBOOKINFO
product:
- Windows
targetos: Windows
req.typenames: RILPHONEBOOKINFO, *LPRILPHONEBOOKINFO
req.product: Windows 10 or later.
---

# RILPHONEBOOKINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILPHONEBOOKINFO {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwUsed;
  DWORD dwTotal;
  DWORD dwMaxAddressLength;
  DWORD dwMaxTextLength;
  DWORD dwMaxAdditionalNumbers;
  DWORD dwMaxAdditionalNumberLength;
  DWORD dwMaxAdditionalNumberTextLength;
  DWORD dwUsedAdditionalNumberStrings;
  DWORD dwTotalAdditionalNumberStrings;
  DWORD dwMaxEmails;
  DWORD dwMaxEmailAddressLength;
  DWORD dwMaxGroups;
  DWORD dwMaxGroupStringLength;
  DWORD dwUsedGroupStrings;
  DWORD dwTotalGroupStrings;
  DWORD dwMaxSecondNameStringLength;
}  *LPRILPHONEBOOKINFO;
```

## Members


`cbSize`



`dwParams`



`dwUsed`



`dwTotal`



`dwMaxAddressLength`



`dwMaxTextLength`



`dwMaxAdditionalNumbers`



`dwMaxAdditionalNumberLength`



`dwMaxAdditionalNumberTextLength`



`dwUsedAdditionalNumberStrings`



`dwTotalAdditionalNumberStrings`



`dwMaxEmails`



`dwMaxEmailAddressLength`



`dwMaxGroups`



`dwMaxGroupStringLength`



`dwUsedGroupStrings`



`dwTotalGroupStrings`



`dwMaxSecondNameStringLength`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |