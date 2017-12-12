---
UID: NS.KSMEDIA.PTRANSPORT_STATE
title: PTRANSPORT_STATE
author: windows-driver-content
description: The TRANSPORT_STATE structure
old-location: stream\transport_state.htm
old-project: stream
ms.assetid: 373fb91d-e469-4136-b2e3-bf57016c0fd6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PTRANSPORT_STATE, TRANSPORT_STATE, *PTRANSPORT_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TRANSPORT_STATE
req.alt-loc: ksmedia.h
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

# PTRANSPORT_STATE structure



## -description
The TRANSPORT_STATE structure 



## -syntax

````
typedef struct {
  ULONG Mode;
  ULONG State;
} TRANSPORT_STATE, *PTRANSPORT_STATE;
````


## -struct-fields

### -field Mode

Specifies the mode of the external device transport.


### -field State

Specifies the state of the external device transport mode.


## -remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

The following modes and states are used by <i>msdv.sys </i>and <i>mstape.sys</i>:

When <b>Mode</b> equals ED_MODE_RECORD, <b>State</b> may be:

ED_MODE_RECORD

ED_MODE_RECORD_FREEZE.

When <b>Mode</b> equals ED_MODE_PLAY, <b>State</b> may be:

ED_MODE_PLAY

ED_MODE_REV_PLAY

ED_MODE_STEP_FWD

ED_MODE_STEP_REV

ED_MODE_PLAY_SLOWEST_FWD

ED_MODE_PLAY_FASTEST_FWD

ED_MODE_PLAY_SLOWEST_REV

ED_MODE_PLAY_FASTEST_REV

ED_MODE_FREEZE

<b>Mode</b> equals <b>State</b> in the cases of:

ED_MODE_REW_FASTEST

ED_MODE_STOP

ED_MODE_FF


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>