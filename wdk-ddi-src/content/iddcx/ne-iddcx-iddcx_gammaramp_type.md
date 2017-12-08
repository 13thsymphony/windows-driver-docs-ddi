---
UID: NE.iddcx.IDDCX_GAMMARAMP_TYPE
title: IDDCX_GAMMARAMP_TYPE
author: windows-driver-content
description: An enumeration indicating the type of gamma ramp being set.
old-location: display\iddcx_gammaramp_type.htm
old-project: display
ms.assetid: 40fa5169-e295-429c-a63d-3e4ab9c14672
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IDDCX_GAMMARAMP_TYPE,
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
req.alt-api: IDDCX_GAMMARAMP_TYPE
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
---

# IDDCX_GAMMARAMP_TYPE enumeration



## -description

                     An enumeration indicating the type of gamma ramp being set
                


## -syntax

````
typedef enum _IDDCX_GAMMARAMP_TYPE { 
  IDDCX_GAMMARAMP_TYPE_UNINITIALIZED  = 0,
  IDDCX_GAMMARAMP_TYPE_DEFAULT        = 1,
  IDDCX_GAMMARAMP_TYPE_RGB256x3x16    = 2
} IDDCX_GAMMARAMP_TYPE;
````


## -enum-fields

### -field IDDCX_GAMMARAMP_TYPE_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_GAMMARAMP_TYPE</b> variable has not yet been assigned a meaningful value.

### -field IDDCX_GAMMARAMP_TYPE_DEFAULT


                        The gamma ramp is the default ramp
                    

### -field IDDCX_GAMMARAMP_TYPE_RGB256x3x16


                        Indicates that the gamma lookup table contains three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.
                    

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>