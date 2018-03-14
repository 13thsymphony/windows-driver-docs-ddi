---
UID: NS:ntddrilapitypes.RILPSMEDIACONFIGURATION
title: RILPSMEDIACONFIGURATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediaconfiguration.htm
old-project: netvista
ms.assetid: 579a0943-0577-4dde-82d9-4794537e58f4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION structure [Network Drivers Starting with Windows Vista], netvista.rilpsmediaconfiguration, ntddrilapitypes/RILPSMEDIACONFIGURATION"
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
-	RILPSMEDIACONFIGURATION
product: Windows
targetos: Windows
req.typenames: RILPSMEDIACONFIGURATION, *LPRILPSMEDIACONFIGURATION
---

# RILPSMEDIACONFIGURATION structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPSMEDIACONFIGURATION {
  RILPSMEDIAPREFERENCE  dwMediaPreference;
  DWORD                 dwServiceType;
} RILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION;
````

## Members


`dwMediaPreference`



`dwServiceType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |