---
UID: NS:ntddrilapitypes.RILCAPSLOCKINGPWDLENGTH
title: RILCAPSLOCKINGPWDLENGTH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcapslockingpwdlength.htm
old-project: netvista
ms.assetid: 99f21862-5cd6-4bf9-abde-d5d24332a147
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH structure [Network Drivers Starting with Windows Vista], netvista.rilcapslockingpwdlength, ntddrilapitypes/RILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH"
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
-	RILCAPSLOCKINGPWDLENGTH
product: Windows
targetos: Windows
req.typenames: "*LPRILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH"
---

# RILCAPSLOCKINGPWDLENGTH structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCAPSLOCKINGPWDLENGTH {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwPersoFeature;
  DWORD  dwPasswordLength;
} RILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH;
````

## Members


`cbSize`



`dwParams`



`dwPasswordLength`



`dwPersoFeature`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |