---
UID: NS:ksmedia._tagKSTELEPHONY_CALLCONTROL
title: "_tagKSTELEPHONY_CALLCONTROL"
author: windows-driver-content
description: The KSTELEPHONY_CALLCONTROL structure specifies the phone call type and control operation to use for the KSPROPERTY_TELEPHONY_CALLCONTROL property.
old-location: audio\kstelephony_callcontrol.htm
old-project: audio
ms.assetid: 44CA5D9D-EF6E-4681-93EB-B803638896F9
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSTELEPHONY_CALLCONTROL, KSTELEPHONY_CALLCONTROL, KSTELEPHONY_CALLCONTROL structure [Audio Devices], PKSTELEPHONY_CALLCONTROL, PKSTELEPHONY_CALLCONTROL structure pointer [Audio Devices], _tagKSTELEPHONY_CALLCONTROL, audio.kstelephony_callcontrol, ksmedia/KSTELEPHONY_CALLCONTROL, ksmedia/PKSTELEPHONY_CALLCONTROL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSTELEPHONY_CALLCONTROL
product: Windows
targetos: Windows
req.typenames: KSTELEPHONY_CALLCONTROL, *PKSTELEPHONY_CALLCONTROL
---

# _tagKSTELEPHONY_CALLCONTROL structure
The <b>KSTELEPHONY_CALLCONTROL</b> structure specifies the phone call type and control operation to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169871">KSPROPERTY_TELEPHONY_CALLCONTROL</a> property.

## Syntax
```
typedef struct _tagKSTELEPHONY_CALLCONTROL {
  TELEPHONY_CALLTYPE      CallType;
  TELEPHONY_CALLCONTROLOP CallControlOp;
} *PKSTELEPHONY_CALLCONTROL, KSTELEPHONY_CALLCONTROL;
```

## Members


`CallType`

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).

`CallControlOp`

Specifies the call control operation (enable or disable).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10,Windows 10 Mobile Windows 10,Windows 10 Mobile |
| **Header** | ksmedia.h |