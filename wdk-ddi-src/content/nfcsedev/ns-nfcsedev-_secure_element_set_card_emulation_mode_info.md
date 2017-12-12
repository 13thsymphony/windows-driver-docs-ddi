---
UID: NS.NFCSEDEV._SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
title: _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
author: windows-driver-content
description: SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO is the input parameter for IOCTL_NFCSE_SET_CARD_EMULATION_MODE.
old-location: nfpdrivers\secure_element_set_card_emulation_mode_info.htm
old-project: nfpdrivers
ms.assetid: 64EE1896-DD19-42AD-92D7-3B3498A83E75
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, *PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
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
req.alt-api: SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO
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

# _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO structure



## -description
SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO is the input parameter for  <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_set_card_emulation_mode.md">IOCTL_NFCSE_SET_CARD_EMULATION_MODE</a>.



## -syntax

````
typedef struct _SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO {
  GUID                               guidSecureElementId;
  SECURE_ELEMENT_CARD_EMULATION_MODE eMode;
} SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO, *PSECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO;
````


## -struct-fields

### -field guidSecureElementId

This is a unique identifier for the secure element.


### -field eMode

Card emulation mode: off, power dependent, or power-independent.



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