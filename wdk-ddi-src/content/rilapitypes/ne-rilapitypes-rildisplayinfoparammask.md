---
UID: NE:rilapitypes.RILDISPLAYINFOPARAMMASK
title: RILDISPLAYINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfoparammask.htm
old-project: netvista
ms.assetid: deb9da97-7a61-4642-bebd-ab0e4082b410
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILDISPLAYINFOPARAMMASK, RILDISPLAYINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_DISPLAY_ALL, RIL_PARAM_DISPLAY_MESSAGE, RIL_PARAM_DISPLAY_MESSAGESIZE, RIL_PARAM_DISPLAY_TAG, RIL_PARAM_DISPLAY_TYPE, netvista.rildisplayinfoparammask, ntddrilapitypes/RILDISPLAYINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_DISPLAY_ALL, ntddrilapitypes/RIL_PARAM_DISPLAY_MESSAGE, ntddrilapitypes/RIL_PARAM_DISPLAY_MESSAGESIZE, ntddrilapitypes/RIL_PARAM_DISPLAY_TAG, ntddrilapitypes/RIL_PARAM_DISPLAY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	RILDISPLAYINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDISPLAYINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILDISPLAYINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDISPLAYINFOPARAMMASK { 
  RIL_PARAM_DISPLAY_TYPE,
  RIL_PARAM_DISPLAY_TAG,
  RIL_PARAM_DISPLAY_MESSAGESIZE,
  RIL_PARAM_DISPLAY_MESSAGE,
  RIL_PARAM_DISPLAY_ALL
} RILDISPLAYINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_TYPE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_TAG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_MESSAGESIZE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_MESSAGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DISPLAY_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |