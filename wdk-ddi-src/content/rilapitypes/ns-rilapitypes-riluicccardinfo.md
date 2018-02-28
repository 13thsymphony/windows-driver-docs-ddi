---
UID: NS:rilapitypes.RILUICCCARDINFO
title: RILUICCCARDINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfo_2.htm
old-project: netvista
ms.assetid: c49d538c-49c9-43ba-bc97-324706a5a5b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILUICCCARDINFO, RILUICCCARDINFO, RILUICCCARDINFO structure [Network Drivers Starting with Windows Vista], netvista.riluicccardinfo_2, rilapitypes/RILUICCCARDINFO"
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
-	RILUICCCARDINFO
product: Windows
targetos: Windows
req.typenames: RILUICCCARDINFO, *LPRILUICCCARDINFO
req.product: Windows 10 or later.
---

# RILUICCCARDINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCCARDINFO {
  DWORD                  cbSize;
  DWORD                  dwParams;
  BOOL                   fIsVirtualCard;
  BYTE [MAXLENGTH_ICCID] IccId;
  DWORD                  dwNumApps;
  RILUICCAPPINFO [1]     AppInfo;
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
| **Header** | rilapitypes.h |