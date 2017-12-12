---
UID: NE.rilapitypes.RILMSGCDMALANGUAGE
title: RILMSGCDMALANGUAGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmalanguage_2.htm
old-project: netvista
ms.assetid: d1ad512e-10ba-4266-9688-2fc8e63bb4c4
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGCDMALANGUAGE, RILMSGCDMALANGUAGE
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
req.alt-api: RILMSGCDMALANGUAGE
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

# RILMSGCDMALANGUAGE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILMSGCDMALANGUAGE { 
  RIL_MSGCDMALANG_ENGLISH,
  RIL_MSGCDMALANG_FRENCH,
  RIL_MSGCDMALANG_SPANISH,
  RIL_MSGCDMALANG_JAPANESE,
  RIL_MSGCDMALANG_KOREAN,
  RIL_MSGCDMALANG_CHINESE,
  RIL_MSGCDMALANG_HEBREW,
  RIL_MSGCDMALANG_MAX
} RILMSGCDMALANGUAGE;
````


## -enum-fields

### -field RIL_MSGCDMALANG_ENGLISH


### -field RIL_MSGCDMALANG_FRENCH


### -field RIL_MSGCDMALANG_SPANISH


### -field RIL_MSGCDMALANG_JAPANESE


### -field RIL_MSGCDMALANG_KOREAN


### -field RIL_MSGCDMALANG_CHINESE


### -field RIL_MSGCDMALANG_HEBREW


### -field RIL_MSGCDMALANG_MAX


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