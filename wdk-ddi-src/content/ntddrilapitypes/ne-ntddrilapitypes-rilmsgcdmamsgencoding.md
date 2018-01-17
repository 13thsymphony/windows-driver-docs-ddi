---
UID: NE:ntddrilapitypes.RILMSGCDMAMSGENCODING
title: RILMSGCDMAMSGENCODING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmamsgencoding.htm
old-project: netvista
ms.assetid: d0bc5fa4-d08d-484c-b6e0-35c7f1d144c3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGCDMAMSGENCODING, RILMSGCDMAMSGENCODING
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
req.alt-api: RILMSGCDMAMSGENCODING
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
req.typenames: RILMSGCDMAMSGENCODING
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
