---
UID: NE:rilapitypes.RILCALLAUDIOMEDIASTATEPARAMMASK
title: RILCALLAUDIOMEDIASTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastateparammask_2.htm
old-project: netvista
ms.assetid: cc13d98b-0516-49bf-b92c-5ed6b1c6b5b2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLAUDIOMEDIASTATEPARAMMASK, RILCALLAUDIOMEDIASTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CALLAUDIO_ALL, RIL_PARAM_CALLAUDIO_FLAGS, RIL_PARAM_CALLAUDIO_QUALITY, netvista.rilcallaudiomediastateparammask_2, rilapitypes/RILCALLAUDIOMEDIASTATEPARAMMASK, rilapitypes/RIL_PARAM_CALLAUDIO_ALL, rilapitypes/RIL_PARAM_CALLAUDIO_FLAGS, rilapitypes/RIL_PARAM_CALLAUDIO_QUALITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILCALLAUDIOMEDIASTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOMEDIASTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLAUDIOMEDIASTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLAUDIOMEDIASTATEPARAMMASK { 
  RIL_PARAM_CALLAUDIO_QUALITY,
  RIL_PARAM_CALLAUDIO_FLAGS,
  RIL_PARAM_CALLAUDIO_ALL
} RILCALLAUDIOMEDIASTATEPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CALLAUDIO_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLAUDIO_FLAGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLAUDIO_QUALITY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLAUDIO_SOURCE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |