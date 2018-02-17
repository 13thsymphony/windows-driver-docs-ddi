---
UID: NS:nfcradiodev._NFCRM_RADIO_STATE
title: "_NFCRM_RADIO_STATE"
author: windows-driver-content
description: This structure is used to indicate the radio state.
old-location: nfpdrivers\_nfcrm_radio_state_.htm
old-project: nfpdrivers
ms.assetid: 414486ED-464D-4CAF-95C2-9AC59D608816
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: PNFCRM_RADIO_STATE, PNFCRM_RADIO_STATE structure pointer [Near-Field Proximity Drivers], nfcradiodev/PNFCRM_RADIO_STATE, *PNFCRM_RADIO_STATE, NFCRM_RADIO_STATE structure [Near-Field Proximity Drivers], nfcradiodev/NFCRM_RADIO_STATE, _NFCRM_RADIO_STATE, nfpdrivers._nfcrm_radio_state_, NFCRM_RADIO_STATE
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
-	NFCRM_RADIO_STATE
product: Windows
targetos: Windows
req.typenames: "*PNFCRM_RADIO_STATE, NFCRM_RADIO_STATE"
---

# _NFCRM_RADIO_STATE structure
This structure is used to indicate the radio state.

## Syntax
````
typedef struct _NFCRM_RADIO_STATE  {
  BOOLEAN MediaRadioOn;
} NFCRM_RADIO_STATE, *PNFCRM_RADIO_STATE;
````

## Members


`MediaRadioOn`

This is a boolean flag that indicates whether the media radio is on.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcradiodev.h |