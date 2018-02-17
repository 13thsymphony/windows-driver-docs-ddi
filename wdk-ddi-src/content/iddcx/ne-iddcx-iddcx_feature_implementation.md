---
UID: NE:iddcx.IDDCX_FEATURE_IMPLEMENTATION
title: IDDCX_FEATURE_IMPLEMENTATION
author: windows-driver-content
description: Enum used to indicate how a given supported feature is implemented.
old-location: display\iddcx_feature_implementation.htm
old-project: display
ms.assetid: 7bed6940-3f69-4cc0-b746-98cd7441f4b8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_FEATURE_IMPLEMENTATION enumeration [Display Devices], iddcx/IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE, IDDCX_FEATURE_IMPLEMENTATION_NONE, IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE, iddcx/IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED, IDDCX_FEATURE_IMPLEMENTATION, IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED, iddcx/IDDCX_FEATURE_IMPLEMENTATION_NONE, IDDCX_FEATURE_IMPLEMENTATION_HARDWARE, iddcx/IDDCX_FEATURE_IMPLEMENTATION, display.iddcx_feature_implementation, iddcx/IDDCX_FEATURE_IMPLEMENTATION_HARDWARE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
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
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDDCX_FEATURE_IMPLEMENTATION
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FEATURE_IMPLEMENTATION Enumeration
Enum used to indicate how a given supported feature is implemented

## Syntax
````
typedef enum _IDDCX_FEATURE_IMPLEMENTATION { 
  IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED  = 0,
  IDDCX_FEATURE_IMPLEMENTATION_NONE           = 1,
  IDDCX_FEATURE_IMPLEMENTATION_HARDWARE       = 2,
  IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE       = 3
} IDDCX_FEATURE_IMPLEMENTATION;
````

## Constants

<table>
            
                <tr>
                    <td>IDDCX_FEATURE_IMPLEMENTATION_HARDWARE</td>
                    <td>The feature is implemented and hardware is used in the implementation. For example, the adapter/ display pipeline blends the hardware cursor image into the signal sent to the monitor.</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FEATURE_IMPLEMENTATION_NONE</td>
                    <td>The feature is not implemented</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE</td>
                    <td>The feature is implemented and software is used in the implementation. For example, the driver/ support hardware cursor by blending the cursor image into the display pixels as part of the processing.</td>
                </tr>
            
                <tr>
                    <td>IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED</td>
                    <td>Indicates that an <b>IDDCX_FEATURE_IMPLEMENTATION</b> variable has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>UINT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |