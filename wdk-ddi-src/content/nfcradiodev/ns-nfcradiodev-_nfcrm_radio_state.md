---
UID: NS.NFCRADIODEV._NFCRM_RADIO_STATE
title: _NFCRM_RADIO_STATE
author: windows-driver-content
description: This structure is used to indicate the radio state.
old-location: nfpdrivers\_nfcrm_radio_state_.htm
old-project: nfpdrivers
ms.assetid: 414486ED-464D-4CAF-95C2-9AC59D608816
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _NFCRM_RADIO_STATE, *PNFCRM_RADIO_STATE, NFCRM_RADIO_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcradiodev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NFCRM_RADIO_STATE
req.alt-loc: nfcradiodev.h
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

# _NFCRM_RADIO_STATE structure



## -description
This structure is used to indicate the radio state.


## -syntax

````
typedef struct _NFCRM_RADIO_STATE  {
  BOOLEAN MediaRadioOn;
} NFCRM_RADIO_STATE, *PNFCRM_RADIO_STATE;
````


## -struct-fields

### -field MediaRadioOn

This is a boolean flag that indicates whether the media radio is on.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Nfcradiodev.h</dt>
</dl>
</td>
</tr>
</table>