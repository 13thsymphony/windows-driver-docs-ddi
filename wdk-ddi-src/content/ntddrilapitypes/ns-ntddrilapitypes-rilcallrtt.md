---
UID: NS:ntddrilapitypes.RILCALLRTT
title: RILCALLRTT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrtt.htm
old-project: netvista
ms.assetid: aa69cc11-66c7-4d23-b596-c37472af484a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCALLRTT, RILCALLRTT, RILCALLRTT structure [Network Drivers Starting with Windows Vista], netvista.rilcallrtt, ntddrilapitypes/RILCALLRTT"
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
-	RILCALLRTT
product: Windows
targetos: Windows
req.typenames: RILCALLRTT, *LPRILCALLRTT
---

# RILCALLRTT structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCALLRTT {
  RILCALLRTTACTION dwRTTAction;
  RILCALLRTTMODE   dwRTTModeType;
  RILCALLRTTCAP    stRTTCap;
}  *LPRILCALLRTT;
```

## Members


`dwRTTAction`



`dwRTTModeType`



`stRTTCap`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |