---
UID: NE:iddcx.IDDCX_PATH_FLAGS
title: IDDCX_PATH_FLAGS
author: windows-driver-content
description: Indicates the state of the path.
old-location: display\iddcx_path_flags.htm
old-project: display
ms.assetid: f7a9b20a-753c-487d-a2d5-3e1c08317519
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_PATH_FLAGS,
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
req.alt-api: IDDCX_PATH_FLAGS
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

# IDDCX_PATH_FLAGS enumeration



## -description
Indicates the state of the path.
                    
                



## -syntax

````
typedef enum _IDDCX_PATH_FLAGS { 
  IDDCX_PATH_FLAGS_NONE     = 0,
  IDDCX_PATH_FLAGS_CHANGED  = 1,
  IDDCX_PATH_FLAGS_ACTIVE   = 2
} IDDCX_PATH_FLAGS;
````


## -enum-fields

### -field IDDCX_PATH_FLAGS_NONE


                        
                    Indicates that the path is not active and has not changed.


### -field IDDCX_PATH_FLAGS_CHANGED


                        Indicates if this path has changed
                    


### -field IDDCX_PATH_FLAGS_ACTIVE


                        Indicates if this path is active
                    


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