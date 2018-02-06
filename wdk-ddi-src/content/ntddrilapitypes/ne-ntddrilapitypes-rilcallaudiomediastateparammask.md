---
UID: NE:ntddrilapitypes.RILCALLAUDIOMEDIASTATEPARAMMASK
title: RILCALLAUDIOMEDIASTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastateparammask.htm
old-project: netvista
ms.assetid: ad016fd6-1fbf-4600-809b-b0a9b368a87b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILCALLAUDIOMEDIASTATEPARAMMASK, RILCALLAUDIOMEDIASTATEPARAMMASK, RIL_PARAM_CALLAUDIO_ALL, netvista.rilcallaudiomediastateparammask, ntddrilapitypes/RIL_PARAM_CALLAUDIO_QUALITY, RIL_PARAM_CALLAUDIO_FLAGS, RILCALLAUDIOMEDIASTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_PARAM_CALLAUDIO_ALL, ntddrilapitypes/RIL_PARAM_CALLAUDIO_FLAGS, RIL_PARAM_CALLAUDIO_QUALITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILCALLAUDIOMEDIASTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOMEDIASTATEPARAMMASK
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
| **Header** | ntddrilapitypes.h |