---
UID: NE.rilapitypes.RILMSGCDMAMSGENCODING
title: RILMSGCDMAMSGENCODING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgencoding_2.htm
old-project: netvista
ms.assetid: 85586f69-09c3-4ebe-ad90-eb1b18e9d552
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGCDMAMSGENCODING, RILMSGCDMAMSGENCODING
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
req.alt-api: RILMSGCDMAMSGENCODING
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILMSGCDMAMSGENCODING enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILMSGCDMAMSGENCODING { 
  RIL_MSGCODING_7BITASCII,
  RIL_MSGCODING_UNICODE,
  RIL_MSGCODING_7BITGSM,
  RIL_MSGCODING_8BITGSM,
  RIL_MSGCODING_OCTET,
  RIL_MSGCODING_IA5,
  RIL_MSGCODING_JIS,
  RIL_MSGCODING_KOREAN,
  RIL_MSGCODING_LATIN_HEBREW,
  RIL_MSGCODING_LATIN,
  RIL_MSGCODING_MAX
} RILMSGCDMAMSGENCODING;
````


## -enum-fields

### -field RIL_MSGCODING_7BITASCII


### -field RIL_MSGCODING_UNICODE


### -field RIL_MSGCODING_7BITGSM


### -field RIL_MSGCODING_8BITGSM


### -field RIL_MSGCODING_OCTET


### -field RIL_MSGCODING_IA5


### -field RIL_MSGCODING_JIS


### -field RIL_MSGCODING_KOREAN


### -field RIL_MSGCODING_LATIN_HEBREW


### -field RIL_MSGCODING_LATIN


### -field RIL_MSGCODING_MAX


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>