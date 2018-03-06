---
UID: NE:rilapitypes.RILCALLVIDEOMEDIASTATEPARAMMASK
title: RILCALLVIDEOMEDIASTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallvideomediastateparammask_2.htm
old-project: netvista
ms.assetid: 4cd834ba-c2f0-4b48-bc24-adf1cf2610f8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCALLVIDEOMEDIASTATEPARAMMASK, RILCALLVIDEOMEDIASTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_CALLVIDEO_ALL, RIL_PARAM_CALLVIDEO_CONTEXTID, RIL_PARAM_CALLVIDEO_FLAGS, netvista.rilcallvideomediastateparammask_2, rilapitypes/RILCALLVIDEOMEDIASTATEPARAMMASK, rilapitypes/RIL_PARAM_CALLVIDEO_ALL, rilapitypes/RIL_PARAM_CALLVIDEO_CONTEXTID, rilapitypes/RIL_PARAM_CALLVIDEO_FLAGS
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
-	RILCALLVIDEOMEDIASTATEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLVIDEOMEDIASTATEPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLVIDEOMEDIASTATEPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLVIDEOMEDIASTATEPARAMMASK { 
  RIL_PARAM_CALLVIDEO_FLAGS,
  RIL_PARAM_CALLVIDEO_CONTEXTID,
  RIL_PARAM_CALLVIDEO_ALL
} RILCALLVIDEOMEDIASTATEPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CALLVIDEO_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLVIDEO_CONTEXTID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLVIDEO_FLAGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CALLVIDEO_PEERCAPABILITIES</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |