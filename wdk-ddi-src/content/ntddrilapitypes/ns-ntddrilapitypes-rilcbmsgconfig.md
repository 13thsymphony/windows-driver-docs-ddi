---
UID: NS:ntddrilapitypes.RILCBMSGCONFIG
title: RILCBMSGCONFIG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbmsgconfig.htm
old-project: netvista
ms.assetid: c59f26b7-47ce-4bf9-b678-a2bb48c69754
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILCBMSGCONFIG, RILCBMSGCONFIG structure [Network Drivers Starting with Windows Vista], netvista.rilcbmsgconfig, RILCBMSGCONFIG, ntddrilapitypes/RILCBMSGCONFIG"
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
-	RILCBMSGCONFIG
product: Windows
targetos: Windows
req.typenames: "*LPRILCBMSGCONFIG, RILCBMSGCONFIG"
---

# RILCBMSGCONFIG structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCBMSGCONFIG {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwGWLConfigInfoSize;
  RILCBGWLCONFIGINFO [50]  GWLConfigInfo;
  DWORD                    dwCDMAConfigInfoSize;
  RILCBCDMACONFIGINFO [50] CDMAConfigInfo;
} RILCBMSGCONFIG, RILCBMSGCONFIG;
````

## Members


`cbSize`



`CDMAConfigInfo`



`dwCDMAConfigInfoSize`



`dwGWLConfigInfoSize`



`dwParams`



`GWLConfigInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |