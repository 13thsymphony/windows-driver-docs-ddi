---
UID: NS.NTDDRILAPITYPES.RILMSGMWIDETAIL
title: RILMSGMWIDETAIL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwidetail.htm
old-project: netvista
ms.assetid: 69371414-9f4a-46a6-8622-5750db7a0c5b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGMWIDETAIL, RILMSGMWIDETAIL, *LPRILMSGMWIDETAIL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMSGMWIDETAIL
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

# RILMSGMWIDETAIL structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMSGMWIDETAIL {
  RILMSGMWITYPE      dwMwiType;
  RILMSGMWIPRIORITY  dwMwiPriority;
  RILADDRESS         raToAddress;
  RILADDRESS         raFromAddress;
  RILSYSTEMTIME      stDateSent;
  WCHAR [256]        wszSubject;
  WCHAR [256]        wszMessageId;
} RILMSGMWIDETAIL, RILMSGMWIDETAIL;
````


## -struct-fields

### -field dwMwiType


### -field dwMwiPriority


### -field raToAddress


### -field raFromAddress


### -field stDateSent


### -field wszSubject


### -field wszMessageId


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