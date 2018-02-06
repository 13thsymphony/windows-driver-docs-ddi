---
UID: NS:ntddrilapitypes.RILHIDECONNECTEDIDSETTINGS
title: RILHIDECONNECTEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettings.htm
old-project: netvista
ms.assetid: a0445969-b4b5-43f3-a8dc-a8d61bf44d94
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILHIDECONNECTEDIDSETTINGS, *LPRILHIDECONNECTEDIDSETTINGS, netvista.rilhideconnectedidsettings, ntddrilapitypes/RILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS structure [Network Drivers Starting with Windows Vista]
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
-	RILHIDECONNECTEDIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILHIDECONNECTEDIDSETTINGS, *LPRILHIDECONNECTEDIDSETTINGS
---

# RILHIDECONNECTEDIDSETTINGS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILHIDECONNECTEDIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS;
````

## Members


`cbSize`



`dwExecutor`



`dwParams`



`dwProvisioning`



`dwStatus`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |