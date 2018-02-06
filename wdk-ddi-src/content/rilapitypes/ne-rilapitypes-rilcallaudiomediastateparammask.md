---
UID: NE:rilapitypes.RILCALLAUDIOMEDIASTATEPARAMMASK
title: RILCALLAUDIOMEDIASTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastateparammask_2.htm
old-project: netvista
ms.assetid: cc13d98b-0516-49bf-b92c-5ed6b1c6b5b2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallaudiomediastateparammask_2, rilapitypes/RILCALLAUDIOMEDIASTATEPARAMMASK, RILCALLAUDIOMEDIASTATEPARAMMASK, RIL_PARAM_CALLAUDIO_ALL, RIL_PARAM_CALLAUDIO_FLAGS, RILCALLAUDIOMEDIASTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_CALLAUDIO_ALL, rilapitypes/RIL_PARAM_CALLAUDIO_QUALITY, RIL_PARAM_CALLAUDIO_QUALITY, rilapitypes/RIL_PARAM_CALLAUDIO_FLAGS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
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