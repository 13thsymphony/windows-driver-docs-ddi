---
UID: NS:rilapitypes.RILUICCSLOTINFO
title: RILUICCSLOTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccslotinfo.htm
old-project: netvista
ms.assetid: 4f8ed150-b378-49c3-955c-a1e69ab8c1a9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*LPRILUICCSLOTINFO, RILUICCSLOTINFO, RILUICCSLOTINFO structure [Network Drivers Starting with Windows Vista], netvista.riluiccslotinfo, ntddrilapitypes/RILUICCSLOTINFO"
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
-	RILUICCSLOTINFO
product: Windows
targetos: Windows
req.typenames: RILUICCSLOTINFO, *LPRILUICCSLOTINFO
req.product: Windows 10 or later.
---

# RILUICCSLOTINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef struct RILUICCSLOTINFO {
  DWORD            cbSize;
  DWORD            dwParams;
  DWORD            dwNumOfUiccSlots;
  RILUICCSLOTSTATE dwSlotState[1];
} *LPRILUICCSLOTINFO, RILUICCSLOTINFO;
```

## Members


`cbSize`



`dwParams`



`dwNumOfUiccSlots`



`dwSlotState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |