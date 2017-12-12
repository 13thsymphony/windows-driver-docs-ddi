---
UID: NE.ntddrilapitypes.RILMSGMWITYPE
title: RILMSGMWITYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwitype.htm
old-project: netvista
ms.assetid: e5faa899-194a-412c-9308-a84227a31a6a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGMWITYPE, RILMSGMWITYPE
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
req.alt-api: RILMSGMWITYPE
req.alt-loc: ntddrilapitypes.h
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

# RILMSGMWITYPE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILMSGMWITYPE { 
  RIL_MSGMWITYPE_VOICEMAIL,
  RIL_MSGMWITYPE_VIDEOMAIL,
  RIL_MSGMWITYPE_FAX,
  RIL_MSGMWITYPE_PAGER,
  RIL_MSGMWITYPE_MULTIMEDIA,
  RIL_MSGMWITYPE_TEXT,
  RIL_MSGMWITYPE_MAX
} RILMSGMWITYPE;
````


## -enum-fields

### -field RIL_MSGMWITYPE_VOICEMAIL


### -field RIL_MSGMWITYPE_VIDEOMAIL


### -field RIL_MSGMWITYPE_FAX


### -field RIL_MSGMWITYPE_PAGER


### -field RIL_MSGMWITYPE_MULTIMEDIA


### -field RIL_MSGMWITYPE_TEXT


### -field RIL_MSGMWITYPE_MAX


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>