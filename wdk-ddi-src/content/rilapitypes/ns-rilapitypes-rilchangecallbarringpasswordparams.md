---
UID: NS:rilapitypes.RILCHANGECALLBARRINGPASSWORDPARAMS
title: RILCHANGECALLBARRINGPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangecallbarringpasswordparams_2.htm
old-project: netvista
ms.assetid: 1a9dda19-329b-4046-bba1-1bbedf37fa31
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILCHANGECALLBARRINGPASSWORDPARAMS, *LPRILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilchangecallbarringpasswordparams_2
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
-	RILCHANGECALLBARRINGPASSWORDPARAMS
product: Windows
targetos: Windows
req.typenames: RILCHANGECALLBARRINGPASSWORDPARAMS, *LPRILCHANGECALLBARRINGPASSWORDPARAMS
req.product: Windows 10 or later.
---

# RILCHANGECALLBARRINGPASSWORDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCHANGECALLBARRINGPASSWORDPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  char [MAXLENGTH_PASSWORD]       szOldPassword;
  char [MAXLENGTH_PASSWORD]       szNewPassword;
  char [MAXLENGTH_PASSWORD]       szConfirmPassword;
} RILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS;
````

## Members


`dwExecutor`



`dwType`



`szConfirmPassword`



`szNewPassword`



`szOldPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |