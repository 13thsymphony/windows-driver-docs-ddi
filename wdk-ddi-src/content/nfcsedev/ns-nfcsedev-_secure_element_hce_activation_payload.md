---
UID: NS.NFCSEDEV._SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD
title: _SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD
author: windows-driver-content
description: .
old-location: nfpdrivers\secure_element_hce_activation_payload.htm
old-project: nfpdrivers
ms.assetid: 2FFEB2DB-7506-4CDB-BD5F-41D2E4212017
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD, SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD, *PSECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD
req.alt-loc: nfcsedev.h
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

# _SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD structure



## -description



## -syntax

````
typedef struct _SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD {
  USHORT bConnectionId;
  BYTE   eRfTechType;
  BYTE   eRfProtocolType;
} SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD, *PSECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD;
````


## -struct-fields

### -field bConnectionId

Unique identifer for current connection.

### -field eRfTechType

NFC Forum RF technology type.


### -field eRfProtocolType

NFC Forum RF protocol
type.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Nfcsedev.h</dt>
</dl>
</td>
</tr>
</table>