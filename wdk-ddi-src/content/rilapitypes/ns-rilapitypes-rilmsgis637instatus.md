---
UID: NS:rilapitypes.RILMSGIS637INSTATUS
title: RILMSGIS637INSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgis637instatus.htm
old-project: netvista
ms.assetid: ba87baa2-7d96-4418-bfbc-411bb4cda3fb
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMSGIS637INSTATUS, RILMSGIS637INSTATUS, RILMSGIS637INSTATUS structure [Network Drivers Starting with Windows Vista], netvista.rilmsgis637instatus, ntddrilapitypes/RILMSGIS637INSTATUS"
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
-	RILMSGIS637INSTATUS
product: Windows
targetos: Windows
req.typenames: RILMSGIS637INSTATUS, *LPRILMSGIS637INSTATUS
req.product: Windows 10 or later.
---

# RILMSGIS637INSTATUS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGIS637INSTATUS {
  RILADDRESS               raOrigAddress;
  RILSUBADDRESS            rsaOrigSubaddr;
  RILSYSTEMTIME            stSCReceiveTime;
  DWORD                    dwCauseCode;
  DWORD                    dwReplySeqNumber;
  DWORD                    dwUserResponseCode;
  RILMSGCDMAMSGSTATUSTYPE  dwMsgStatusType;
  DWORD                    dwMsgID;
  RILMSGCDMALANGUAGE       dwMsgLang;
  RILMSGCDMAMSGENCODING    dwMsgEncoding;
  DWORD                    cchMsgLength;
  BYTE [512]               rgbMsg;
} RILMSGIS637INSTATUS, RILMSGIS637INSTATUS;
````

## Members


`raOrigAddress`



`rsaOrigSubaddr`



`stSCReceiveTime`



`dwCauseCode`



`dwReplySeqNumber`



`dwUserResponseCode`



`dwMsgStatusType`



`dwMsgID`



`dwMsgLang`



`dwMsgEncoding`



`cchMsgLength`



`rgbMsg`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |