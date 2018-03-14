---
UID: NS:rilapitypes.RILMSGINSTATUS
title: RILMSGINSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsginstatus.htm
old-project: netvista
ms.assetid: 383ed544-c8c8-42a0-a7de-57f0f4072611
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILMSGINSTATUS, RILMSGINSTATUS, RILMSGINSTATUS structure [Network Drivers Starting with Windows Vista], netvista.rilmsginstatus, ntddrilapitypes/RILMSGINSTATUS"
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
-	RILMSGINSTATUS
product: Windows
targetos: Windows
req.typenames: RILMSGINSTATUS, *LPRILMSGINSTATUS
req.product: Windows 10 or later.
---

# RILMSGINSTATUS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGINSTATUS {
  DWORD                       dwMsgID;
  RILADDRESS                  raTgtRecipAddress;
  RILSYSTEMTIME               stTgtSCReceiveTime;
  RILSYSTEMTIME               stTgtDischargeTime;
  DWORD                       dwReserved;
  RILMSGINSTATUSTGTDLVSTATUS  dwTgtDlvStatus;
  RILMSGPROTOCOLID            dwProtocolID;
  RILMSGDCS                   rmdDataCoding;
  DWORD                       cbHdrLength;
  DWORD                       cchMsgLength;
  BYTE [256]                  rgbHdr;
  BYTE [512]                  rgbMsg;
} RILMSGINSTATUS, RILMSGINSTATUS;
````

## Members


`cbHdrLength`



`cchMsgLength`



`dwMsgID`



`dwProtocolID`



`dwReserved`



`dwTgtDlvStatus`



`raTgtRecipAddress`



`rgbHdr`



`rgbMsg`



`rmdDataCoding`



`stTgtDischargeTime`



`stTgtSCReceiveTime`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |