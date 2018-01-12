---
UID: NE:bthddi._PCM_DATA_FORMAT
title: _PCM_DATA_FORMAT
author: windows-driver-content
description: This enumeration is for internal use only.
old-location: bltooth\pcm_data_format.htm
old-project: bltooth
ms.assetid: 50B76D96-120C-4C86-89ED-7F298E50B1A4
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _PCM_DATA_FORMAT, PCM_DATA_FORMAT, *PPCM_DATA_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCM_DATA_FORMAT
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames: PCM_DATA_FORMAT, *PPCM_DATA_FORMAT
---

# _PCM_DATA_FORMAT enumeration



## -description
This enumeration is for internal use only.



## -syntax

````
typedef enum _PCM_DATA_FORMAT { 
    = 
} PCM_DATA_FORMAT, *PPCM_DATA_FORMAT;
````


## -enum-fields

### -field 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>