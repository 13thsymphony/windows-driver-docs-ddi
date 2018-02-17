---
UID: NS:ntddrilapitypes.RILUICCCARDINFO
title: RILUICCCARDINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfo.htm
old-project: netvista
ms.assetid: 761f1ab6-75e6-4c40-b79c-01f2e92df495
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILUICCCARDINFO, RILUICCCARDINFO structure [Network Drivers Starting with Windows Vista], RILUICCCARDINFO, *LPRILUICCCARDINFO, netvista.riluicccardinfo
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
-	RILUICCCARDINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCCARDINFO, RILUICCCARDINFO"
---

# RILUICCCARDINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCCARDINFO {
  DWORD              cbSize;
  DWORD              dwParams;
  BOOL               fIsVirtualCard;
  BYTE [10]          IccId;
  DWORD              dwNumApps;
  RILUICCAPPINFO [1] AppInfo;
} RILUICCCARDINFO, RILUICCCARDINFO;
````

## Members


`AppInfo`



`cbSize`



`dwNumApps`



`dwParams`



`fIsVirtualCard`



`IccId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |