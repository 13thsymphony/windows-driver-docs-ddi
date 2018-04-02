---
UID: NS:ntddrilapitypes.RILMESSAGE
title: RILMESSAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessage.htm
old-project: netvista
ms.assetid: b776b060-79bf-4848-807d-1999d38075ad
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILMESSAGE, RILMESSAGE, RILMESSAGE structure [Network Drivers Starting with Windows Vista], netvista.rilmessage, ntddrilapitypes/RILMESSAGE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILMESSAGE
product:
- Windows
targetos: Windows
req.typenames: RILMESSAGE, *LPRILMESSAGE
---

# RILMESSAGE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILMESSAGE {
  DWORD          cbSize;
  DWORD          dwParams;
  RILADDRESS     raSvcCtrAddress;
  RILMESSAGETYPE dwType;
  DWORD          dwFlags;
  union {
    RILMSGBCGENERAL     unMsgBcGeneral;
    RILMSGCDMAINDELIVER unMsgCDMAInDeliver;
    RILMSGCDMAOUTSUBMIT unMsgCDMAOutSubmit;
    RILMSGINDELIVER     unMsgInDeliver;
    RILMSGINSTATUS      unMsgInStatus;
    RILMSGIS637INSTATUS unMsgIS637InStatus;
    RILMSGOUTSUBMIT     unMsgOutSubmit;
  } msgUnion;
  RILMSGUNION    RILMSGUNION;
}  *LPRILMESSAGE;
```

## Members


`cbSize`



`dwParams`



`raSvcCtrAddress`



`dwType`



`dwFlags`



`msgUnion`



`RILMSGUNION`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |