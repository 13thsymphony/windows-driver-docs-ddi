---
UID: NS:nfcradiodev._NFCRM_SET_RADIO_STATE
title: _NFCRM_SET_RADIO_STATE
author: windows-driver-content
description: This structure is used to set the radio state. The driver, in the case of airplane mode, has to persist the radio state and restore it when airplane mode is disabled.
old-location: nfpdrivers\_nfcrm_set_radio_state_.htm
old-project: nfpdrivers
ms.assetid: 22FE29AC-790D-40D2-949F-9C132F67AEAB
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: _NFCRM_SET_RADIO_STATE, NFCRM_SET_RADIO_STATE, *PNFCRM_SET_RADIO_STATE
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
req.alt-api: _NFCRM_SET_RADIO_STATE
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
req.typenames: NFCRM_SET_RADIO_STATE, *PNFCRM_SET_RADIO_STATE
---

# _NFCRM_SET_RADIO_STATE structure



## -description
This structure is used to set the radio state. The driver, in the case of airplane mode, has to persist the radio state and restore it when airplane mode is disabled.



## -syntax

````
typedef struct _NFCRM_SET_RADIO_STATE  {
  BOOLEAN SystemStateUpdate;
  BOOLEAN MediaRadioOn;
} _NFCRM_SET_RADIO_STATE, *P_NFCRM_SET_RADIO_STATE;
````


## -struct-fields

### -field SystemStateUpdate

The <b>SystemStateUpdate</b>. If true, indicates that IOCTL_NFCRM_SET_RADIO_STATE is triggered by airplane mode.


### -field MediaRadioOn

The <b>MediaRadioOn</b> flag either enables the system trigger (airplane mode if  <b>SystemStateUpdate</b> is true) or disables it.


## -remarks
Airplane mode status is ON if  <b>SystemStateUpdate</b> is true and <b>MediaRadioOn</b> is false.






Airplane mode status is OFF if  <b>SystemStateUpdate</b> is true and <b>MediaRadioOn</b> is true.






NFC status is ON if <b>SystemStateUpdate</b> is false and <b>MediaRadioOn</b> is true.






NFC status is OFF if <b>SystemStateUpdate</b> is false and <b>MediaRadioOn</b> is false.


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