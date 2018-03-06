---
UID: NS:rilapitypes.RILIMSFAILURE
title: RILIMSFAILURE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailure_2.htm
old-project: netvista
ms.assetid: f9c25e60-8f9e-491f-898a-c79e8790193e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILIMSFAILURE, RILIMSFAILURE, RILIMSFAILURE structure [Network Drivers Starting with Windows Vista], netvista.rilimsfailure_2, rilapitypes/RILIMSFAILURE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILIMSFAILURE
product: Windows
targetos: Windows
req.typenames: RILIMSFAILURE, *LPRILIMSFAILURE
req.product: Windows 10 or later.
---

# RILIMSFAILURE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILIMSFAILURE {
  DWORD                                       cbSize;
  DWORD                                       dwParams;
  DWORD                                       dwExecutor;
  RILIMSFAILUREMESSAGETYPE                    dwMessageType;
  DWORD                                       dwMessageSubType;
  DWORD                                       dwErrorCode;
  WCHAR [MAXLENGTH_SIP_FAILURE_REASON_STRING] wszErrorString;
} RILIMSFAILURE, RILIMSFAILURE;
````

## Members


`cbSize`



`dwErrorCode`



`dwExecutor`



`dwMessageSubType`



`dwMessageType`



`dwParams`



`wszErrorString`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |