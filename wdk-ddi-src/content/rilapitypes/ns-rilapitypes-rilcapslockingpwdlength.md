---
UID: NS:rilapitypes.RILCAPSLOCKINGPWDLENGTH
title: RILCAPSLOCKINGPWDLENGTH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcapslockingpwdlength.htm
old-project: netvista
ms.assetid: 99f21862-5cd6-4bf9-abde-d5d24332a147
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH, RILCAPSLOCKINGPWDLENGTH structure [Network Drivers Starting with Windows Vista], netvista.rilcapslockingpwdlength, ntddrilapitypes/RILCAPSLOCKINGPWDLENGTH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	RILCAPSLOCKINGPWDLENGTH
product:
- Windows
targetos: Windows
req.typenames: RILCAPSLOCKINGPWDLENGTH, *LPRILCAPSLOCKINGPWDLENGTH
req.product: Windows 10 or later.
---

# RILCAPSLOCKINGPWDLENGTH structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILCAPSLOCKINGPWDLENGTH {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwPersoFeature;
  DWORD dwPasswordLength;
}  *LPRILCAPSLOCKINGPWDLENGTH;
```

## Members


`cbSize`



`dwParams`



`dwPersoFeature`



`dwPasswordLength`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |