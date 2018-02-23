---
UID: NS:ntddrilapitypes.RILMSGSERVICEINFO
title: RILMSGSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfo.htm
old-project: netvista
ms.assetid: 21b1c6ef-b8f3-4230-bc3f-7ac19c6cb2d1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGSERVICEINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILMSGSERVICEINFO, netvista.rilmsgserviceinfo, RILMSGSERVICEINFO, *LPRILMSGSERVICEINFO
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
-	RILMSGSERVICEINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGSERVICEINFO, RILMSGSERVICEINFO"
---

# RILMSGSERVICEINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGSERVICEINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwMsgSupport;
  DWORD  dwStoreUsed;
  DWORD  dwStoreTotal;
} RILMSGSERVICEINFO, RILMSGSERVICEINFO;
````

## Members


`cbSize`



`dwMsgSupport`



`dwParams`



`dwStoreTotal`



`dwStoreUsed`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |