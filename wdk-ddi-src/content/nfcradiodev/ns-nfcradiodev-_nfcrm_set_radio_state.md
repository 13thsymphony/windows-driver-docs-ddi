---
UID: NS:nfcradiodev._NFCRM_SET_RADIO_STATE
title: "_NFCRM_SET_RADIO_STATE"
author: windows-driver-content
description: This structure is used to set the radio state. The driver, in the case of airplane mode, has to persist the radio state and restore it when airplane mode is disabled.
old-location: nfpdrivers\_nfcrm_set_radio_state_.htm
old-project: nfpdrivers
ms.assetid: 22FE29AC-790D-40D2-949F-9C132F67AEAB
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NFCRM_SET_RADIO_STATE, NFCRM_SET_RADIO_STATE structure [Near-Field Proximity Drivers], P_NFCRM_SET_RADIO_STATE structure pointer [Near-Field Proximity Drivers], nfpdrivers._nfcrm_set_radio_state_, nfcradiodev/NFCRM_SET_RADIO_STATE, _NFCRM_SET_RADIO_STATE, _NFCRM_SET_RADIO_STATE structure [Near-Field Proximity Drivers], *PNFCRM_SET_RADIO_STATE, P_NFCRM_SET_RADIO_STATE, nfcradiodev/P_NFCRM_SET_RADIO_STATE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcradiodev.h
apiname:
-	_NFCRM_SET_RADIO_STATE
product: Windows
targetos: Windows
req.typenames: NFCRM_SET_RADIO_STATE, *PNFCRM_SET_RADIO_STATE
---

# _NFCRM_SET_RADIO_STATE structure
This structure is used to set the radio state. The driver, in the case of airplane mode, has to persist the radio state and restore it when airplane mode is disabled.

## Syntax
````
typedef struct _NFCRM_SET_RADIO_STATE  {
  BOOLEAN SystemStateUpdate;
  BOOLEAN MediaRadioOn;
} _NFCRM_SET_RADIO_STATE, *P_NFCRM_SET_RADIO_STATE;
````

## Members


`MediaRadioOn`

The <b>MediaRadioOn</b> flag either enables the system trigger (airplane mode if  <b>SystemStateUpdate</b> is true) or disables it.

`SystemStateUpdate`

The <b>SystemStateUpdate</b>. If true, indicates that IOCTL_NFCRM_SET_RADIO_STATE is triggered by airplane mode.

## Remarks
Airplane mode status is ON if  <b>SystemStateUpdate</b> is true and <b>MediaRadioOn</b> is false.






Airplane mode status is OFF if  <b>SystemStateUpdate</b> is true and <b>MediaRadioOn</b> is true.






NFC status is ON if <b>SystemStateUpdate</b> is false and <b>MediaRadioOn</b> is true.






NFC status is OFF if <b>SystemStateUpdate</b> is false and <b>MediaRadioOn</b> is false.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcradiodev.h |