---
UID: NS:ntddrilapitypes.RILCHANGECALLBARRINGPASSWORDPARAMS
title: RILCHANGECALLBARRINGPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangecallbarringpasswordparams.htm
old-project: netvista
ms.assetid: 9b90f85e-091f-465d-a6e2-fa4ad66489ff
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCHANGECALLBARRINGPASSWORDPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILCHANGECALLBARRINGPASSWORDPARAMS, *LPRILCHANGECALLBARRINGPASSWORDPARAMS, netvista.rilchangecallbarringpasswordparams, RILCHANGECALLBARRINGPASSWORDPARAMS
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
-	RILCHANGECALLBARRINGPASSWORDPARAMS
product: Windows
targetos: Windows
req.typenames: RILCHANGECALLBARRINGPASSWORDPARAMS, *LPRILCHANGECALLBARRINGPASSWORDPARAMS
---

# RILCHANGECALLBARRINGPASSWORDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCHANGECALLBARRINGPASSWORDPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  char [256]                      szOldPassword;
  char [256]                      szNewPassword;
  char [256]                      szConfirmPassword;
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
| **Header** | ntddrilapitypes.h |