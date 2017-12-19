---
UID: NS.NTDDVDEO._VIDEO_POINTER_POSITION
title: _VIDEO_POINTER_POSITION
author: windows-driver-content
description: The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.
old-location: display\video_pointer_position.htm
old-project: display
ms.assetid: 07586be9-a8bc-4149-8037-7b649a75a818
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION, PVIDEO_POINTER_POSITION, VIDEO_POINTER_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_POINTER_POSITION
req.alt-loc: Ntddvdeo.h
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

# _VIDEO_POINTER_POSITION structure



## -description
The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.



## -syntax

````
typedef struct _VIDEO_POINTER_ATTRIBUTES {
  SHORT Column;
  SHORT Row;
} VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION;
````


## -struct-fields

### -field Column

Specifies the column location of the pointer in pixels, starting from the top left corner of the screen.


### -field Row

Specifies the row location of the pointer in pixels, starting from the top left corner of the screen.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>