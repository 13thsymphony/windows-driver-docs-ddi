---
UID: NS:ntddrilapitypes.GETDEVICEINFORESPONSE
title: GETDEVICEINFORESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\getdeviceinforesponse.htm
old-project: netvista
ms.assetid: 312b60ba-9df4-4171-a831-ab402cc99664
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPGETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE structure [Network Drivers Starting with Windows Vista], netvista.getdeviceinforesponse, ntddrilapitypes/GETDEVICEINFORESPONSE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
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
-	kbSyntax
api_type:
-	<TBD>
api_location:
-
api_name:
-	GETDEVICEINFORESPONSE
product: Windows
targetos: Windows
req.typenames: GETDEVICEINFORESPONSE, *LPGETDEVICEINFORESPONSE
---

# GETDEVICEINFORESPONSE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _GETDEVICEINFORESPONSE {
  char [256] Result;
} GETDEVICEINFORESPONSE, GETDEVICEINFORESPONSE;
````

## Members


`Result`

TBD


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Ntddrilapitypes.h) |