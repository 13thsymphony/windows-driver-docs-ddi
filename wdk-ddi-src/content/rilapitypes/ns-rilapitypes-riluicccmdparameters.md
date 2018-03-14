---
UID: NS:rilapitypes.RILUICCCMDPARAMETERS
title: RILUICCCMDPARAMETERS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccmdparameters.htm
old-project: netvista
ms.assetid: 02c37c3d-fa5b-4d26-a092-09f6f3dbd46c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS structure [Network Drivers Starting with Windows Vista], netvista.riluicccmdparameters, ntddrilapitypes/RILUICCCMDPARAMETERS"
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
-	RILUICCCMDPARAMETERS
product: Windows
targetos: Windows
req.typenames: RILUICCCMDPARAMETERS, *LPRILUICCCMDPARAMETERS
req.product: Windows 10 or later.
---

# RILUICCCMDPARAMETERS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCCMDPARAMETERS {
  DWORD            cbSize;
  DWORD            dwParams;
  RILUICCFILEPATH  filePath;
  DWORD            dwParameter1;
  DWORD            dwParameter2;
  DWORD            dwParameter3;
} RILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS;
````

## Members


`cbSize`



`dwParameter1`



`dwParameter2`



`dwParameter3`



`dwParams`



`filePath`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |