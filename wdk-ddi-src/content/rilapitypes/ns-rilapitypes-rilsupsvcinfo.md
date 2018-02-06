---
UID: NS:rilapitypes.RILSUPSVCINFO
title: RILSUPSVCINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcinfo_2.htm
old-project: netvista
ms.assetid: b3b86cf8-0e0c-4ed1-9d8c-6f2fef00b9cd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSUPSVCINFO, RILSUPSVCINFO structure [Network Drivers Starting with Windows Vista], *LPRILSUPSVCINFO, netvista.rilsupsvcinfo_2, rilapitypes/RILSUPSVCINFO
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
-	RILSUPSVCINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILSUPSVCINFO, RILSUPSVCINFO"
req.product: Windows 10 or later.
---

# RILSUPSVCINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSUPSVCINFO {
  DWORD                            cbSize;
  DWORD                            dwParams;
  DWORD                            dwExecutor;
  DWORD                            fFromNetwork;
  DWORD                            dwFailureReason;
  RILSUPSVCACTION                  dwSupSvcAction;
  RILCALLFORWARDINGSETTINGSREASON  dwCallForwardingReason;
  RILCALLBARRINGSTATUSPARAMSTYPE   dwCallBarringType;
  RILSUPSVCTYPE                    dwSupSvcType;
  DWORD                            dwInfoClasses;
  RILALPHAIDENTIFIER               aiIdentifier;
  char [MAXLENGTH_PASSWORD]        szCallBarringPassword;
  char [MAXLENGTH_PASSWORD]        szNewCallBarringPassword;
  RILCALLFORWARDINGSETTINGS        callForwardSettings;
  RILCALLERIDSETTINGS              callerIdSettings;
  RILDIALEDIDSETTINGS              dialedIdSettings;
  RILHIDEIDSETTINGS                hideIdSettings;
  RILHIDECONNECTEDIDSETTINGS       hideConnectedIdSettings;
  RILSUPSERVICEDATA                supServiceData;
} RILSUPSVCINFO, RILSUPSVCINFO;
````

## Members


`aiIdentifier`



`callerIdSettings`



`callForwardSettings`



`cbSize`



`dialedIdSettings`



`dwCallBarringType`



`dwCallForwardingReason`



`dwExecutor`



`dwFailureReason`



`dwInfoClasses`



`dwParams`



`dwSupSvcAction`



`dwSupSvcType`



`fFromNetwork`



`hideConnectedIdSettings`



`hideIdSettings`



`supServiceData`



`szCallBarringPassword`



`szNewCallBarringPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |