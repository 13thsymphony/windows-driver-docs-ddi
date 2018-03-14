---
UID: NS:ntddrilapitypes.RILCALLWAITINGINFO
title: RILCALLWAITINGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallwaitinginfo.htm
old-project: netvista
ms.assetid: 526ce708-93bb-43f2-9d78-b3e8360e01da
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILCALLWAITINGINFO, RILCALLWAITINGINFO, RILCALLWAITINGINFO structure [Network Drivers Starting with Windows Vista], netvista.rilcallwaitinginfo, ntddrilapitypes/RILCALLWAITINGINFO"
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
-	RILCALLWAITINGINFO
product: Windows
targetos: Windows
req.typenames: RILCALLWAITINGINFO, *LPRILCALLWAITINGINFO
---

# RILCALLWAITINGINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLWAITINGINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  RILCALLTYPE         dwCallType;
  RILREMOTEPARTYINFO  rrpiCallerInfo;
} RILCALLWAITINGINFO, RILCALLWAITINGINFO;
````

## Members


`cbSize`



`dwCallType`



`dwExecutor`



`dwParams`



`rrpiCallerInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |