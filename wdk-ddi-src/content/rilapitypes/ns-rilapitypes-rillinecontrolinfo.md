---
UID: NS:rilapitypes.RILLINECONTROLINFO
title: RILLINECONTROLINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillinecontrolinfo_2.htm
old-project: netvista
ms.assetid: 490ef6ed-c5df-450f-acd1-36091ac8999e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILLINECONTROLINFO structure [Network Drivers Starting with Windows Vista], RILLINECONTROLINFO, rilapitypes/RILLINECONTROLINFO, *LPRILLINECONTROLINFO, netvista.rillinecontrolinfo_2
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
-	RILLINECONTROLINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILLINECONTROLINFO, RILLINECONTROLINFO"
req.product: Windows 10 or later.
---

# RILLINECONTROLINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILLINECONTROLINFO {
  DWORD  cbSize;
  DWORD  dwExecutor;
  BOOL   fPolarityIncluded;
  BOOL   fToggleMode;
  BOOL   fReversePolarity;
  DWORD  dwPowerDenialTime;
} RILLINECONTROLINFO, RILLINECONTROLINFO;
````

## Members


`cbSize`



`dwExecutor`



`dwPowerDenialTime`



`fPolarityIncluded`



`fReversePolarity`



`fToggleMode`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |