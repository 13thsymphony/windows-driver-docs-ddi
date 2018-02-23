---
UID: NS:rilapitypes.RILCALLERIDSETTINGS
title: RILCALLERIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalleridsettings_2.htm
old-project: netvista
ms.assetid: 129fcbf9-8162-494a-a571-5c604849d387
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RILCALLERIDSETTINGS, RILCALLERIDSETTINGS, RILCALLERIDSETTINGS structure [Network Drivers Starting with Windows Vista], *LPRILCALLERIDSETTINGS, netvista.rilcalleridsettings_2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLERIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILCALLERIDSETTINGS, *LPRILCALLERIDSETTINGS
req.product: Windows 10 or later.
---

# RILCALLERIDSETTINGS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLERIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILCALLERIDSETTINGS, RILCALLERIDSETTINGS;
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
| **Header** | rilapitypes.h |