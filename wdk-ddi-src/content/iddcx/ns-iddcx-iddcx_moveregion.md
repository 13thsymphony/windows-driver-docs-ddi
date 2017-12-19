---
UID: NS.IDDCX.IDDCX_MOVEREGION
title: IDDCX_MOVEREGION
author: windows-driver-content
description: Gives information about the current move region.
old-location: display\iddcx_moveregion.htm
old-project: display
ms.assetid: 28974c00-9225-4458-a198-beb4538e3a45
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDDCX_MOVEREGION,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDDCX_MOVEREGION
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
req.irql: 
---

# IDDCX_MOVEREGION structure



## -description

                 Gives information about the current move region.



## -syntax

````
typedef struct IDDCX_MOVEREGION {
  UINT  Size;
  POINT SourcePoint;
  RECT  DestRect;
} IDDCX_MOVEREGION, *IDDCX_MOVEREGION;
````


## -struct-fields

### -field Size


                     Total size of the structure.
                 


### -field SourcePoint


                     The location within the surface of the top left of the source rect. The source rect size is the same as the
    destination rect size.
                 


### -field DestRect


                     Defines the destination rect of the move.
                 


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