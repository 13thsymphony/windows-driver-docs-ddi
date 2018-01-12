---
UID: NE:iddcx.IDDCX_CURSOR_SHAPE_TYPE
title: IDDCX_CURSOR_SHAPE_TYPE
author: windows-driver-content
description: Describes the type of cursor.
old-location: display\iddcx_cursor_shape_type.htm
old-project: display
ms.assetid: 8aced7c9-e1be-4ec0-8b59-77cee011a71e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_CURSOR_SHAPE_TYPE,
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
req.alt-api: IDDCX_CURSOR_SHAPE_TYPE
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
req.typenames: 
---

# IDDCX_CURSOR_SHAPE_TYPE enumeration



## -description

                    Describes the type of cursor.
                



## -syntax

````
typedef enum _IDDCX_CURSOR_SHAPE_TYPE { 
  IDDCX_CURSOR_SHAPE_TYPE_UNINITIALIZED  = 0,
  IDDCX_CURSOR_SHAPE_TYPE_MASKED_COLOR   = 1,
  IDDCX_CURSOR_SHAPE_TYPE_ALPHA          = 2
} IDDCX_CURSOR_SHAPE_TYPE;
````


## -enum-fields

### -field IDDCX_CURSOR_SHAPE_TYPE_UNINITIALIZED


                        
                    Indicates that the cursor shape is uninitialized


### -field IDDCX_CURSOR_SHAPE_TYPE_MASKED_COLOR


                        Indicates this is a masked-color cursor shape
                    


### -field IDDCX_CURSOR_SHAPE_TYPE_ALPHA


                        Indicates this is a 32bpp alpha cursor
                    


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